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
| Median FPS (raw capture field) | Median frame rate within an individual capture; retained in raw data only | Higher |
| P1 FPS | First-percentile frame rate | Higher |
| 1% low average FPS | Average of the slowest 1% of frames | Higher |
| 0.1% low average FPS | Average of the slowest 0.1% of frames | Higher |
| Min FPS | Lowest single-frame frame rate | Higher |

## Statistical breakdown

- Keep cold captures in the raw data; exclude them from warm-run statistics.
- For each exported metric, report the **mean** across captures and its **CV**.
- CV (coefficient of variation) = sample standard deviation / mean × 100%.
- CV is a percentage showing relative variation between separate captures. For example, a 5% CV means the standard deviation of the capture results is 5% of their mean. For the movement test, Adrenaline's Average FPS mean is 128.17 with a 5.3% CV (SD 6.79 FPS); Citron's mean is 105.82 with a 1.4% CV (SD 1.51 FPS). Citron is slower on average, but its separate capture results vary less relative to its mean.
- A CV of 1.4% is not 1.4% more FPS. It means the standard deviation across captures is 1.4% of the mean FPS.
- CV measures run-to-run variation, not frame-to-frame stutter within one capture.
- The per-capture CapFrameX field named `Median FPS` remains in raw tables only and is not included in across-run summaries.
- Check movement-test drift using five-run blocks.
- Compare the last 10 warm captures as the steady-state result.
- Compare packs using mean changes and CV, with capture counts stated.
