# Testing stage for FPS

## Testing method

- Tool: CapFrameX
- FPS testing is only done for the final version in each major development series.
- Example: test `dev.1.2.0` if it is the final 1.x version, not `dev.1.0.0` or `dev.1.1.0`.
- Use 3 captures, each 60 seconds long.
- Wait 60 seconds after loading the world before capturing.
- Use the same settings and saved world for Adrenaline and Citron.

### Test settings

| Setting | Value |
| --- | --- |
| World seed | `5872972574357925067` |
| Test scene | Same position and direction near the village; record coordinates before testing |
| Render distance | 12 chunks |
| Simulation distance | 8 chunks |
| Graphics | Custom |
| Shaders | Off |
| VSync | Off |
| Max framerate | 260 FPS |
| Fullscreen | On |
| Resolution | Native display resolution |
| Biome blend | 2 |
| Particles | Minimal |
| Clouds | On |
| Entity distance scaling | 100% |
| Entity shadows | On |
| Mipmap levels | 4 |
| Resource packs | None |
| Weather / time | Clear / noon |

Disable the daylight and weather cycles in the test world:

```mcfunction
/gamerule doDaylightCycle false
/gamerule doWeatherCycle false
/time set noon
/weather clear
```

Use the same world save in both instances, not just the same seed. Keep the laptop plugged in and use the same Windows power mode. Keep all video settings identical.

The 260 FPS cap reflects the current `options.txt`. Keep it for a realistic test using your current settings. Because this cap can limit the measured FPS, do not compare these results with tests made using an unlimited cap.

### Metrics

| Metric | Better result |
| --- | --- |
| Average FPS | Higher |
| 1% low FPS | Higher |
| P99 frame time | Lower |
| Frames >= 50 ms | Lower |

Use the median of the 3 runs for each metric.

---

## Raw Adrenaline

### 1.21.11
Build ID: `26.5.1+mc1.21.11.fabric`

### Stationary test

| Run | Average FPS | 1% low FPS | P99 frame time (ms) | Frames >= 50 ms |
| --- | --- | --- | --- | --- |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Breakdown

| Metric | Median |
| --- | ---: |
| Average FPS | — |
| 1% low FPS | — |
| P99 frame time (ms) | — |
| Frames >= 50 ms | — |

---

## Citron

### dev.1.2.0+mc1.21.11.fabric
Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev120mc12111fabric)

### Stationary test

| Run | Average FPS | 1% low FPS | P99 frame time (ms) | Frames >= 50 ms |
| --- | --- | --- | --- | --- |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Breakdown

| Metric | Adrenaline median | Citron median | Difference (%) |
| --- | ---: | ---: | ---: |
| Average FPS | — | — | — |
| 1% low FPS | — | — | — |
| P99 frame time (ms) | — | — | — |
| Frames >= 50 ms | — | — | — |

Difference (%) = ((Citron - Adrenaline) / Adrenaline) × 100. Positive is better for FPS; negative is better for frame time and spike count.

### Movement test (optional)

Use the same saved world, starting position and route. Capture 60 seconds per run. If testing chunk generation, restore a copy of the world from before that route was explored before each run. Keep movement results separate from the stationary test.

Notes: [Fill in]
