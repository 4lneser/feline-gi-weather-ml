# Severity Rules Summary (Clinical Threshold Extension)

## Setup
- Environmental numeric (kept): 31
- Environmental categorical: 5
- Consequents: severity flags only (clinical threshold states).

## Baseline Prevalence Per Severity Marker
| severity_marker | baseline_prevalence |
| --- | --- |
| BUN_increased | 0.3854 |
| albumin_low | 0.2611 |
| creatinine_increased | 0.2930 |
| leukocyte_increased | 0.1624 |
| lymphocyte_increased | 0.0669 |
| neutrophil_increased | 0.2166 |

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
| precipitation_hours_mean_7d_low, precipitation_hours_peak_14d_low, surface_pressure_max_day1_high | 0.0637 | 0.7692 | 1.9962 | 0.3854 |
| precipitation_hours_peak_14d_low, precipitation_sum_mean_7d_low, surface_pressure_max_day1_high | 0.0573 | 0.7500 | 1.9463 | 0.3854 |
| precipitation_hours_mean_7d_low, precipitation_hours_peak_14d_low, surface_pressure_max_mean_13d_high | 0.0637 | 0.7407 | 1.9223 | 0.3854 |
### albumin_low
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| surface_pressure_max_day1_low, surface_pressure_max_mean_13d_low | 0.0573 | 0.3750 | 1.4360 | 0.2611 |
| snowfall_sum_mean_13d_low, wind_direction_10m_dominant_peak_7d_low | 0.0510 | 0.3556 | 1.3615 | 0.2611 |
| surface_pressure_max_mean_13d_low | 0.0892 | 0.3544 | 1.3572 | 0.2611 |
### creatinine_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| precipitation_hours_peak_14d_low, precipitation_sum_mean_13d_low, precipitation_sum_mean_7d_low | 0.0541 | 0.4250 | 1.4505 | 0.2930 |
| precipitation_hours_mean_13d_low, precipitation_hours_peak_14d_low, precipitation_sum_mean_7d_low | 0.0541 | 0.4146 | 1.4152 | 0.2930 |
| precipitation_hours_mean_13d_high, precipitation_hours_mean_7d_high, precipitation_sum_mean_7d_high | 0.0510 | 0.4103 | 1.4002 | 0.2930 |
### leukocyte_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| precipitation_hours_mean_7d_low, snowfall_sum_mean_13d_low | 0.0510 | 0.2462 | 1.5155 | 0.1624 |
| surface_pressure_max_mean_13d_low | 0.0573 | 0.2278 | 1.4028 | 0.1624 |
| precipitation_sum_day1_high | 0.0510 | 0.2025 | 1.2470 | 0.1624 |
### lymphocyte_increased
- No rules met thresholds.
### neutrophil_increased
| antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- |
| moon_near_new | 0.0573 | 0.4091 | 1.8890 | 0.2166 |
| snowfall_sum_mean_13d_low, surface_pressure_max_mean_13d_low | 0.0573 | 0.3750 | 1.7316 | 0.2166 |
| precipitation_hours_mean_13d_low, precipitation_hours_mean_7d_low, snowfall_sum_mean_13d_low | 0.0510 | 0.3556 | 1.6418 | 0.2166 |

## Clinical State Coverage
| lab_key | state | count | pct |
| --- | --- | --- | --- |
| albumin | increased | 46 | 14.6497 |
| albumin | lower_limit | 82 | 26.1146 |
| albumin | physiological | 137 | 43.6306 |
| albumin | upper_limit | 49 | 15.6051 |
| bun | increased | 121 | 38.5350 |
| bun | lower_limit | 82 | 26.1146 |
| bun | physiological | 66 | 21.0191 |
| bun | upper_limit | 45 | 14.3312 |
| creatinine | increased | 92 | 29.2994 |
| creatinine | lower_limit | 94 | 29.9363 |
| creatinine | physiological | 64 | 20.3822 |
| creatinine | upper_limit | 64 | 20.3822 |
| hematocrit | increased | 20 | 6.3694 |
| hematocrit | lower_limit | 146 | 46.4968 |
| hematocrit | physiological | 90 | 28.6624 |
| hematocrit | upper_limit | 58 | 18.4713 |
| leukocyte | increased | 51 | 16.2420 |
| leukocyte | lower_limit | 98 | 31.2102 |
| leukocyte | physiological | 124 | 39.4904 |
| leukocyte | upper_limit | 41 | 13.0573 |
| lymphocyte | increased | 21 | 6.6879 |
| lymphocyte | lower_limit | 241 | 76.7516 |
| lymphocyte | physiological | 37 | 11.7834 |
| lymphocyte | upper_limit | 15 | 4.7771 |
| neutrophil | increased | 68 | 21.6561 |
| neutrophil | lower_limit | 102 | 32.4841 |
| neutrophil | physiological | 113 | 35.9873 |
| neutrophil | upper_limit | 31 | 9.8726 |
| serum_cl | increased | 87 | 27.7070 |
| serum_cl | lower_limit | 60 | 19.1083 |
| serum_cl | physiological | 54 | 17.1975 |
| serum_cl | upper_limit | 113 | 35.9873 |
| serum_k | increased | 18 | 5.7325 |
| serum_k | lower_limit | 161 | 51.2739 |
| serum_k | physiological | 107 | 34.0764 |
| serum_k | upper_limit | 28 | 8.9172 |
| serum_na | increased | 13 | 4.1401 |
| serum_na | lower_limit | 147 | 46.8153 |
| serum_na | physiological | 110 | 35.0318 |
| serum_na | upper_limit | 44 | 14.0127 |
| total_protein | increased | 66 | 21.0191 |
| total_protein | lower_limit | 64 | 20.3822 |
| total_protein | physiological | 63 | 20.0637 |
| total_protein | upper_limit | 121 | 38.5350 |

## Note
- If a severity marker has zero qualifying rules, thresholds were still applied but no association passed filters.