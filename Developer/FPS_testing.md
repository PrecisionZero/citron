# FPS Testing

## Purpose

This document records repeatable FPS and frame-time tests for Citron, compared against its Adrenaline foundation.

The standard test is intentionally simple: a stationary 60-second capture in a saved world, repeated three times per pack. It measures performance in one representative scene; it does not represent every Minecraft workload or every computer.

## Testing schedule

FPS benchmarks are performed **only for the final minor version in each major development series**.

For example:
- `dev.1.0.0`: no full FPS benchmark
- `dev.1.1.0`: no full FPS benchmark
- `dev.1.2.0`: run the FPS benchmark if this is the final minor version in the 1.x development series

Repeat the full benchmark for the final minor version in the next major series, such as `dev.2.2.0` if that is the final 2.x minor version.

Intermediate versions still receive the necessary launch, stability and changed-feature checks. A targeted performance check may be run to investigate a suspected regression, but it is not a scheduled full benchmark.

## Tools

- **CapFrameX:** capture and analyse FPS and frame-time data.
- **HWiNFO (optional):** monitor CPU/GPU temperatures, clocks and utilization if results look unusual.

Use the same versions of the tools for both packs within a comparison where possible.

## Standard test environment

### Software and hardware record

Fill in this information when performing a full benchmark.

| Item | Value |
|---|---|
| Test date | [YYYY-MM-DD] |
| Computer / model | [Fill in] |
| CPU | [Fill in] |
| GPU | [Fill in] |
| RAM | [Fill in] |
| Operating system and power mode | [Fill in] |
| GPU driver | [Fill in] |
| Java runtime | [Fill in] |
| CapFrameX version | [Fill in] |
| Minecraft version | 1.21.11 |
| Loader | Fabric |
| Adrenaline baseline build | `26.5.1+mc1.21.11.fabric` |

### Fixed in-game settings

Use the same settings for Adrenaline and Citron. Record any change to this profile before comparing results.

| Setting | Standard value |
|---|---|
| World | Same saved test world copied into both instances |
| Seed used to create test world | `5872972574357925067` |
| Test scene | Fixed position and viewing direction near the village |
| Render distance | 12 chunks |
| Simulation distance | 8 chunks |
| Graphics | Fancy |
| Shaders | Off |
| VSync | Off |
| Max Framerate | Unlimited |
| Resolution / display mode | Record the tested resolution and mode |
| Resource packs | Identical in both instances |
| Weather / time | Clear weather, noon; disable weather and daylight cycle |
| Other video settings | Keep identical between packs |

Commands for stabilizing the world (enable cheats for the test world if necessary):

```mcfunction
/gamerule doDaylightCycle false
/gamerule doWeatherCycle false
/time set noon
/weather clear
```

Use the same **world save**, not merely the same seed: generate the test area, save and quit, then copy that save into each instance. This prevents differences in world state or chunk generation from undermining the comparison. Do not change the world or settings between captures.

Keep the laptop plugged in, use the same Windows power mode, close unnecessary background applications, and avoid running other monitoring or capture tools that might interfere with CapFrameX.

## Standard test: stationary rendering

This is the required FPS test for each scheduled benchmark.

1. Launch the pack and load the prepared test world.
2. Stand at the recorded test coordinates, facing the recorded direction. Do not move during the stationary test.
3. Wait 60 seconds after the scene has loaded so the initial loading activity can settle. Do not attempt to load every chunk in the world.
4. In CapFrameX, select or confirm the Minecraft `javaw.exe` process and start a 60-second capture.
5. Do not move, open menus, or interact with the game during the capture.
6. Repeat until there are **three valid 60-second captures**. They can be taken in the same game session; keep the scene and settings unchanged.
7. Complete all three captures for Adrenaline and all three for the Citron version being tested.

If a capture is interrupted, records an incorrect process, or includes an obvious unrelated interruption (such as a notification or alt-tab), discard it, note why, and repeat it. Do not discard a valid run simply because its result is worse.

## Metrics to record

Use the same CapFrameX metric definitions for every comparison.

| Metric | Interpretation | Preferred direction |
|---|---|---|
| Average FPS | Overall rendering throughput | Higher |
| 1% low FPS | Performance in slower frames | Higher |
| P99 frame time (ms) | Frame time at the 99th percentile | Lower |
| Frames at or above 50 ms | Simple indicator of long frame-time spikes during the capture | Lower |

Frame-time spikes are a useful indicator, not a perfect count of visible stutters. Record the actual results reported by the same tool; do not mix results from different metric definitions.

## Raw Adrenaline baseline

### Minecraft 1.21.11

Build ID: `26.5.1+mc1.21.11.fabric`

#### Capture results

| Run | Average FPS | 1% low FPS | P99 frame time (ms) | Frames >= 50 ms |
|---|---:|---:|---:|---:|
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Summary

Record the **median of the three runs** for each metric.

| Metric | Median result |
|---|---:|
| Average FPS | — |
| 1% low FPS | — |
| P99 frame time (ms) | — |
| Frames >= 50 ms | — |

Notes / abnormal conditions: [Fill in]

This is the reference baseline for Citron on the same Minecraft version and the same test machine. Redo this baseline only if a material part of the environment changes, such as Minecraft / Adrenaline build, Java runtime, GPU driver, hardware, or the standard settings profile.

## Citron benchmark record

Create or update one record for **the final minor version of each major development series**. Do not fill in results until the captures have actually been performed.

### [Citron version, e.g. dev.1.2.0+mc1.21.11.fabric]

Adrenaline baseline build: `26.5.1+mc1.21.11.fabric`

#### Capture results

| Run | Average FPS | 1% low FPS | P99 frame time (ms) | Frames >= 50 ms |
|---|---:|---:|---:|---:|
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Summary

Use the median of the three runs for each metric.

| Metric | Adrenaline median | Citron median | Difference (%) | Better result |
|---|---:|---:|---:|---|
| Average FPS | — | — | — | — |
| 1% low FPS | — | — | — | — |
| P99 frame time (ms) | — | — | — | — |
| Frames >= 50 ms | — | — | — | — |

Calculate percentage difference consistently:

`Difference (%) = ((Citron median - Adrenaline median) / Adrenaline median) × 100`

For FPS metrics, a positive difference is generally better. For frame-time and spike-count metrics, a negative difference is generally better. For frames >= 50 ms, compare counts from captures of the same duration.

Notes / abnormal conditions: [Fill in]

## Optional test: movement and chunk loading

The stationary test is the standard requirement; this test is optional and is mainly useful when preparing a major milestone or evaluating changes to rendering, chunk loading, entities or particles.

- Use a fixed route and the same starting point, direction and settings.
- For ordinary traversal, use the same prepared world and route for both packs.
- To test new chunk generation, restore a copy of the world from before the route's chunks were generated before each run. Otherwise, subsequent runs will mostly test already-generated terrain.
- Capture 60 seconds per run and record the same metrics as the stationary test.
- Keep movement-test results separate from stationary results; do not combine them into one score.

## Interpretation

- Higher average FPS alone does not prove that a pack feels smoother.
- A promising result is higher average FPS and 1% low FPS without worse P99 frame time or more long frame-time spikes.
- Similar average FPS with better 1% lows and lower P99 frame time can still indicate a smoother experience.
- If results vary substantially between runs, check background activity, temperatures, clocks and test consistency before drawing conclusions.
- Small differences may be normal run-to-run variation. Treat this three-run test as a practical comparison, not a laboratory-grade or universal performance claim.

Results apply to the recorded hardware, software, settings and scene. They should not be presented as guaranteed performance improvements for every user or computer.
