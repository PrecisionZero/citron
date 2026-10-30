# FPS Benchmark Method

Citron is compared against Adrenaline, its optimisation foundation, using repeatable stationary and movement tests. The two test types have separate result sets and settings; their FPS values should not be compared directly against each other.

## Test environment

| Item | Value |
|---|---|
| Minecraft | 1.21.11 |
| Capture tool | CapFrameX 1.9.1.5 |
| CPU | Intel Core i3-8145U |
| GPU | Intel UHD Graphics 620 |
| System RAM | 12 GB |
| Allocated RAM | 4096 MB |
| World seed | `5872972574357925067` |
| Movement render distance | 16 chunks |
| Movement simulation distance | 5 chunks |
| Max framerate | Unlimited |
| Fullscreen | On |
| VSync | Off |
| Smooth lighting | On |
| Biome blend | 2×2 |
| Clouds | Fancy |
| Particles | All |
| Mipmap levels | 4 |

The benchmark world uses a fixed daytime, clear weather, disabled spawning and random ticks, and immobilised non-player entities. Chunks are pregenerated before capture. Server ticking is not frozen.

## Stationary test

- Stand at the same fixed position and face the same direction.
- Wait 60 seconds after loading the world.
- Capture 60 seconds per run.
- Use identical world, scene, settings, and external conditions.

The historical stationary results use 12-chunk render distance and 8-chunk simulation distance. They are kept separate from the current movement setup. See [Stationary Results](Stationary_Results.md).

## Movement test

- Record a complete route once with Carpet, saving player position and camera rotation every game tick.
- Replay the same route in the same benchmark world for each pack.
- Keep CPU process count at 155 ±5 and total RAM use at 5.5 GB ±200 MB.
- Keep the same system power conditions, game settings, and options.
- Capture from the start cue until the replay finishes.

The replay is tick-based, so the route and its timing remain the same regardless of FPS. See [Movement Results](Movement_Results.md).

## Reported metrics

| Metric | Meaning |
|---|---|
| Average FPS | Mean frame rate during the capture |
| Median FPS | Median frame rate during the capture |
| P1 FPS | First-percentile frame rate |
| 1% low average FPS | Average frame rate of the slowest 1% of frames |
| 0.1% low average FPS | Average frame rate of the slowest 0.1% of frames |
| Min FPS | Lowest single-frame frame rate |

## Statistical breakdown

- Keep the cold capture in the raw results; exclude it from warm-run statistics.
- Report the mean, median, minimum, maximum, and sample variance across warm captures.
- Check movement-test drift using five-run blocks.
- Compare the last 10 warm captures as the steady-state result.
- Compare Citron and Adrenaline using the same metrics and state the capture counts.
