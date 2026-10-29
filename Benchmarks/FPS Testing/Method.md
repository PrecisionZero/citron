# Benchmark Method

Since this is a modpack, I have made Citron and Adrenaline undergo rigorous testing to see how well each of them performs. Adrenaline is taken as the comparitive pack as it's the base for Citron and is a well optimized modpack overall.

## 1. Goal

- Obtain accurate FPS readings and performance data
- Test in stationary and pixel perfect movement environments to obtain reliable "real world" recreative data
- Report them in a way that shows the averages, medians, and variation

## 2. Test environment

### System

| Item | Value |
|---|---|
| Minecraft version | `1.21.11` |
| Capture tool | CapFrameX `1.9.1.5` |
| CPU | `Intel Core i3-8145u` |
| GPU | `Intel UHD Graphics 620` |
| RAM | `12GB, 4096MB Allocated` |

### Minecraft

| Setting | Value |
| --- | --- |
| **Render Distance** | 16 Chunks |
| **Simulation Distance** | 5 Chunks |
| **Max Framerate** | Unlimited |
| **Fullscreen** | On |
| **VSync** | Off |
|  |  |
| **Smooth Lighting** | On |
| **Biome Blend** | 2x2 |
| **Clouds** | On (Fancy) |
| **Particles** | All |
| **Mipmap Levels** | 4 |
|  |  |
| **Seed** | `5872972574357925067` |

## 3. Preparation

### 3.1 World creation

- A benchmark world was created with a fixed seed containing a village scene
- Chunky was used to pregenerate chunks around a 600 block radius before testing began

### 3.2 Commands

These commands were run to ensure fair tests throughout

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

#### Environment control
- Items, boats and minecarts were removed with `/kill`.
- `/tick freeze` was **not** used, because it removes server-side ticking and animation work that exists in real play.
- Entities were kept ticking, but locked in place, using `/execute as @e[type=!player] run data merge entity @s {NoAI:1b,Silent:1b,PersistenceRequired:1b,Invulnerable:1b}`, that way I could get fair entity based readings without it changing due to entity movement.

---

# Stationary test

## 1. Method

1. Stand at a fixed location, facing a fixed direction of a loaded world
- Take 10 captures of 60 seconds each per pack
- Use the same world, scene, settings, and external conditions for both packs
- Report the data in [Stationary_Results.md](Stationary_Results.md)


Existing stationary results use the earlier setup of 12-chunk render distance and 8-chunk simulation distance. The current setup above uses 16 and 5; treat results from these configurations separately.
---

# Movement test

## 1. Method

### 1.1 Path recording

1. I used Carpet and a custom script to record myself walking along a certain path by hand
2. The script saves the player's position and camera angle (`x, y, z, yaw, pitch`) every game tick (20 per second) while the route is walked once
3. I made sure to make a complete loop back to the starting position before ending the recording

The script for those who are interested:
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

### 1.2 Replay

1. I ensured that the system environment was same before the test by keeping the CPU Processes at 155 at an offset of +- 5 and RAM at 5.5GB (Total Utilized) at an offset of +- 200MB
2. I used the same world, with the same script, and same `options.txt` for Adrenaline and Citron before beginning each test

#### Script explained
- The script teleports the player to the first recorded point, shows a 3-2-1 countdown with sounds, then sets the player's position and camera to the recorded value every tick until the end.
- The replay is driven by game ticks, not frames, so the path and timing are the same on every run regardless of FPS.
- Pauses in the recording are replayed too, so deliberate stops in dense areas give steady scene readings.

#### Route recorded and replayed
| Section | What it stresses |
|---|---|
| Village centre | Entity and block entity rendering |
| Trees | Transparency, culling |
| Distant skyline | Render distance, chunk rendering |
| Mobs | Entity rendering and management |

#### Result
- Over 20 replays were taken per modpack and it clearly showed the difference in performances between them
- The full report is available in the [Movement_Results.md](Movement_Results.md)
