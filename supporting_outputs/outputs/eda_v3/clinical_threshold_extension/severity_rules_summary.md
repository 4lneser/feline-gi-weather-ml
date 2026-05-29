# Severity Rules Summary (Clinical Threshold Extension)

## Setup
- Environmental numeric (kept): 31
- Environmental categorical: 5
- Consequents: severity flags only (clinical threshold states).

## Baseline Prevalence Per Severity Marker
| severity_marker | baseline_prevalence |
| --- | --- |
| BUN_increased | 0.3841 |
| albumin_low | 0.2603 |
| creatinine_increased | 0.2921 |
| leukocyte_increased | 0.1619 |
| lymphocyte_increased | 0.0667 |
| neutrophil_increased | 0.2159 |

## Rule Count Per Severity Marker
| severity_marker | n_rules |
| --- | --- |
| BUN_increased | 10 |
| albumin_low | 10 |
| creatinine_increased | 10 |
| neutrophil_increased | 10 |
| leukocyte_increased | 6 |

## Top 3 Strongest Rules Per Marker
### BUN_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| precipitation_hours_mean_7d_low, precipitation_hours_peak_14d_low, surface_pressure_max_day1_high | 0.0635 | 0.7692 | 2.0025 | 0.3841 |
| precipitation_hours_peak_14d_low, precipitation_sum_mean_7d_low, surface_pressure_max_day1_high | 0.0571 | 0.7500 | 1.9525 | 0.3841 |
| precipitation_hours_mean_7d_low, precipitation_hours_peak_14d_low, surface_pressure_max_mean_13d_high | 0.0635 | 0.7407 | 1.9284 | 0.3841 |
### albumin_low
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| surface_pressure_max_day1_low, surface_pressure_max_mean_13d_low | 0.0571 | 0.3750 | 1.4405 | 0.2603 |
| snowfall_sum_mean_13d_low, wind_direction_10m_dominant_peak_7d_low | 0.0508 | 0.3556 | 1.3659 | 0.2603 |
| surface_pressure_max_mean_13d_low | 0.0889 | 0.3544 | 1.3615 | 0.2603 |
### creatinine_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| precipitation_hours_peak_14d_low, precipitation_sum_mean_13d_low, precipitation_sum_mean_7d_low | 0.0540 | 0.4250 | 1.4552 | 0.2921 |
| precipitation_hours_mean_13d_low, precipitation_hours_peak_14d_low, precipitation_sum_mean_7d_low | 0.0540 | 0.4146 | 1.4197 | 0.2921 |
| precipitation_hours_mean_13d_high, precipitation_hours_mean_7d_high, precipitation_sum_mean_7d_high | 0.0508 | 0.4103 | 1.4047 | 0.2921 |
### leukocyte_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| precipitation_hours_mean_7d_low, snowfall_sum_mean_13d_low | 0.0508 | 0.2462 | 1.5204 | 0.1619 |
| surface_pressure_max_mean_13d_low | 0.0571 | 0.2278 | 1.4073 | 0.1619 |
| daylight_duration_day1_high | 0.0508 | 0.2000 | 1.2353 | 0.1619 |
### lymphocyte_increased
- No rules met thresholds.
### neutrophil_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| moon_near_new | 0.0571 | 0.4091 | 1.8951 | 0.2159 |
| snowfall_sum_mean_13d_low, surface_pressure_max_mean_13d_low | 0.0571 | 0.3750 | 1.7371 | 0.2159 |
| precipitation_hours_mean_13d_low, precipitation_hours_mean_7d_low, snowfall_sum_mean_13d_low | 0.0508 | 0.3556 | 1.6471 | 0.2159 |

## Clinical State Coverage
| lab_key | state | count | pct |
| --- | --- | --- | --- |
| albumin | increased | 46 | 14.6032 |
| albumin | lower_limit | 82 | 26.0317 |
| albumin | physiological | 138 | 43.8095 |
| albumin | upper_limit | 49 | 15.5556 |
| bun | increased | 121 | 38.4127 |
| bun | lower_limit | 83 | 26.3492 |
| bun | physiological | 66 | 20.9524 |
| bun | upper_limit | 45 | 14.2857 |
| creatinine | increased | 92 | 29.2063 |
| creatinine | lower_limit | 94 | 29.8413 |
| creatinine | physiological | 65 | 20.6349 |
| creatinine | upper_limit | 64 | 20.3175 |
| hematocrit | increased | 20 | 6.3492 |
| hematocrit | lower_limit | 147 | 46.6667 |
| hematocrit | physiological | 90 | 28.5714 |
| hematocrit | upper_limit | 58 | 18.4127 |
| leukocyte | increased | 51 | 16.1905 |
| leukocyte | lower_limit | 98 | 31.1111 |
| leukocyte | physiological | 125 | 39.6825 |
| leukocyte | upper_limit | 41 | 13.0159 |
| lymphocyte | increased | 21 | 6.6667 |
| lymphocyte | lower_limit | 242 | 76.8254 |
| lymphocyte | physiological | 37 | 11.7460 |
| lymphocyte | upper_limit | 15 | 4.7619 |
| neutrophil | increased | 68 | 21.5873 |
| neutrophil | lower_limit | 102 | 32.3810 |
| neutrophil | physiological | 113 | 35.8730 |
| neutrophil | upper_limit | 32 | 10.1587 |
| serum_cl | increased | 87 | 27.6190 |
| serum_cl | lower_limit | 60 | 19.0476 |
| serum_cl | physiological | 55 | 17.4603 |
| serum_cl | upper_limit | 113 | 35.8730 |
| serum_k | increased | 18 | 5.7143 |
| serum_k | lower_limit | 162 | 51.4286 |
| serum_k | physiological | 107 | 33.9683 |
| serum_k | upper_limit | 28 | 8.8889 |
| serum_na | increased | 13 | 4.1270 |
| serum_na | lower_limit | 148 | 46.9841 |
| serum_na | physiological | 110 | 34.9206 |
| serum_na | upper_limit | 44 | 13.9683 |
| total_protein | increased | 67 | 21.2698 |
| total_protein | lower_limit | 64 | 20.3175 |
| total_protein | physiological | 63 | 20.0000 |
| total_protein | upper_limit | 121 | 38.4127 |

## Note
- If a severity marker has zero qualifying rules, thresholds were still applied but no association passed filters.