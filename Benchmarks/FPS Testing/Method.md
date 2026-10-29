# FPS Testing Method

## Test Environment

| Item | Value |
|---|---|
| Minecraft | 1.21.11 |
| Capture tool | CapFrameX 1.9.1.5 |
| CPU | Intel Core i3-8145U |
| GPU | Intel UHD Graphics 620 |
| System RAM | 12 GB |
| Allocated RAM | 4096 MB |
| World seed | `5872972574357925067` |
| Render distance | 16 chunks |
| Simulation distance | 5 chunks |
| Max framerate | Unlimited |
| Fullscreen | On |
| VSync | Off |
| Smooth lighting | On |
| Biome blend | 2×2 |
| Clouds | Fancy |
| Particles | All |
| Mipmap levels | 4 |

Chunks were pregenerated within a 600-block radius. Time, weather, difficulty, and spawning were fixed. Non-player entities were immobilised; tick freezing was not used.

## Stationary Test

- Use the same fixed position and camera direction.
- Wait 60 seconds after loading the world.
- Take 10 captures of 60 seconds per pack.
- Older stationary results used 12-chunk render distance and 8-chunk simulation distance; keep them separate from results using the current settings.

Results: [Stationary Results](Stationary_Results.md).

## Movement Test

- Record a complete route once, saving player position and camera rotation every game tick.
- Replay the same route in the same world with the same game settings.
- Keep CPU process count at 155 ±5 and total RAM use at 5.5 GB ±200 MB.
- Each replay follows the recorded tick sequence, so route timing does not depend on FPS.

Results: [Movement Results](Movement_Results.md).

## Reported Metrics

- Average FPS
- Variance of Average FPS across captures

For warm-run summaries, exclude the initial cold capture.
