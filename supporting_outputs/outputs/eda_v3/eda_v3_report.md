# EDA v3: Weather-Focused Reproduction (HTML-style)

This run follows the structure of the prior weather-results workflow (PCA -> filtering -> RF -> OR) on the enriched feline dataset.

## Dataset Snapshot
- Shape: **315 rows x 208 columns**
- Outcome column: **`group`**

### Outcome Distribution
| outcome | count | pct |
| --- | --- | --- |
| acute pancreatitis | 124 | 39.37 |
| acute flare-up of triaditis/chronic enteropathy | 90 | 28.57 |
| acute gastroenteritis | 60 | 19.05 |
| parvovirus enteritis | 41 | 13.02 |

### Feature Grouping Summary
| group | n_columns |
| --- | --- |
| weather_numeric | 133 |
| weather_categorical | 2 |
| moon_numeric | 4 |
| moon_categorical | 1 |
| moon_default_model_numeric | 3 |
| moon_threshold_model_numeric | 2 |
| moon_threshold_model_categorical | 1 |
| temporal_derived | 3 |
| all_numeric_model | 163 |
| all_categorical_model | 30 |
| excluded_metadata | 8 |
| excluded_leakage | 2 |

### Reusable Feature Blocks
| feature_block | n_numeric | n_categorical | n_total |
| --- | --- | --- | --- |
| clinical_only | 27 | 25 | 52 |
| combined | 58 | 30 | 88 |
| environmental_only | 31 | 5 | 36 |

## Stratified 5-Fold CV (Primary Evaluation)
| model | feature_block | accuracy_mean_pm_std | balanced_accuracy_mean_pm_std | macro_f1_mean_pm_std | weighted_f1_mean_pm_std |
| --- | --- | --- | --- | --- | --- |
| hist_gb | clinical_only | 0.5810 ± 0.1074 | 0.6064 ± 0.0860 | 0.6099 ± 0.1018 | 0.5772 ± 0.1099 |
| hist_gb | combined | 0.5746 ± 0.0713 | 0.6055 ± 0.0854 | 0.6143 ± 0.0735 | 0.5757 ± 0.0668 |
| hist_gb | environmental_only | 0.3683 ± 0.0519 | 0.3389 ± 0.0299 | 0.3434 ± 0.0378 | 0.3631 ± 0.0484 |
| logistic_ovr | clinical_only | 0.5556 ± 0.0489 | 0.5988 ± 0.0330 | 0.5855 ± 0.0433 | 0.5492 ± 0.0528 |
| logistic_ovr | combined | 0.5333 ± 0.0509 | 0.5794 ± 0.0382 | 0.5739 ± 0.0451 | 0.5299 ± 0.0517 |
| logistic_ovr | environmental_only | 0.3079 ± 0.0497 | 0.3241 ± 0.0468 | 0.3088 ± 0.0424 | 0.3017 ± 0.0492 |
| random_forest | clinical_only | 0.5365 ± 0.0507 | 0.5304 ± 0.0509 | 0.5281 ± 0.0471 | 0.5110 ± 0.0492 |
| random_forest | combined | 0.5333 ± 0.0509 | 0.5218 ± 0.0704 | 0.5091 ± 0.0638 | 0.4863 ± 0.0538 |
| random_forest | environmental_only | 0.3778 ± 0.0455 | 0.3424 ± 0.0394 | 0.3514 ± 0.0424 | 0.3670 ± 0.0426 |

## Legacy EDA Block (Carried into v3)
- Existing EDA style outputs are included in this run (missingness, monthly trends, weather/UV/moon plots).
- UV columns profiled: **7**
- Moon numeric columns profiled: **4**
- Moon categorical columns profiled: **1**
- Variables with any missingness: **0**

## PCA Analysis (Weather Block)
- PC1 variance ratio: **0.5162**
- PC2 variance ratio: **0.1219**
- PC3 variance ratio: **0.0611**
- See scree and loading outputs for interpretation.

## RF Model (All Usable Features)
- Accuracy: **0.5079**
- Balanced accuracy: **0.5311**
- Macro F1: **0.5395**

## Filtering Weather Parameters (Correlation Matrix)
- Correlation threshold: **|r| > 0.85**
- Weather numeric before: **136**
- Weather numeric after: **31**

## RF Model (Environmental Conditions)
- Accuracy: **0.4444**
- Balanced accuracy: **0.4169**
- Macro F1: **0.4332**

## Logistic Model (Odds Ratios)
- Top OR feature per class:
| outcome_class | feature | odds_ratio |
| --- | --- | --- |
| acute flare-up of triaditis/chronic enteropathy | wind_gusts_10m_max__peak_14d | 1.3486219625040219 |
| acute gastroenteritis | wind_gusts_10m_max__peak_14d | 0.5709776959298076 |
| acute pancreatitis | surface_pressure_max__day1 | 1.2895427476292936 |
| parvovirus enteritis | wind_direction_10m_dominant__mean_13d | 0.45514437402200797 |

## Moon Encoding Sensitivity
- RF + logistic screening rerun under three moon encodings: sincos(+fraction), thresholded flags(+category), and mixed.
| encoding | rf_accuracy | rf_balanced_accuracy | rf_macro_f1 | numeric_features_after_corr | logistic_top_or_feature | logistic_top_or_value |
| --- | --- | --- | --- | --- | --- | --- |
| sincos_fraction | 0.4444444444444444 | 0.41694444444444445 | 0.43321226795803064 | 31 | wind_direction_10m_dominant__mean_13d | 0.45514437402200797 |
| thresholded | 0.4126984126984127 | 0.39694444444444443 | 0.41164126667616197 | 31 | wind_direction_10m_dominant__mean_7d | 2.6935883677978727 |
| mixed | 0.4126984126984127 | 0.38263888888888886 | 0.404204653557544 | 33 | wind_gusts_10m_max__peak_14d | 0.5621144854035108 |

## Interpretation Notes
- Exploratory only; no causal inference.
- Correlation filtering reduces redundancy but can remove potentially useful interactions.
- RF importances are relative; OR effects are class-specific and model-dependent.

## Output Paths
- Root: `outputs/eda_v3`
- Tables: `outputs/eda_v3/tables`
- Plots: `outputs/eda_v3/plots`
- Models: `outputs/eda_v3/models`