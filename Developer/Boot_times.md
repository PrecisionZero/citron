# Boot Time Testing

## Raw Adrenaline

### 1.21.11
Build ID: `26.5.1+mc1.21.11.fabric`

| Boot number | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0² | 51.43 | 07.01 | 58.45 |
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

---

## Citron

### 1.21.11

Adrenaline Build ID: `26.5.1+mc1.21.11.fabric`

Run 0 is the first launch and is excluded from summary statistics.

<details>
  <summary>1.0.0-dev.1+mc1.21.11.fabric</summary>

Refer to: [Development stage](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#100-dev1mc12111fabric)

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
</details>

---

<details>
  <summary>1.0.0-dev.2+mc1.21.11.fabric</summary>

Refer to: [Development stage](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#100-dev2mc12111fabric)

| Boot number | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0² | 39.55 | 18.04 | 57.60 |
| 1 | 30.26 | 13.18 | 43.45 |
| 2 | 33.03 | 14.43 | 47.47 |
| 3 | 31.34 | 14.13 | 45.47 |

##### Breakdown

| Metric | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** | 31.54 | 13.91 | 45.46 |
| **% Difference from Adrenaline** | +1.41% | +9.96% | +3.93% |
| **% Difference from baseline build⁵** | -4.74% | -4.00% | -4.50% |
| CV⁴ | 4.43% | 4.69% | 4.42% |
| Range | 30.26 - 33.03 | 13.18 - 14.43 | 43.45 - 47.47 |
</details>

---

<details>
  <summary>1.0.0-dev.3+mc1.21.11.fabric</summary>

Refer to: [Development stage](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#100-dev3mc12111fabric)

| Boot number | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0² | 39.66 | 17.98 | 57.65 |
| 1 | 30.35 | 12.41 | 42.77 |
| 2 | 31.66 | 14.78 | 46.45 |
| 3 | 33.70 | 13.70 | 47.40 |
| 4 | 32.41 | 14.10 | 46.51 |
| 5 | 32.19 | 13.61 | 45.80 |

##### Breakdown

| Metric | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** | 32.06 | 13.72 | 45.79 |
| **% Difference from Adrenaline** | +3.09% | +8.46% | +4.69% |
| **% Difference from baseline build⁵** | -3.17% | -5.31% | -3.80% |
| CV⁴ | 3.79% | 6.31% | 3.89% |
| Range | 30.35 - 33.70 | 12.41 - 14.78 | 42.77 - 47.40 |
</details>

---

<details>
  <summary>* 1.0.0-dev.9+mc1.21.11.fabric</summary>

Refer to: [Development stage](https://github.com/PrecisionZero/citron/blob/main/Developer/Development_stage.md#100-dev3mc12111fabric)

| Boot number | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| 0² | 43.15 | 20.80 | 1:03.95 |
| 1 | 37.34 | 17.02 | 54.45 |
| 2 | 34.12 | 16.39 | 50.52 |
| 3 | 34.50 | 17.16 | 51.66 |

##### Breakdown

| Metric | Show time¹ | Load time | Total load time |
| ----------- | ---------- | --------- | --------------- |
| **Average** | 32.06 | 13.72 | 45.79 |
| **% Difference from Adrenaline** | +3.09% | +8.46% | +4.69% |
| **% Difference from baseline build⁵** | -3.17% | -5.31% | -3.80% |
| CV⁴ | 3.79% | 6.31% | 3.89% |
| Range | 30.35 - 33.70 | 12.41 - 14.78 | 42.77 - 47.40 |
</details>

---

¹ Time taken for the window to appear.  
² First launch; excluded from summary statistics.  
³ Standard deviation.  
⁴ Coefficient of variation.  
⁵ Difference from the baseline Citron build, `1.0.0-dev.1+mc1.21.11.fabric`.

The number of runs differs between versions, so the recorded differences should be treated as descriptive rather than a fully balanced comparison.
