# Testing stage for boot times

## Raw Adrenaline

### 1.21.11
Build ID: `26.5.1+mc1.21.11.fabric`

| Boot number | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0² | 51.43 | 07.01 |58.45 |
| 1 | 30.20 | 13.77 | 43.97 |
| 2 | 31.27 | 12.18 | 43.35 |
| 3 | 32.95 | 12.90 | 45.85 |
| 4 | 29.76 | 12.03 | 41.80 |
| 5 | 29.48 | 12.15 | 41.63 |
| 6 | 29.06 | 11.96 | 41.03 |
| 7 | 31.28 | 12.41 | 43.70 |
| 8 | 33.25 | 13.62 | 46.87 |
| 9 | 32.88 | 12.66 | 45.55 |
| 10 | 30.83 | 12.84 | 43.68 |

#### Breakdown

| Metric | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** | 31.10 | 12.65 | 43.74 |
| Shortest | 29.06 (6) | 11.96 (6) | 41.03 (6) |
| Longest | 33.25 (8) | 13.77 (1) | 46.87 (8) |
| **SD³** | 1.52 | 0.64 | 1.92 |
| **CV⁴** | 4.88% | 5.06% | 4.40% |
| **Range** | 29.06 - 33.25 | 11.96 - 13.77 | 41.03 - 46.87 |

¹ The time taken for the window to show\
² The first boot, not counted for Average or RV\
³ Standard Deviation\
⁴ Relative Variation\


## Citron 
### 1.21.11
Adrenaline Build ID: `26.5.1+mc1.21.11.fabric`

### Dev.1.0.0+mc1.21.11.fabric
Refer to page: [Visit](https://github.com/PrecisionZero/Citron/blob/main/Developer/Development_stage.md#010mc12111fabric)

| Boot number | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0² | 35.55 | 14.13 | 49.69 |
| 1 | 32.56 | 13.12 | 45.69 |
| 2 | 33.50 | 14.53 | 48.03 |
| 3 | 32.22 | 16.14 | 48.36 |
| 4 | 33.65 | 14.47 | 48.12 |
| 5 | 33.60 | 14.21 | 47.81 |

#### Breakdown

| Metric | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** | 33.11 | 14.49 | 47.60 |
| **% Difference from Adrenaline** | +6.46% | +14.55% | +8.82% |
| Shortest | 32.22 (3) | 13.12 (1) | 45.69 (1) |
| Longest | 33.65 (4) | 16.14 (3) | 48.36 (3) |
| **SD³** | 0.67 | 1.08 | 1.09 |
| **CV⁴** | 2.01% | 7.46% | 2.28% |
| **Range** | 32.22 - 33.65 | 13.12 - 16.14 | 45.69 - 48.36 |

¹ The time taken for the window to show\
² The first boot, not counted for Average or RV\
³ Standard Deviation\
⁴ Relative Variation\
