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
| Metrics | Average FPS, 1% low average FPS, P99 Animation Error, Adaptive STDEV |

This is the earlier stationary dataset. It is not a stationary benchmark of the initial release `1.0.0`; the release-build data currently recorded is the movement test.

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

## Breakdown

Values are calculated across all available captures. Variance is sample variance.

| Metric | Adrenaline mean | Median | Range | Variance | Citron dev.3 mean | Median | Range | Variance |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Average FPS | 125.97 | 127.35 | 107.0–138.7 | 134.94 | 114.02 | 122.50 | 91.5–130.2 | 330.14 |
| 1% low average FPS | 54.09 | 60.05 | 26.7–65.2 | 154.12 | 53.20 | 57.10 | 43.4–61.7 | 64.13 |
| P99 Animation Error (ms) | 4.11 | 3.90 | 3.0–5.4 | 0.94 | 4.58 | 4.40 | 3.8–5.3 | 0.38 |
| Adaptive STDEV | 19.60 | 20.10 | 11.9–26.9 | 28.66 | 18.02 | 17.90 | 11.5–26.8 | 43.74 |

## Adrenaline comparison

Percentage change is calculated from the per-run medians: `(Citron median − Adrenaline median) / Adrenaline median × 100`.

| Metric | Adrenaline median | Citron dev.3 median | Change | Better direction |
|---|---:|---:|---:|---|
| Average FPS | 127.35 | 122.50 | -3.8% | Higher |
| 1% low average FPS | 60.05 | 57.10 | -4.9% | Higher |
| P99 Animation Error (ms) | 3.90 | 4.40 | +12.8% | Lower |
| Adaptive STDEV | 20.10 | 17.90 | -10.9% | Lower |

- Average FPS and 1% low average FPS were lower for Citron dev.3.
- P99 Animation Error was higher for Citron dev.3; lower is better.
- Adaptive STDEV was lower for Citron dev.3 by median, but its sample variance across captures was higher.

The comparison is provisional: Adrenaline has 10 captures and Citron dev.3 has 5. The two datasets should not be treated as a release-build comparison.
