# Apriori Refined Final 2 Summary

## Configuration
- Antecedents: environmental-only items (LOW/HIGH at 25th/75th quantiles + environmental categorical one-hot + moon_near_new/moon_near_full).
- Itemset max length = 4; antecedent size <= 3.
- min_support = 0.05.
- min_confidence = consequent baseline prevalence (dynamic).
- lift thresholds: diagnosis >= 1.25; severity/cluster >= 1.20.
- Singleton diagnosis rules shown only if lift >= 1.5.
- Stability screen: 5 stratified folds by diagnosis, stable if appears in >=3/5 training folds.
- Environmental antecedent item count: 676.
- k_best used for cluster consequents: clinical_only=2, combined=2.

## Reporting Policy
- k_best cluster rules reported fully.
- k=6 cluster rules met reporting threshold (>=3 rules with lift >= 1.3).

## Top 5 Rules By Track (Lift)
### Diagnosis
| consequent_name | antecedents | support | confidence | lift |
| --- | --- | --- | --- | --- |
| diagnosis=acute gastroenteritis | snowfall_sum_mean_13d_low, surface_pressure_max_day1_low | 0.051 | 0.340 | 1.787 |
| diagnosis=acute gastroenteritis | precipitation_hours_peak_7d_high, precipitation_sum_mean_7d_high | 0.057 | 0.340 | 1.783 |
| diagnosis=acute pancreatitis | daylight_duration_day1_high, precipitation_hours_peak_7d_low, precipitation_sum_mean_7d_low | 0.051 | 0.696 | 1.767 |
| diagnosis=parvovirus enteritis | eda3_season__autumn | 0.067 | 0.228 | 1.754 |
| diagnosis=acute gastroenteritis | precipitation_hours_mean_2d_high, snowfall_sum_mean_13d_low | 0.054 | 0.333 | 1.750 |

### Severity
| consequent_name | antecedents | support | confidence | lift |
| --- | --- | --- | --- | --- |
| TOTAL_PROTEIN_INCREASED | precipitation_hours_mean_13d_low, precipitation_hours_mean_7d_low, precipitation_sum_mean_2d_low | 0.051 | 0.457 | 2.149 |
| TOTAL_PROTEIN_INCREASED | precipitation_hours_mean_13d_low, precipitation_hours_mean_2d_low, precipitation_sum_mean_7d_low | 0.051 | 0.432 | 2.033 |
| TOTAL_PROTEIN_INCREASED | precipitation_hours_mean_2d_low, precipitation_hours_mean_7d_low, precipitation_sum_mean_13d_low | 0.051 | 0.432 | 2.033 |
| BUN_LOWER_LIMIT | precipitation_hours_day1_high, wind_gusts_10m_max_mean_13d_high | 0.051 | 0.533 | 2.024 |
| TOTAL_PROTEIN_INCREASED | precipitation_hours_mean_13d_low, precipitation_hours_mean_2d_low, precipitation_hours_mean_7d_low | 0.057 | 0.429 | 2.015 |

### Cluster k_best
| consequent_name | antecedents | support | confidence | lift |
| --- | --- | --- | --- | --- |
| cluster_clinical_kbest=1 | precipitation_hours_mean_13d_high, precipitation_sum_mean_13d_high, snowfall_sum_mean_13d_low | 0.051 | 0.500 | 2.351 |
| cluster_clinical_kbest=1 | precipitation_hours_mean_7d_high, snowfall_sum_mean_13d_low | 0.060 | 0.487 | 2.290 |
| cluster_combined_kbest=1 | precipitation_hours_mean_13d_high, precipitation_sum_mean_13d_high, snowfall_sum_mean_13d_low | 0.051 | 0.500 | 2.283 |
| cluster_clinical_kbest=1 | precipitation_hours_mean_13d_high, snowfall_sum_mean_13d_low | 0.060 | 0.475 | 2.233 |
| cluster_combined_kbest=1 | precipitation_hours_mean_7d_high, snowfall_sum_mean_13d_low | 0.060 | 0.487 | 2.224 |

### Cluster k=6
| consequent_name | antecedents | support | confidence | lift |
| --- | --- | --- | --- | --- |
| cluster_combined_k6=5 | precipitation_hours_mean_13d_high, snowfall_sum_mean_13d_low | 0.051 | 0.400 | 5.040 |
| cluster_combined_k6=5 | precipitation_hours_peak_7d_high, precipitation_sum_mean_13d_high | 0.054 | 0.362 | 4.557 |
| cluster_combined_k6=5 | precipitation_hours_mean_13d_high, precipitation_hours_peak_7d_high | 0.051 | 0.314 | 3.953 |
| cluster_combined_k6=5 | precipitation_hours_mean_7d_high, precipitation_sum_mean_7d_high | 0.051 | 0.314 | 3.953 |
| cluster_combined_k6=5 | precipitation_hours_mean_13d_high, precipitation_hours_mean_7d_high | 0.057 | 0.310 | 3.910 |

## Note
- Exploratory association mining only; non-causal and hypothesis-generating.
