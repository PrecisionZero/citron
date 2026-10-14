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

| Metric | Purpose | Better result |
| --- | --- | --- |
| Average FPS | Overall performance | Higher |
| 1% low average FPS | Performance during slower frames | Higher |
| P99 Animation Error (ms) | Animation smoothness error | Lower |
| Adaptive STDEV | Frame-time consistency within a capture | Lower |

For each metric, use the median for the comparison. SD and CV below show variation between captures, not frame-to-frame variation within a capture.

---

## Raw Adrenaline

### 1.21.11
Build ID: `26.5.1+mc1.21.11.fabric`

### Stationary test

10 captures recorded on 2026-10-14.

| Run | Time | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | --- | ---: | ---: | ---: | ---: |
| 1 | 14:20:40 | 138.7 | 60.2 | 5.2 | 26.9 |
| 2 | 14:22:22 | 88.3 | 34.6 | 7.9 | 18.1 |
| 3 | 14:23:56 | 136.1 | 60.2 | 4.7 | 23.7 |
| 4 | 14:25:12 | 89.6 | 27.4 | 9.0 | 18.5 |
| 5 | 14:27:12 | 129.1 | 46.9 | 5.4 | 22.9 |
| 6 | 14:29:46 | 138.3 | 64.0 | 4.2 | 20.7 |
| 7 | 14:30:55 | 96.4 | 26.8 | 8.3 | 20.5 |
| 8 | 14:35:33 | 125.6 | 56.2 | 5.3 | 26.2 |
| 9 | 14:39:45 | 97.4 | 38.9 | 7.4 | 23.7 |
| 10 | 14:41:00 | 84.0 | 31.1 | 7.9 | 18.0 |

#### Breakdown

| Metric | Mean | Median | SD | CV | Range |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | 112.35 | 111.50 | 23.01 | 20.48% | 84.0–138.7 |
| 1% low average FPS | 44.63 | 42.90 | 14.65 | 32.81% | 26.8–64.0 |
| P99 Animation Error (ms) | 6.53 | 6.40 | 1.73 | 26.56% | 4.2–9.0 |
| Adaptive STDEV | 21.92 | 21.80 | 3.26 | 14.87% | 18.0–26.9 |

SD is the sample standard deviation. CV = SD / mean × 100%. A lower CV means the repeated captures were more consistent with each other.

---

## Citron

### dev.1.2.0+mc1.21.11.fabric
Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev120mc12111fabric)

### Stationary test

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Breakdown

| Metric | Mean | Median | SD | CV | Range |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | — | — | — | — | — |
| 1% low average FPS | — | — | — | — | — |
| P99 Animation Error (ms) | — | — | — | — | — |
| Adaptive STDEV | — | — | — | — | — |

#### Comparison

| Metric | Adrenaline median | Citron median | Difference (%) | Adrenaline CV | Citron CV |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | 111.50 | — | — | 20.48% | — |
| 1% low average FPS | 42.90 | — | — | 32.81% | — |
| P99 Animation Error (ms) | 6.40 | — | — | 26.56% | — |
| Adaptive STDEV | 21.80 | — | — | 14.87% | — |

Difference (%) = ((Citron median - Adrenaline median) / Adrenaline median) × 100. Positive is better for FPS; negative is better for Animation Error and Adaptive STDEV. Lower CV means more repeatable results between runs.

### Movement test (optional)

Use the same saved world, starting position and route. Capture 60 seconds per run. If testing chunk generation, restore a copy of the world from before that route was explored before each run. Keep movement results separate from the stationary test.

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

Notes: [Fill in]
