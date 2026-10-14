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
| Test scene | Same position and direction near the village |
| Render distance | 12 chunks |
| Simulation distance | 8 chunks |
| Max framerate | Unlimited |
| Mipmap levels | 4 |
| RAM allocated | 4096MB |

### Hardware settings

| Component | Value |
| --- | --- |
| CPU | Intel i3-8145u |
| GPU | Intel UHD Graphics 620 |
| RAM | 12 GB |

All external factors like the seed, memory, Windows power plan, apps open, and plug-in status remain the same throughout.

### Metrics

| Metric | Better result |
| --- | --- |
| Average FPS | Higher |
| 1% low average FPS | Higher |
| P99 |Animation Error| (ms) | Lower |
| Adaptive STDEV | Lower |

Use the median of the runs for each metric.

---

## Raw Adrenaline

### 1.21.11
Build ID: `26.5.1+mc1.21.11.fabric`

### Stationary test

| Run | Time | Max FPS | P99 FPS | P95 FPS | Average FPS | Median FPS | P5 FPS | P1 FPS |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | 14:20:40 | 343.2 | 246.8 | 188.4 | 138.7 | 142.7 | 104.8 | 82.1 |
| 2 | 14:22:22 | 284.6 | 176.0 | 149.5 | 88.3 | 91.1 | 57.9 | 50.9 |
| 3 | 14:23:56 | 325.4 | 212.8 | 180.0 | 136.1 | 138.8 | 108.3 | 83.3 |
| 4 | 14:25:12 | 209.5 | 155.9 | 128.4 | 89.6 | 93.7 | 64.5 | 49.4 |
| 5 | 14:27:12 | 313.2 | 208.3 | 177.2 | 129.1 | 136.6 | 84.4 | 63.1 |
| 6 | 14:29:46 | 344.2 | 199.9 | 177.3 | 138.3 | 140.7 | 111.3 | 87.4 |
| 7 | 14:30:55 | 289.1 | 183.0 | 156.2 | 96.4 | 99.0 | 64.5 | 52.6 |
| 8 | 14:35:33 | 296.2 | 215.9 | 180.2 | 125.6 | 128.9 | 85.3 | 77.8 |
| 9 | 14:39:45 | 239.0 | 195.1 | 168.7 | 97.4 | 101.2 | 59.8 | 51.2 |
| 10 | 14:41:00 | 174.2 | 133.8 | 119.8 | 84.0 | 88.8 | 58.4 | 52.8 |

| Run | 1% low average FPS | 1% low integral FPS | P0.2 FPS | P0.1 FPS | 0.1% low average FPS | 0.1% low integral FPS | Min FPS |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | 60.2 | 73.7 | 72.0 | 64.0 | 19.4 | 5.9 | 5.9 |
| 2 | 34.6 | 33.0 | 34.6 | 19.4 | 12.5 | 5.9 | 5.9 |
| 3 | 60.2 | 74.6 | 69.9 | 52.3 | 20.3 | 6.8 | 6.8 |
| 4 | 27.4 | 16.3 | 26.2 | 18.3 | 7.5 | 3.4 | 3.4 |
| 5 | 46.9 | 49.9 | 49.5 | 39.7 | 19.3 | 6.2 | 6.2 |
| 6 | 64.0 | 78.9 | 71.9 | 56.5 | 22.4 | 6.5 | 6.5 |
| 7 | 26.8 | 5.1 | 27.6 | 19.3 | 6.8 | 2.3 | 2.3 |
| 8 | 56.2 | 73.1 | 70.4 | 57.3 | 16.8 | 5.6 | 5.6 |
| 9 | 38.9 | 46.2 | 45.8 | 35.4 | 14.3 | 5.1 | 5.1 |
| 10 | 31.1 | 22.1 | 31.3 | 20.4 | 8.9 | 3.1 | 3.1 |

| Run | P99 |Animation Error| (ms) | Adaptive STDEV | CPU FPS / 10W | GPU FPS / 10W |
| --- | ---: | ---: | ---: | ---: |
| 1 | 5.2 | 26.9 | 92.45 | 0 |
| 2 | 7.9 | 18.1 | 110.32 | 0 |
| 3 | 4.7 | 23.7 | 90.74 | 0 |
| 4 | 9.0 | 18.5 | 128.04 | 0 |
| 5 | 5.4 | 22.9 | 92.22 | 0 |
| 6 | 4.2 | 20.7 | 86.46 | 0 |
| 7 | 8.3 | 20.5 | 120.45 | 0 |
| 8 | 5.3 | 26.2 | 83.72 | 0 |
| 9 | 7.4 | 23.7 | 97.43 | 0 |
| 10 | 7.9 | 18.0 | 119.97 | 0 |

#### Breakdown

| Metric | Median |
| --- | ---: |
| Max FPS | 292.65 |
| P99 FPS | 197.50 |
| P95 FPS | 172.95 |
| Average FPS | 111.50 |
| Median FPS | 115.05 |
| P5 FPS | 74.45 |
| P1 FPS | 57.95 |
| 1% low average FPS | 42.90 |
| 1% low integral FPS | 48.05 |
| P0.2 FPS | 47.65 |
| P0.1 FPS | 37.55 |
| 0.1% low average FPS | 15.55 |
| 0.1% low integral FPS | 5.75 |
| Min FPS | 5.75 |
| P99 |Animation Error| (ms) | 6.40 |
| Adaptive STDEV | 21.80 |
| CPU FPS / 10W | 94.94 |
| GPU FPS / 10W | 0 |

P99 frame time and frames >= 50 ms were not included in the supplied export.

---

## Citron

### dev.1.2.0+mc1.21.11.fabric
Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev120mc12111fabric)

### Stationary test

| Run | Average FPS | 1% low average FPS | P99 |Animation Error| (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Breakdown

| Metric | Adrenaline median | Citron median | Difference (%) |
| --- | ---: | ---: | ---: |
| Average FPS | 111.50 | — | — |
| 1% low average FPS | 42.90 | — | — |
| P99 |Animation Error| (ms) | 6.40 | — | — |
| Adaptive STDEV | 21.80 | — | — |

Difference (%) = ((Citron - Adrenaline) / Adrenaline) × 100. Positive is better for FPS; negative is better for animation error and Adaptive STDEV.

### Movement test (optional)

Use the same saved world, starting position and route. Capture 60 seconds per run. If testing chunk generation, restore a copy of the world from before that route was explored before each run. Keep movement results separate from the stationary test.

Notes: [Fill in]
