# Benchmark Method

## 1. Goal

Measure how a Minecraft modpack instance (**Adrenaline**) performs along an identical, repeatable path through a village scene, so it can be compared fairly with another instance (**Citron**). The aim is to remove every source of randomness that does not come from the game's own performance, and to report community-standard metrics (average FPS, median FPS, percentile lows).

## 2. Test environment

| Item | Value |
|---|---|
| Minecraft version | `<version>` |
| Loader | Fabric `<loader version>` |
| Carpet mod | `<fabric-carpet version>` |
| Capture tool | CapFrameX `<version>` |
| CPU / GPU / RAM | `<specs>` |
| OS / GPU driver | `<OS, driver version>` |
| Java version | `<version>` |
| JVM allocation | `-Xms<..> -Xmx<..>`, plus `<other JVM args>` |
| Resolution / mode | `<e.g. 1920x1080, fullscreen>` |
| Render / simulation distance | `<e.g. 16 / 12>` |
| Other settings | VSync off, max framerate unlimited, HUD hidden (F1) |
| Shaders / resource packs | `<none or list>` |

## 3. World preparation

### 3.1 Setup world and benchmark world

1. A **setup world** was created with a fixed seed containing the village scene.
2. All environment commands (3.2), Chunky pre-generation (3.3) and the entity lock-down (3.4) were run in the setup world.
3. The world was saved (`/save-all flush`) and closed.
4. The setup world was **duplicated before recording**, producing the **benchmark world**. This keeps the benchmark copy in a clean state, since recording itself changes the world.
5. The path was recorded in the setup world, and the recording file was copied into the benchmark world.
6. The benchmark world is kept as a master copy and is copied into each instance's `saves` folder, so every instance starts from byte-identical data.

### 3.2 Environment commands

```
/gamerule doDaylightCycle false
/gamerule doWeatherCycle false
/gamerule doMobSpawning false
/gamerule doPatrolSpawning false
/gamerule doTraderSpawning false
/gamerule randomTickSpeed 0
/gamerule mobGriefing false
/gamerule doEntityDrops false
/time set 6000
/weather clear 1000000
/difficulty peaceful
```

Fixed time (noon) and clear weather give identical lighting and sky rendering. `randomTickSpeed 0` stops crop growth, leaf decay and spread. `/save-off` removes autosave hitches during runs. (Newer versions rename some gamerules, so check with tab-complete.)

### 3.3 Chunk pre-generation (Chunky)

```
/chunky world world
/chunky center
/chunky shape square
/chunky radius 800
/chunky start
```

The radius covers the whole route plus the render distance. The task was left to finish (`/chunky progress`) so that no world generation happens during a run.

### 3.4 Entity control

Entities were kept (so their rendering and ticking cost is part of the test) but locked in place:

```
/execute as @e[type=!player] run data merge entity @s {NoAI:1b,Silent:1b,PersistenceRequired:1b,Invulnerable:1b}
```

Items, boats and minecarts were removed with `/kill`. `/tick freeze` was **not** used, because it removes server-side ticking and animation work that exists in real play, and it can stop the Carpet script.

### 3.5 Warm-up of the world

The route was replayed once in the benchmark world before any recorded run, so first-visit chunk lighting and entity loading were already done.

## 4. Path recording and replay (Carpet scripting)

Walking the route by hand differs every time, so the game replays it instead.

- **Recording:** the Carpet script saves the player's position and camera angle (`x, y, z, yaw, pitch`) every game tick (20 per second) while the route is walked once.
- **Replay:** the script teleports the player to the first recorded point, shows a 3-2-1 countdown with sounds, then sets the player's position and camera to the recorded value every tick until the end.
- The replay is driven by game ticks, not frames, so the path and timing are the same on every run regardless of FPS.
- Pauses in the recording are replayed too, so deliberate stops in dense areas give steady scene readings.

### 4.1 Commands

| Command | Purpose |
|---|---|
| `/script load bench` | Load the script (once per session) |
| `/bench record` | Start recording |
| `/bench mark <name>` | Optional section label (typing causes a pause) |
| `/bench save` | Stop recording and write the file |
| `/bench play` | Countdown, then replay |
| `/bench stop` | Cancel recording or replay |

### 4.2 Script (`<world>/scripts/bench.sc`)

