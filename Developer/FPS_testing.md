# FPS Testing

## Method

- Tool: CapFrameX.
- Test only the final version in each major development series.
- Take 3 captures of 60 seconds each.
- Wait 60 seconds after loading the world.
- Use the same world, scene, settings, and external conditions for both packs.

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

Use the median to compare performance and variance to compare consistency between captures.

---

## Adrenaline baseline

Version: `26.5.1+mc1.21.11.fabric`

### Captures

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | 138.7 | 60.2 | 5.2 | 26.9 |
| 2 | 88.3 | 34.6 | 7.9 | 18.1 |
| 3 | 136.1 | 60.2 | 4.7 | 23.7 |
| 4 | 89.6 | 27.4 | 9.0 | 18.5 |
| 5 | 129.1 | 46.9 | 5.4 | 22.9 |
| 6 | 138.3 | 64.0 | 4.2 | 20.7 |
| 7 | 96.4 | 26.8 | 8.3 | 20.5 |
| 8 | 125.6 | 56.2 | 5.3 | 26.2 |
| 9 | 97.4 | 38.9 | 7.4 | 23.7 |
| 10 | 84.0 | 31.1 | 7.9 | 18.0 |

---

## Citron

Version: `dev.1.2.0+mc1.21.11.fabric`

### Captures

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | — | — | — | — |
| 2 | — | — | — | — |
| 3 | — | — | — | — |

---

## Comparison

| Metric | Adrenaline median | Adrenaline variance | Citron median | Citron variance | Difference (%) |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | 111.50 | 529.50 | — | — | — |
| 1% low average FPS | 42.90 | 214.48 | — | — | — |
| P99 Animation Error (ms) | 6.40 | 3.01 | — | — | — |
| Adaptive STDEV | 21.80 | 10.62 | — | — | — |

Difference (%) = ((Citron median - Adrenaline median) / Adrenaline median) × 100. Higher FPS metrics are better; lower error and Adaptive STDEV are better. Lower variance means more consistent captures.
