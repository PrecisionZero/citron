# FPS Testing

## Method

- Tool: CapFrameX.
- Test only the final version in each major development series.
- Take 5 captures of 60 seconds each.
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

Adrenaline summary values remain blank until the new baseline is recorded. Citron values are calculated from the five captures above.

| Metric | Adrenaline median | Adrenaline variance | Citron median | Citron variance | Difference (%) |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | — | — | 122.50 | 330.14 | — |
| 1% low average FPS | — | — | 57.10 | 64.13 | — |
| P99 Animation Error (ms) | — | — | 4.40 | 0.38 | — |
| Adaptive STDEV | — | — | 17.90 | 43.74 | — |

Difference (%) = ((Citron median - Adrenaline median) / Adrenaline median) × 100. Higher FPS metrics are better; lower error and Adaptive STDEV are better. Lower variance means more consistent captures.
