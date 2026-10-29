# Stationary Results

Setup: Render distance 12 chunks; simulation distance 8 chunks.  
Adrenaline: `26.5.1+mc1.21.11.fabric`  
Citron: `1.0.0-dev.3+mc1.21.11.fabric` (`dev.1.2.0+mc1.21.11.fabric`)  
Captures: 10 Adrenaline; 5 Citron.

| Pack | Run | Average FPS | 1% low average FPS | P99 Animation Error (ms) | Adaptive STDEV |
| --- | ---: | ---: | ---: | ---: | ---: |
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

## Summary

| Metric | Adrenaline median | Adrenaline variance | Citron median | Citron variance | Median difference |
| --- | ---: | ---: | ---: | ---: | ---: |
| Average FPS | 127.35 | 134.9357 | 122.50 | 330.1370 | -3.81% |
| 1% low average FPS | 60.05 | 154.1166 | 57.10 | 64.1250 | -4.91% |
| P99 Animation Error (ms) | 3.90 | 0.9410 | 4.40 | 0.3770 | +12.82% |
| Adaptive STDEV | 20.10 | 28.6578 | 17.90 | 43.7370 | -10.95% |

The comparison is provisional because the capture counts differ.