```
__config() -> {'scope' -> 'global',
  'commands' -> {
    'record' -> 'bench_record',
    'mark <name>' -> 'bench_mark',
    'save' -> 'bench_save',
    'play' -> 'bench_play',
    'stop' -> 'bench_stop'
  },
  'arguments' -> {'name' -> {'type' -> 'string'}}
};

global_path = l();
global_marks = l();
global_state = 'idle';
global_i = 0;
global_m = 0;

bench_record() -> (
  global_path = l();
  global_marks = l();
  global_state = 'recording';
  print(player(), 'Recording... use /bench mark <name> at section starts, /bench save when done');
  schedule(0, '_rec');
);

_rec() -> (
  if(global_state != 'recording', return());
  put(global_path, null, query(player(), 'location'));
  schedule(1, '_rec');
);

bench_mark(name) -> (
  if(global_state != 'recording', return(print(player(), 'Not recording')));
  put(global_marks, null, l(length(global_path), name));
  print(player(), 'Marker ' + name + ' at ' + str('%.1f', length(global_path) / 20) + 's');
);

bench_save() -> (
  global_state = 'idle';
  write_file('path', 'json', {'path' -> global_path, 'marks' -> global_marks});
  print(player(), 'Saved ' + length(global_path) + ' ticks (' + round(length(global_path) / 20) + ' seconds), ' + length(global_marks) + ' markers');
);

bench_play() -> (
  data = read_file('path', 'json');
  if(!data, return(print(player(), 'No saved path found')));
  if(type(data) == 'list', data = {'path' -> data, 'marks' -> l()});
  global_path = data:'path';
  global_marks = data:'marks';
  global_i = 0;
  global_m = 0;
  global_state = 'counting';
  _count(3);
);

_count(n) -> (
  if(global_state != 'counting', return());
  p = player();
  modify(p, 'location', global_path:0);
  if(n > 0,
    display_title(p, 'title', str(n), 0, 25, 0);
    sound('block.note_block.pling', pos(p), 1, 1);
    schedule(20, '_count', n - 1),
    display_title(p, 'title', 'GO', 0, 15, 5);
    sound('block.note_block.pling', pos(p), 1, 2);
    global_state = 'playing';
    schedule(0, '_play')
  );
);

_play() -> (
  if(global_state != 'playing', return());
  while(global_m < length(global_marks) && global_marks:global_m:0 <= global_i, 1000,
    mk = global_marks:global_m;
    print(player(), '[marker] ' + mk:1 + ' @ ' + str('%.1f', mk:0 / 20) + 's');
    sound('block.note_block.hat', pos(player()), 1, 1.5);
    global_m += 1
  );
  if(global_i >= length(global_path),
    global_state = 'idle';
    print(player(), 'Done - stop capture. Marker times:');
    for(global_marks, print(player(), _:1 + ' = ' + str('%.1f', _:0 / 20) + 's'));
    return()
  );
  modify(player(), 'location', global_path:global_i);
  global_i += 1;
  schedule(1, '_play');
);

bench_stop() -> ( global_state = 'idle'; );
```

### 4.3 Route design

The route is a loop around the village, finishing at the starting point. It deliberately includes sections that stress different parts of the renderer:

| Section | What it stresses |
|---|---|
| Village centre | Entity and block entity rendering |
| Dense trees / leaves | Transparency, culling |
| Distant skyline | Render distance, chunk rendering |
| Fast camera turn | Chunk rebuilds |
| Hillside / cave entrance | Occlusion culling |

`<edit to match your actual route and path length: e.g. 95 s, N ticks>`

## 5. Capture procedure (CapFrameX)

1. Launch the instance, load the benchmark world, run `/save-off` and `/script load bench`.
2. Start `/bench play`. The 3-2-1 countdown gives a fixed cue.
3. Start the CapFrameX capture on the same cue every run (`<GO or the final beep>`) and stop it when the script prints "Done".
4. **Run 0** was a cold boot, the first capture after launching the game. It is reported separately and excluded from statistics.
5. **Runs 1-20** were recorded back to back in the same session, about 3-4 minutes apart (16:13 to 17:26).
6. Background applications were closed, the same power plan was used and the system was plugged in.

## 6. Metrics

| Metric | Meaning |
|---|---|
| Average FPS | Total frames divided by total capture time |
| Median FPS | Middle FPS value, less affected by outlier frames |
| P1 FPS | 1st percentile FPS; 99% of the time the game ran faster than this |
| 1% Low | Average FPS of the slowest 1% of frames |
| 0.1% Low | Average FPS of the slowest 0.1% of frames, which shows severe stutter |
| Min FPS | Lowest single-frame FPS in the run |
| Variation (CV) | Standard deviation divided by mean across runs, as a percentage; lower means more repeatable |

Columns not used in the report: Max FPS, P99 and P95 FPS, P0.2 FPS, the integral low variants, animation error, adaptive STDEV and per-watt efficiency. They add little to a modpack comparison.

## 7. Analysis

1. Runs 1-20 were summarised with mean, median, min, max, standard deviation and CV for each metric.
2. **Drift** was checked by averaging blocks of five runs (1-5, 6-10, 11-15, 16-20) and comparing first and last blocks.
3. A **steady-state baseline** was taken from the last ten runs (11-20), after the session had settled.
4. **Outliers** were identified by comparing each run's P1 and 1% low with the rest. Runs 1 and 2 were flagged.
5. The **median-to-average gap** and the **low-to-average ratios** were used as indicators of stutter.
6. Differences between instances are only considered meaningful if they exceed the run-to-run CV (about 3%, as the steady-state runs met the 2-3% target).

## 8. Limitations

- Results are specific to this hardware,
