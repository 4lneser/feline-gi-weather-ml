# Final Validation Summary

## 1) Holdout vs CV Direction
- Holdout env-only mean AUC: 0.6154
- LightGBM env-only CV mean AUC: 0.5833
- HistGB vs LightGBM directional consistency: 4/4 diseases.

## 2) Model-family replication
- acute flare-up of triaditis/chronic enteropathy: HistGB AUC=0.5074, LGBM AUC=0.5610, HistGB p=0.5423, LGBM p=0.1443, direction_consistent=True
- acute gastroenteritis: HistGB AUC=0.5962, LGBM AUC=0.6141, HistGB p=0.0647, LGBM p=0.0299, direction_consistent=True
- acute pancreatitis: HistGB AUC=0.4776, LGBM AUC=0.4910, HistGB p=0.6418, LGBM p=0.5473, direction_consistent=True
- parvovirus enteritis: HistGB AUC=0.6200, LGBM AUC=0.6670, HistGB p=0.0498, LGBM p=0.0050, direction_consistent=True

## 3) Apriori robustness (top10 negative control)
- Stable: 0
- Moderately sensitive: 7
- Unstable: 3

## 4) Final statement
- Environmental disease classification signal: **Moderate**
- Environmental severity modulation signal: **Moderate**
- Overall robustness confidence: **Moderate**