# FPS Testing

# Stationary Test

### Method

- Tool: CapFrameX.
- Test the final development build before a release.
- Take 10 captures of 60 seconds each per pack.
- Wait 60 seconds after loading the world.
- Use the same world, scene, settings, and external conditions for both packs.
- Use the same number of valid captures for a final comparison.
- Keep original build IDs alongside the development build identifier for historical results.

### Test setup

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

### Metrics

| Metric | Better result |
| --- | --- |
| Average FPS | Higher |
| 1% low average FPS | Higher |
| P99 Animation Error (ms) | Lower |
| Adaptive STDEV | Lower |

Use the median to compare performance. CV (coefficient of variation) is calculated as sample standard deviation divided by the mean, multiplied by 100%, and describes relative variation between captures.

---

### Adrenaline

Version: `26.5.1+mc1.21.11.fabric`

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

#### Breakdown

| Metric | Median | Difference from Adrenaline | CV |
| --- | ---: | ---: | ---: |
| Average FPS | 127.35 | — | 9.22% |
| 1% low average FPS | 60.05 | — | 22.95% |
| P99 Animation Error (ms) | 3.90 | — | 23.60% |
| Adaptive STDEV | 20.10 | — | 27.31% |

---

### Citron

Version: `1.0.0-dev.3+mc1.21.11.fabric`  
Original build ID: `dev.1.2.0+mc1.21.11.fabric`

| Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: |
| 1 | 130.2 | 57.1 | 5.3 | 26.8 |
| 2 | 122.5 | 57.8 | 4.4 | 17.9 |
| 3 | 91.5 | 43.4 | 5.1 | 11.8 |
| 4 | 97.5 | 46.0 | 4.3 | 11.5 |
| 5 | 128.4 | 61.7 | 3.8 | 22.1 |

#### Breakdown

Citron currently has five captures, compared with ten for the Adrenaline baseline. The comparison is provisional until both packs have the same number of valid captures.

| Metric | Median | Difference from Adrenaline | CV |
| --- | ---: | ---: | ---: |
| Average FPS | 122.50 | -3.81% | 15.94% |
| 1% low average FPS | 57.10 | -4.91% | 15.05% |
| P99 Animation Error (ms) | 4.40 | +12.82% | 13.41% |
| Adaptive STDEV | 17.90 | -10.95% | 36.70% |

Difference (%) = ((Citron median - Adrenaline median) / Adrenaline median) × 100. Positive differences are better for FPS metrics; negative differences are better for Animation Error and Adaptive STDEV. Lower CV means less relative variation between captures.

---

### Citron Initial Release

Version: `1.0.0+mc.1.21.11.fabric`  
Test date: 2026-10-29  
Captures: 22 total (Run 0 is the cold recording; Runs 1–21 are subsequent captures)

The readings below were collected in the same test environment described above. Run 0 is retained in the raw data but excluded from the warm-run summary statistics.

