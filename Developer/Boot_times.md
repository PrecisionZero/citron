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
⁴ Relative Variation


## Citron 
### 1.21.11
Adrenaline Build ID: `26.5.1+mc1.21.11.fabric`

<details>
  <summary>dev.1.0.0+mc1.21.11.fabric</summary>
  
Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev100mc12111fabric)

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
⁴ Relative Variation
</details>

---

<details>
  <summary>dev.1.1.0+mc1.21.11.fabric</summary>
  
  Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev110mc12111fabric)

| Boot number | Show time | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0 | 39.55 | 18.04 | 57.60 |
| 1 | 30.26 | 13.18 | 43.45 |
| 2 | 33.03 | 14.43 | 47.47 |
| 3 | 31.34 | 14.13 | 45.47 |

##### Breakdown

| Metric | Show time | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** | 31.54 | 13.91 | 45.46 |
| **% Difference from Adrenaline** | +1.41% | +9.96% | +3.93% |
| **% Difference from Citron⁵** | -4.74% | -4.00% | -4.50% |
| CV | 4.43% | 4.69% | 4.42% |
| Range | 30.26 - 33.03 | 13.18 - 14.43 | 43.45 - 47.47 |

⁵ The difference from the most recent Major Citron version, being 1.0.0, 2.0.0, excluding 1.1.0, 1.2.0
</details>

---

### dev.1.2.0+mc1.21.11.fabric

Refer to: [Version page](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#dev120mc12111fabric)

| Boot number | Show time | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0 | 39.66 | 17.98 | 57.65 |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |



##### Breakdown

| Metric | Show time | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** |  |  |  |
| **% Difference from Adrenaline** |  |  |  |
| **% Difference from Citron** |  |  |  |
| CV |  |  |  |
| Range |  |  |  |
