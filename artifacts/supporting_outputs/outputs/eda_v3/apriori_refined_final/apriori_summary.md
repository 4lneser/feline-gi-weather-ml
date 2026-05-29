# Apriori Refined Final Summary

## Setup
- Environmental numeric features (kept): 31
- Environmental categorical features: 5
- Clinical cluster k_best source: clinical_only={'dtag': 'Dfixed6', 'k': 2, 'silhouette': 0.5317265764606748}, combined={'dtag': 'Dfixed6', 'k': 2, 'silhouette': 0.40635838091614973}
- Severity cutoffs were taken from `Heamtology parameter interpreta` only:
  - BUN_high: threshold=11.7200, data_column=BUN concentration
  - CREA_high: threshold=160.0000, data_column=CREA concentration 
  - albumin_low: threshold=27.0000, data_column=Albumin concentration (in g/l)
  - leukocyte_high: threshold=17.0300, data_column=leukocyte count
  - neutrophil_high: threshold=10.3000, data_column=neutrophil count (x 10^9/L)

## Baseline Prevalence By Consequent
| track | consequent_name | baseline_prevalence |
| --- | --- | --- |
| cluster_clin | cluster_clin_kbest_0 | 0.7873 |
| cluster_clin | cluster_clin_kbest_1 | 0.2127 |
| cluster_comb | cluster_comb_kbest_0 | 0.7810 |
| cluster_comb | cluster_comb_kbest_1 | 0.2190 |
| disease | disease_ap | 0.3937 |
| disease | disease_ge | 0.1905 |
| disease | disease_parvo | 0.1302 |
| disease | disease_tri | 0.2857 |
| severity | BUN_high | 0.3841 |
| severity | CREA_high | 0.2921 |
| severity | albumin_low | 0.2444 |
| severity | leukocyte_high | 0.1619 |
| severity | neutrophil_high | 0.2159 |

## Qualifying Rule Counts By Consequent
| consequent_name | n_rules |
| --- | --- |
| BUN_high | 10 |
| CREA_high | 10 |
| albumin_low | 10 |
| cluster_clin_kbest_0 | 10 |
| cluster_clin_kbest_1 | 10 |
| cluster_comb_kbest_0 | 10 |
| cluster_comb_kbest_1 | 10 |
| disease_ap | 10 |
| disease_ge | 10 |
| disease_tri | 10 |
| neutrophil_high | 10 |
| disease_parvo | 6 |
| leukocyte_high | 6 |

## Top 3 Strongest Rules Per Track
### disease
| consequent_name | antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- | --- |
| disease_ge | snowfall_sum_mean_13d_low, surface_pressure_max_day1_low | 0.0508 | 0.3404 | 1.7872 | 0.1905 |
| disease_ge | precipitation_hours_peak_7d_high, precipitation_sum_mean_7d_high | 0.0571 | 0.3396 | 1.7830 | 0.1905 |
| disease_ap | daylight_duration_day1_high, precipitation_hours_peak_7d_low, precipitation_sum_mean_7d_low | 0.0508 | 0.6957 | 1.7672 | 0.3937 |
### cluster_clin
| consequent_name | antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- | --- |
| cluster_clin_kbest_1 | precipitation_hours_mean_13d_high, precipitation_sum_mean_13d_high, snowfall_sum_mean_13d_low | 0.0508 | 0.5000 | 2.3507 | 0.2127 |
| cluster_clin_kbest_1 | precipitation_hours_mean_7d_high, snowfall_sum_mean_13d_low | 0.0603 | 0.4872 | 2.2905 | 0.2127 |
| cluster_clin_kbest_1 | precipitation_hours_mean_13d_high, snowfall_sum_mean_13d_low | 0.0603 | 0.4750 | 2.2332 | 0.2127 |
### cluster_comb
| consequent_name | antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- | --- |
| cluster_comb_kbest_1 | precipitation_hours_mean_13d_high, precipitation_sum_mean_13d_high, snowfall_sum_mean_13d_low | 0.0508 | 0.5000 | 2.2826 | 0.2190 |
| cluster_comb_kbest_1 | precipitation_hours_mean_7d_high, snowfall_sum_mean_13d_low | 0.0603 | 0.4872 | 2.2241 | 0.2190 |
| cluster_comb_kbest_1 | precipitation_hours_mean_13d_high, snowfall_sum_mean_13d_low | 0.0603 | 0.4750 | 2.1685 | 0.2190 |
### severity
| consequent_name | antecedents | support | confidence | lift | baseline_prevalence |
| --- | --- | --- | --- | --- | --- |
| BUN_high | precipitation_hours_mean_7d_low, precipitation_hours_peak_14d_low, surface_pressure_max_day1_high | 0.0635 | 0.7692 | 2.0025 | 0.3841 |
| BUN_high | precipitation_hours_peak_14d_low, precipitation_sum_mean_7d_low, surface_pressure_max_day1_high | 0.0571 | 0.7500 | 1.9525 | 0.3841 |
| BUN_high | precipitation_hours_mean_7d_low, precipitation_hours_peak_14d_low, surface_pressure_max_mean_13d_high | 0.0635 | 0.7407 | 1.9284 | 0.3841 |

## Note
- Exploratory association mining only. These rules are non-causal and hypothesis-generating.