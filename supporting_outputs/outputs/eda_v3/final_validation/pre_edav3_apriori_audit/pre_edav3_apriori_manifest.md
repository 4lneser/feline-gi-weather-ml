# Pre-EDA v3 Apriori Audit Manifest

## Scope
- Read-only reconstruction of earliest Apriori artifacts prior to `outputs/eda_v3/*`.
- No model rerun; no existing artifact overwritten.

## Candidate Apriori Artifact Directories (Chronological)
| mtime | path | classified_as_pre_v3 |
| --- | --- | --- |
| 2026-02-25 02:02:53 | `/Users/omaralneser/Documents/TYP/outputs/apriori` | True |
| 2026-02-27 23:18:40 | `/Users/omaralneser/Documents/TYP/outputs/eda_v3/apriori_refined_final` | False |
| 2026-03-01 00:20:37 | `/Users/omaralneser/Documents/TYP/outputs/eda_v3/apriori_refined_final2` | False |

## Pre-v3 Artifact Set Used
- Selected run directory: `/Users/omaralneser/Documents/TYP/outputs/apriori`
- Supporting report: `/Users/omaralneser/Documents/TYP/outputs/apriori/apriori_report.md`
- Key outputs: `/Users/omaralneser/Documents/TYP/outputs/apriori/rules_all.csv`, `/Users/omaralneser/Documents/TYP/outputs/apriori/rules_weather_to_outcome_filtered.csv`, `/Users/omaralneser/Documents/TYP/outputs/apriori/rules_top50.csv`, `/Users/omaralneser/Documents/TYP/outputs/apriori/stability_summary.csv`

## Generator Script Attribution
- Likely generator script: `/Users/omaralneser/Documents/TYP/apriori_weather_patterns.py`
- Key functions: `load_data()`, `build_transactions()`, `run_apriori()`, `prune_rules()`, `run_sensitivity()`.
- Attribution basis: output directory constant matches (`outputs/apriori`), file schema matches script exports, sensitivity file columns match scripted support grid.
- Nearby Apriori scripts (`apriori_refined_final.py`, `apriori_refined_final2.py`, `clinical_threshold_apriori_extension.py`) target `outputs/eda_v3/...` and are not pre-v3 artifacts.

## Configuration (Primary Run)
- `min_support = 0.1`
- `min_confidence = 0.6`
- `lift >= 1.2`
- `max_len = 3`
- Sensitivity supports: `[0.08, 0.10, 0.12]`
- Discretization: weather tertiles; moon numeric quartiles; temporal one-hot; outcome one-hot.

## Output Reconstruction
- Frequent itemsets: `1,088,514`
- All rules (unfiltered): `6,350,440`
- Weather→outcome filtered rules (primary thresholds): `0`
- Top50 file rows: `0`
- Stable rules across sensitivity supports: `0`
- Relaxed-support candidates (`sup=0.08`): `4`

## Top Rules Available
- Primary filtered set was empty; top rules reported from relaxed support sensitivity (`sup=0.08`).

| rule_key | support | confidence | lift |
| --- | ---: | ---: | ---: |
| `{moon_phase_category_waning, surface_pressure_max_mean_3d_mid} -> {outcome_acute_pancreatitis}` | 0.082540 | 0.634146 | 1.610936 |
| `{moon_phase_category_waning, wind_direction_10m_dominant_peak_7d_mid} -> {outcome_acute_pancreatitis}` | 0.082540 | 0.619048 | 1.572581 |
| `{rain_sum_mean_3d_low, wind_direction_10m_dominant_peak_7d_high} -> {outcome_acute_pancreatitis}` | 0.082540 | 0.619048 | 1.572581 |
| `{wind_direction_10m_dominant_peak_14d_high, wind_gusts_10m_max_peak_14d_low} -> {outcome_acute_pancreatitis}` | 0.085714 | 0.600000 | 1.524194 |

## Evidence-backed Sparse-output Explanation
- Primary filtered output is empty while sensitivity at lower support (0.08) yields 4 rules with confidence >= 0.60 and lift >= 1.20.
- This indicates support threshold (`min_support=0.10`) is the direct binding constraint in the pre-v3 run.
- Additional likely contributor: high item dimensionality relative to sample size (423 transaction items over 315 presentations).