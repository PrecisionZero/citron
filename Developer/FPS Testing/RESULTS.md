# Adrenaline

- **Date:** 2026-10-27
- **Tool:** CapFrameX
- **Method:** As explained in [METHOD.md](https://github.com/PrecisionZero/citron/blob/main/Developer/FPS%20Testing/METHOD.md)
- **Runs:** 20 recorded + 1 cold boot (excluded)

## Result

| Metric | Mean (Runs 1-20) | Std Dev | Variation (CV) | Steady state (Runs 11-20) |
|---|---|---|---|---|
| Average FPS | 128.2 | 6.8 | 5.3% | **124.0** |
| Median FPS | 140.3 | 4.7 | 3.3% | **137.6** |
| 1% Low | 47.7 | 7.8 | 16.3% | **44.4** |
| 0.1% Low | 16.9 | 4.1 | 24.0% | **15.6** |

**Use the steady-state column as the reference baseline.** Variation in average FPS drops from 5.3% to 2.4% once the session settles.

## Findings

- **Drift:** average FPS fell from 136.3 (Runs 1-5) to 122.1 (Runs 16-20), about -10.4%, then flattened. Likely thermal throttling or heap/GC settling.
- **Stutter:** median (140) sits well above average (128), and the 0.1% low is about 13% of average, so a few long frames drag performance down.
- **Outliers:** Runs 1 and 2 have unusually high P1 and 1% lows and should be treated as unreliable.
- **Cold boot:** Run 0 (134.3 avg) was not slower than later runs.
- **Comparing instances:** only trust differences larger than about 3% on median FPS and 1% low.

<details>
<summary>Per-run data</summary>

| Run | Avg FPS | Median FPS | P1 FPS | 1% Low | 0.1% Low | Min FPS |
|---|---|---|---|---|---|---|
| 0 (cold) | 134.3 | 142.2 | 62.3 | 43.1 | 17.1 | 4.4 |
| 1 | 146.4 | 149.4 | 89.0 | 65.7 | 26.0 | 6.5 |
| 2 | 141.4 | 142.6 | 100.1 | 71.0 | 24.8 | 6.0 |
| 3 | 136.3 | 145.0 | 74.4 | 46.8 | 13.8 | 4.0 |
| 4 | 129.9 | 144.3 | 65.1 | 41.0 | 11.8 | 1.7 |
| 5 | 127.6 | 140.3 | 67.2 | 47.4 | 17.7 | 5.8 |
| 6 | 129.3 | 143.4 | 63.9 | 44.1 | 14.9 | 2.8 |
| 7 | 127.4 | 142.5 | 66.3 | 48.0 | 17.8 | 5.4 |
| 8 | 128.2 | 143.6 | 64.6 | 46.7 | 16.9 | 5.1 |
| 9 | 124.2 | 134.5 | 66.7 | 45.5 | 15.4 | 5.2 |
| 10 | 133.2 | 143.9 | 70.0 | 52.7 | 23.0 | 7.7 |
| 11 | 127.4 | 141.2 | 64.5 | 45.3 | 15.9 | 3.1 |
| 12 | 126.6 | 141.9 | 64.0 | 46.2 | 17.4 | 5.3 |
| 13 | 121.6 | 133.3 | 65.8 | 43.9 | 14.7 | 5.0 |
| 14 | 129.5 | 141.9 | 68.9 | 50.7 | 21.6 | 7.5 |
| 15 | 123.8 | 140.2 | 64.8 | 41.6 | 12.3 | 3.3 |
| 16 | 123.4 | 138.4 | 65.4 | 44.3 | 15.9 | 5.3 |
| 17 | 120.2 | 129.9 | 64.5 | 45.2 | 16.3 | 4.7 |
| 18 | 122.0 | 135.8 | 62.1 | 39.6 | 11.4 | 3.0 |
| 19 | 122.8 | 137.1 | 64.3 | 43.2 | 14.8 | 3.1 |
| 20 | 122.2 | 136.4 | 65.3 | 44.3 | 15.3 | 2.8 |

</details>

## Limitations

Results are specific to this hardware, version and route. Fixed noon and clear weather mean night, rain and shaders are not covered, and NoAI entities exclude AI and pathfinding cost. The full method is in [METHOD.md](METHOD.md).
