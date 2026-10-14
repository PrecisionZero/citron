# FPS Testing

## Method

- Tool: CapFrameX.
- Test only the final version in each major development series.
- Take 10 captures of 60 seconds each per pack.
- Wait 60 seconds after loading the world.
- Use the same world, scene, settings, and external conditions for both packs.
- Use the same number of valid captures for a final comparison.

## Test setup

| Item | Value |
| --- | --- |
| World seed | `5872972574357925067` |
| Scene | Fixed position and direction near the village |
| Render distance | 12 chunks |
| Simulation distance | 8 chunks |
| Max framerate | Unlimited |
| Mipmap levels | 4 |
| Allocated RAM | 4096 MB |
| CPU | Intel Core i3-8145U |
| GPU | Intel UHD Graphics 620 |
| System RAM | 12 GB |

## Metrics

| Metric | Better result |
| --- | --- |
| Average FPS | Higher |
| 1% low average FPS | Higher |
| P99 Animation Error (ms) | Lower |
| Adaptive STDEV | Lower |

Use the median to compare performance and sample variance to compare consistency between captures.

---

## Adrenaline

Version: `26.5.1+mc1.21.11.fabric`

### Stationary test

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | 138.7 | 60.2 | 5.2 | 26.9 |
| 2 | 136.1 | 60.2 | 4.7 | 23.7 |
| 3 | 129.1 | 46.9 | 5.4 | 22.9 |
| 4 | 138.3 | 64.0 | 4.2 | 20.7 |
| 5 | 125.6 | 56.2 | 5.3 | 26.2 |
| 6 | 134.9 | 65.2 | 3.6 | 19.5 |
| 7 | 123.2 | 61.5 | 3.0 | 15.7 |
| 8 | 107.0 | 26.7 | 3.4 | 14.7 |
| 9 | 116.9 | 59.9 | 3.1 | 13.8 |
| 10 | 109.9 | 40.1 | 3.2 | 11.9 |

---

## Citron

Version: `dev.1.2.0+mc1.21.11.fabric`

### Stationary test

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | 130.2 | 57.1 | 5.3 | 26.8 |
| 2 | 122.5 | 57.8 | 4.4 | 17.9 |
| 3 | 91.5 | 43.4 | 5.1 | 11.8 |
| 4 | 97.5 | 46.0 | 4.3 | 11.5 |
| 5 | 128.4 | 61.7 | 3.8 | 22.1 |

---

## Summary and comparison

Adrenaline statistics use 10 captures. Citron statistics currently use 5 captures, so the comparison is provisional until five more Citron captures are recorded under the same conditions.

| Metric | Adrenaline median | Adrenaline variance | Citron median | Citron variance | Difference (%) |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | 127.35 | 134.94 | 122.50 | 330.14 | -3.81% |
| 1% low average FPS | 60.05 | 154.12 | 57.10 | 64.13 | -4.91% |
| P99 Animation Error (ms) | 3.90 | 0.94 | 4.40 | 0.38 | +12.82% |
| Adaptive STDEV | 20.10 | 28.66 | 17.90 | 43.74 | -10.95% |

Difference (%) = ((Citron median - Adrenaline median) / Adrenaline median) × 100. Higher FPS metrics are better; lower error and Adaptive STDEV are better. Lower variance means more consistent captures. Variance is the sample variance across captures.
