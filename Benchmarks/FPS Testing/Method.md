# FPS Benchmark Method

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

The benchmark world uses fixed daytime and clear weather, disabled spawning and random ticks, and immobilised non-player entities. Chunks are pregenerated before capture. Server ticking is not frozen.

## Stationary test

- Use the same fixed position and camera direction.
- Wait 60 seconds after loading the world.
- Capture for 60 seconds per run.
- Keep world, scene, settings, and external conditions identical.

The historical stationary results use 12-chunk render distance and 8-chunk simulation distance. See [Stationary Results](Stationary_Results.md).

## Movement test

- Record a complete route once with Carpet, saving position and camera rotation every game tick.
- Replay the same route and world for each pack.
- Keep CPU process count at 155 ±5 and total RAM use at 5.5 GB ±200 MB.
- Keep system power conditions, game settings, and options identical.
- Capture from the start cue until the replay ends.

The replay is tick-based, so route and timing do not depend on FPS. See [Movement Results](Movement_Results.md).

## Reported metrics

| Metric | Meaning | Better |
|---|---|---|
| Average FPS | Mean frame rate during the capture | Higher |
| Median FPS | Median frame rate during the capture | Higher |
| P1 FPS | First-percentile frame rate | Higher |
| 1% low average FPS | Average of the slowest 1% of frames | Higher |
| 0.1% low average FPS | Average of the slowest 0.1% of frames | Higher |
| Min FPS | Lowest single-frame frame rate | Higher |

## Statistical breakdown

- Keep cold captures in the raw data; exclude them from warm-run statistics.
- Report mean, median, minimum, maximum, sample standard deviation, sample variance, and CV for each metric.
- CV = sample standard deviation / mean × 100%; lower CV means less run-to-run variation.
- Check movement-test drift using five-run blocks.
- Compare the last 10 warm captures as the steady-state result.
- Use median comparisons for the overall pack comparison and state capture counts.
- Report median FPS / Average FPS and low-to-average ratios as frame-consistency indicators.
