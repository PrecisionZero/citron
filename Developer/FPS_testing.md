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
| P99 \|Animation Error\| (ms) | Lower |
| Adaptive STDEV | Lower |

Use the median of the runs for each metric.

---

## Raw Adrenaline

### 1.21.11
Build ID: `26.5.1+mc1.21.11.fabric`

### Stationary test

10 captures recorded on 2026-10-14. The table contains only the metrics used for comparison.

| Metric | Median |
| --- | ---: |
| Average FPS | 111.50 |
| 1% low average FPS | 42.90 |
| P99 \|Animation Error\| (ms) | 6.40 |
| Adaptive STDEV | 21.80 |

---

## Citron

### dev.1.2.0+mc1.21.11.fabric
Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev120mc12111fabric)

### Stationary test

| Run | Average FPS | 1% low average FPS | P99 \|Animation Error\| (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

#### Breakdown

| Metric | Adrenaline median | Citron median | Difference (%) |
| --- | ---: | ---: | ---: |
| Average FPS | 111.50 | — | — |
| 1% low average FPS | 42.90 | — | — |
| P99 \|Animation Error\| (ms) | 6.40 | — | — |
| Adaptive STDEV | 21.80 | — | — |

Difference (%) = ((Citron - Adrenaline) / Adrenaline) × 100. Positive is better for FPS; negative is better for animation error and Adaptive STDEV.

### Movement test (optional)

Use the same saved world, starting position and route. Capture 60 seconds per run. If testing chunk generation, restore a copy of the world from before that route was explored before each run. Keep movement results separate from the stationary test.

Notes: [Fill in]
