# Stationary Benchmark Results

## Test identification

| Item | Value |
|---|---|
| Minecraft | 1.21.11 |
| Render distance | 12 chunks |
| Simulation distance | 8 chunks |
| Adrenaline | `26.5.1+mc1.21.11.fabric` |
| Citron | `1.0.0-dev.3+mc1.21.11.fabric` |
| Original Citron build | `dev.1.2.0+mc1.21.11.fabric` |
| Captures | 10 Adrenaline; 5 Citron |

This is the historical stationary comparison. It is not a stationary test of the initial release `1.0.0`; the initial-release dataset is the movement benchmark.

## Raw captures

| Pack | Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
|---|---:|---:|---:|---:|---:|
| Adrenaline | 1 | 138.7 | 60.2 | 5.2 | 26.9 |
| Adrenaline | 2 | 136.1 | 60.2 | 4.7 | 23.7 |
| Adrenaline | 3 | 129.1 | 46.9 | 5.4 | 22.9 |
| Adrenaline | 4 | 138.3 | 64.0 | 4.2 | 20.7 |
| Adrenaline | 5 | 125.6 | 56.2 | 5.3 | 26.2 |
| Adrenaline | 6 | 134.9 | 65.2 | 3.6 | 19.5 |
| Adrenaline | 7 | 123.2 | 61.5 | 3.0 | 15.7 |
| Adrenaline | 8 | 107.0 | 26.7 | 3.4 | 14.7 |
| Adrenaline | 9 | 116.9 | 59.9 | 3.1 | 13.8 |
| Adrenaline | 10 | 109.9 | 40.1 | 3.2 | 11.9 |
| Citron dev.3 | 1 | 130.2 | 57.1 | 5.3 | 26.8 |
| Citron dev.3 | 2 | 122.5 | 57.8 | 4.4 | 17.9 |
| Citron dev.3 | 3 | 91.5 | 43.4 | 5.1 | 11.8 |
| Citron dev.3 | 4 | 97.5 | 46.0 | 4.3 | 11.5 |
| Citron dev.3 | 5 | 128.4 | 61.7 | 3.8 | 22.1 |

## Mean and CV breakdown

Means are averages across the available captures. CV is the sample standard deviation divided by the mean, expressed as a percentage. Lower CV means less relative variation between separate captures.

| Metric | Adrenaline mean | Adrenaline CV | Citron dev.3 mean | Citron dev.3 CV | Change in mean |
|---|---:|---:|---:|---:|---:|
| Average FPS | 125.97 | 9.2% | 114.02 | 15.9% | -9.5% |
| 1% low average FPS | 54.09 | 23.0% | 53.20 | 15.1% | -1.6% |
| P99 Animation Error (ms) | 4.11 | 23.6% | 4.58 | 13.4% | +11.4% |
| Adaptive STDEV | 19.60 | 27.3% | 18.02 | 36.7% | -8.1% |

## Mean comparison

Percentage change = (Citron dev.3 mean − Adrenaline mean) / Adrenaline mean × 100%. The direction of improvement depends on the metric.

- **Overall speed:** Citron dev.3 averaged **114.0 FPS**, about **9.5% lower** than Adrenaline's 126.0 FPS. Its CV was **15.9%**, compared with **9.2%** for Adrenaline, so Citron's average FPS varied more between captures.
- **1% lows:** Citron averaged **53.2 FPS**, about **1.6% lower**. Its CV was lower, so those low-frame readings were more repeatable between captures.
- **Animation error:** Citron's mean P99 Animation Error was **4.58 ms**, **11.4% higher**. Lower is better, so this result favoured Adrenaline.
- **Adaptive STDEV:** Citron's mean was **18.02**, **8.1% lower** than Adrenaline's. Its CV was higher, so the result varied more between captures.

**In simple terms:** This older dev.3 stationary test showed slightly lower average FPS and 1% lows for Citron, with a higher animation-error reading. Citron's results varied less on 1% lows and animation error, but more on average FPS and Adaptive STDEV. This is not the initial-release benchmark.

## Notes

- The capture counts are unequal (10 Adrenaline, 5 Citron), so the comparison is descriptive.
- Mean Average FPS and mean 1% low average FPS are lower for Citron dev.3.
- Mean P99 Animation Error is higher for Citron dev.3; lower is better.
- Mean Adaptive STDEV is lower for Citron dev.3, but its CV is higher, indicating greater relative variation between captures.
- Do not treat this historical dev.3 dataset as the initial-release benchmark.
