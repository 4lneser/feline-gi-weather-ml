# Apriori Protocol Summary (Final Refined Pass)

Source inspected: `/Users/omaralneser/Documents/TYP/apriori_refined_final.py`

## 1) min_support
- `0.05` for all tracks (disease, cluster_clin, cluster_comb, severity).

## 2) min_confidence
- Dynamic per consequent: `min_confidence = baseline prevalence` of that consequent.
- Implemented as `association_rules(..., metric="confidence", min_threshold=baseline)` plus explicit confidence filter against baseline.

## 3) lift threshold
- Disease track: `lift >= 1.25`.
- Cluster tracks: `lift >= 1.20`.
- Severity track: `lift >= 1.20`.
- Additional singleton policy:
  - Disease: singleton antecedents require `lift >= 1.5`.
  - Cluster/Severity: singleton antecedents require `lift >= 1.2`.

## 4) max_len
- Frequent itemsets mined with `max_len=4` (Apriori itemset size cap).
- Rule antecedents are then constrained to length `1..3` (consequents fixed to length 1).

## 5) Discretization strategy
- Environmental numeric discretization: **25/75 quantile binning** only:
  - LOW: `<= 25th percentile`
  - HIGH: `>= 75th percentile`
  - middle range not encoded
- Environmental categoricals are one-hot encoded to boolean item flags.
- Lunar window flags are explicit booleans (`moon_near_full`, `moon_near_new`).
- `k=6` is **not** a discretization setting in this Apriori pass.

## 6) Reporting policy (k_best vs k=6)
- Cluster consequents are generated from **k_best only** cluster labels (`cluster_clin_kbest_*`, `cluster_comb_kbest_*`).
- Outputs written only for k_best cluster consequents (`cluster_rules_clinical_kbest.csv`, `cluster_rules_combined_kbest.csv`).
- There is **no implemented policy** to report `k=6` conditionally (e.g., "report k=6 only if >=3 rules with lift >=1.3").

## Additional reporting caps
- Top rules kept: `top_n=10` per consequent, ranked by `lift desc`, then `confidence desc`.