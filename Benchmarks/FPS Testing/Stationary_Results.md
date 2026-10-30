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

## Statistical breakdown

SD and variance are sample statistics. CV = SD / mean × 100%.

| Metric | Adrenaline mean | Median | Min–max | SD | Variance | CV | Citron mean | Median | Min–max | SD | Variance | CV |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Average FPS | 125.97 | 127.35 | 107.0–138.7 | 11.62 | 134.94 | 9.2% | 114.02 | 122.50 | 91.5–130.2 | 18.17 | 330.14 | 15.9% |
| 1% low average FPS | 54.09 | 60.05 | 26.7–65.2 | 12.41 | 154.12 | 23.0% | 53.20 | 57.10 | 43.4–61.7 | 8.01 | 64.13 | 15.1% |
| P99 Animation Error (ms) | 4.11 | 3.90 | 3.0–5.4 | 0.97 | 0.94 | 23.6% | 4.58 | 4.40 | 3.8–5.3 | 0.61 | 0.38 | 13.4% |
| Adaptive STDEV | 19.60 | 20.10 | 11.9–26.9 | 5.35 | 28.66 | 27.3% | 18.02 | 17.90 | 11.5–26.8 | 6.61 | 43.74 | 36.7% |

## Adrenaline comparison

Percentage change = (Citron median − Adrenaline median) / Adrenaline median × 100%. Higher is better for FPS metrics; lower is better for Animation Error and Adaptive STDEV.

| Metric | Adrenaline median | Citron dev.3 median | Median change | Better direction |
|---|---:|---:|---:|---|
| Average FPS | 127.35 | 122.50 | -3.8% | Higher |
| 1% low average FPS | 60.05 | 57.10 | -4.9% | Higher |
| P99 Animation Error (ms) | 3.90 | 4.40 | +12.8% | Lower |
| Adaptive STDEV | 20.10 | 17.90 | -10.9% | Lower |

## Notes

- The capture counts are unequal (10 Adrenaline, 5 Citron), so the comparison is descriptive.
- Average FPS and 1% low medians are lower for Citron dev.3.
- P99 Animation Error median is higher for Citron dev.3.
- Adaptive STDEV median is lower for Citron dev.3, while its across-run CV is higher.
- Do not treat this historical dev.3 dataset as the initial-release benchmark.
