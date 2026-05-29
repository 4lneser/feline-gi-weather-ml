# Environmental Signal Summary

## Ranked Diseases (environmental_only)

| disease | histgb_cv_auc | histgb_holdout_auc | lgbm_cv_auc | histgb_perm_p | lgbm_perm_p | shap_env_mean_spearman | delta_holdout_vs_cv | environmental_signal_strength | robustness_tier |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| parvovirus enteritis | 0.6200 | 0.7591 | 0.6670 | 0.0498 | 0.0050 | 0.7841 | 0.1390 | Suggestive | Low |
| acute gastroenteritis | 0.5962 | 0.7288 | 0.6141 | 0.0647 | 0.0299 | 0.8289 | 0.1325 | Weak | Low |
| acute flare-up of triaditis/chronic enteropathy | 0.5074 | 0.5284 | 0.5610 | 0.5423 | 0.1443 | 0.8153 | 0.0210 | Weak | Low |
| acute pancreatitis | 0.4776 | 0.4453 | 0.4910 | 0.6418 | 0.5473 | 0.8332 | -0.0323 | Weak | Low |

## Interpretation
Environmental signal is heterogeneous by disease: parvovirus and acute gastroenteritis show the strongest environmental-only discrimination and favorable permutation support across models, while acute flare-up triaditis/chronic enteropathy and acute pancreatitis remain weak with non-supportive permutation evidence. SHAP rank stability in environmental-only models is high across diseases (Spearman > 0.78), indicating consistent feature ordering even when predictive strength is limited for some outcomes.

**Environmental disease-level classification signal is overall: Suggestive.**