| Time | Max FPS | P99 FPS | P95 FPS | Average FPS | Median FPS | P5 FPS | P1 FPS | 1% low average FPS | 1% low integral FPS | P0.2 FPS | P0.1 FPS | 0.1% low average FPS | 0.1% low integral FPS | Min FPS | P99 Animation Error (ms) | Adaptive STDEV | CPU FPS / 10W | GPU FPS / 10W |
| ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| 16:17:39 | 245.3 | 159.4 | 130.5 | 89.5 | 93.2 | 61.7 | 50.2 | 34.1 | 34 | 33.9 | 21.2 | 13.2 | 9.8 | 7.6 | 15.5 | 19.4 | 81.4 | 0 |
| 16:23:48 | 235.4 | 178.4 | 148.9 | 102.5 | 105.1 | 73.3 | 60.3 | 46 | 50.8 | 46.7 | 37.6 | 19.5 | 12.9 | 12.5 | 11.7 | 22 | 85.41 | 0 |
| 16:27:02 | 268.7 | 175.2 | 148.3 | 103.7 | 106.9 | 75.1 | 61.7 | 44.6 | 51 | 46.4 | 35 | 16.4 | 11.4 | 11.2 | 11.3 | 21.6 | 86.39 | 0 |
| 16:32:11 | 256.1 | 175.3 | 150.1 | 103.2 | 105.4 | 74.5 | 62 | 46.1 | 54.3 | 51 | 36.3 | 17.2 | 13.3 | 11.9 | 11.2 | 22 | 85.98 | 0 |
| 16:36:45 | 238 | 174.9 | 150 | 103.6 | 105.4 | 76.5 | 63.2 | 45 | 53.3 | 50.3 | 31.6 | 15.7 | 12 | 11.7 | 10.5 | 20.8 | 86.33 | 0 |
| 16:42:52 | 251.6 | 177.2 | 152.4 | 106 | 108 | 77.9 | 63.8 | 48.3 | 55.2 | 51.3 | 43 | 19.4 | 13.3 | 11.9 | 10.4 | 21.5 | 88.37 | 0 |
| 16:47:13 | 260.8 | 178.4 | 152.7 | 106.8 | 108.6 | 79.4 | 64.6 | 47.8 | 56.4 | 53.3 | 44.3 | 17.6 | 12.5 | 11.8 | 10.3 | 21.2 | 88.96 | 0 |
| 16:53:37 | 242.2 | 180.7 | 154.5 | 106.8 | 108.8 | 78.5 | 65 | 47.3 | 56.1 | 53.8 | 35.3 | 16.8 | 13 | 10.8 | 10.4 | 21.9 | 88.99 | 0 |
| 16:58:30 | 239.7 | 178 | 151.3 | 105.7 | 108.5 | 76.9 | 63.8 | 46.8 | 55.4 | 52 | 41.4 | 17 | 11.4 | 10.7 | 10.4 | 22 | 88.08 | 0 |
| 17:02:16 | 235.7 | 176.7 | 151.8 | 105.7 | 107.7 | 78.2 | 64 | 47.5 | 55.2 | 52.3 | 41.8 | 17.9 | 13.1 | 12.8 | 10.3 | 21.4 | 88.11 | 0 |
| 17:08:12 | 241.1 | 178.1 | 152.6 | 106.2 | 108.5 | 77.6 | 64 | 47.2 | 55.3 | 52.6 | 33.8 | 17.6 | 12.6 | 9.9 | 10.5 | 21.9 | 88.48 | 0 |
| 17:11:48 | 241.7 | 178.5 | 152.5 | 106.4 | 109.1 | 78.2 | 64.2 | 45.8 | 53.5 | 51 | 39.5 | 15.9 | 11.9 | 11.1 | 10.8 | 21.8 | 88.67 | 0 |
| 17:16:21 | 245.9 | 177.8 | 152.5 | 105.2 | 108.2 | 75.8 | 63.2 | 45.9 | 54.6 | 51.9 | 41 | 16.3 | 12.2 | 11.2 | 10.9 | 22.2 | 87.7 | 0 |
| 17:20:42 | 272.4 | 176.7 | 151.4 | 106.8 | 108.8 | 78.6 | 64.8 | 48.3 | 57.2 | 53.5 | 46 | 17.9 | 12.8 | 11.3 | 10.5 | 21.4 | 0 | 0 |
| 17:25:35 | 234.5 | 177.7 | 151.7 | 106.9 | 108.8 | 79.5 | 65.5 | 47.5 | 56 | 52.9 | 44 | 16.8 | 12.3 | 11.4 | 10 | 21.3 | 82.22 | 0 |
| 17:28:45 | 269.1 | 178.3 | 151 | 105.7 | 108.7 | 78 | 64.3 | 46.6 | 54.2 | 51.4 | 41.6 | 17 | 12.2 | 11.4 | 10.7 | 21.3 | 88.08 | 0 |
| 17:32:31 | 260 | 179 | 153.9 | 106.3 | 109.6 | 76.9 | 64.1 | 47 | 55.4 | 52.4 | 43.9 | 16.9 | 12.2 | 12 | 10.5 | 22.2 | 88.6 | 0 |
| 17:35:41 | 236.5 | 176.9 | 150.5 | 105.6 | 108.1 | 76.6 | 63.5 | 46.9 | 55.8 | 53.8 | 41.2 | 16.9 | 12.2 | 10.7 | 10.6 | 21.4 | 87.99 | 0 |
| 17:38:59 | 274.9 | 181.4 | 154.3 | 106.1 | 109.2 | 77.1 | 63.9 | 48.2 | 57.7 | 55 | 45.4 | 17.8 | 12.8 | 12 | 10.6 | 22.4 | 88.44 | 0 |
| 17:42:15 | 248.9 | 179.9 | 153.7 | 106.3 | 108.3 | 77.9 | 64.6 | 47.8 | 56 | 53.3 | 42.3 | 18 | 13 | 12.3 | 10.4 | 21.8 | 88.56 | 0 |
| 17:45:39 | 248.8 | 179.7 | 154.8 | 108.5 | 111.7 | 79.1 | 65.2 | 48.5 | 57.3 | 54.1 | 42.9 | 17.6 | 13 | 11.3 | 10 | 22.3 | 83.42 | 0 |
| 17:48:47 | 262.5 | 179.5 | 153.9 | 108.2 | 109.9 | 81.1 | 66.3 | 48 | 56.3 | 53.8 | 46.4 | 16.9 | 12.6 | 11.6 | 9.9 | 21.5 | 83.21 | 0 |

#### Breakdown

| Metric | Warm-run median | Difference from Adrenaline | CV |
| --- | ---: | ---: | ---: |
| Average FPS | 106.10 | -16.69% | 1.43% |
| 1% low average FPS | 47.20 | -21.40% | 2.35% |
| P99 Animation Error (ms) | 10.50 | +169.23% | 4.11% |
| Adaptive STDEV | 21.80 | +8.46% | 1.92% |

The warm-run summary uses Runs 1–21. Median differences use the recorded Adrenaline baseline above: 127.35 average FPS, 60.05 1% low average FPS, 3.90 ms P99 Animation Error, and 20.10 Adaptive STDEV. Higher FPS metrics are better; lower Animation Error and Adaptive STDEV are better. CV is sample standard deviation divided by mean, multiplied by 100%.

This comparison is descriptive rather than fully balanced: Citron has 21 warm captures, while the Adrenaline baseline has 10 captures. For a balanced comparison under the stated method, collect 11 additional valid Adrenaline captures or compare equal-sized capture sets. CPU FPS / 10W and GPU FPS / 10W are retained as exported and are not included in this breakdown.

---

# Recreative FPS Test


