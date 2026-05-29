# Robustness Summary

## SHAP Stability (Binary HistGB)

| disease | feature_block | spearman_mean | jaccard_top10_mean | jaccard_top20_mean |
| --- | --- | --- | --- | --- |
| acute flare-up of triaditis/chronic enteropathy | clinical_only | 0.6014 | 0.5183 | 0.7404 |
| acute flare-up of triaditis/chronic enteropathy | combined | 0.4958 | 0.3396 | 0.4221 |
| acute flare-up of triaditis/chronic enteropathy | environmental_only | 0.8153 | 0.3869 | 0.5922 |
| acute gastroenteritis | clinical_only | 0.5848 | 0.4553 | 0.5670 |
| acute gastroenteritis | combined | 0.5214 | 0.4514 | 0.4732 |
| acute gastroenteritis | environmental_only | 0.8289 | 0.5821 | 0.6751 |
| acute pancreatitis | clinical_only | 0.5919 | 0.4342 | 0.5863 |
| acute pancreatitis | combined | 0.4480 | 0.3022 | 0.4304 |
| acute pancreatitis | environmental_only | 0.8332 | 0.3584 | 0.6635 |
| parvovirus enteritis | clinical_only | 0.5165 | 0.4342 | 0.5182 |
| parvovirus enteritis | combined | 0.3860 | 0.4425 | 0.4551 |
| parvovirus enteritis | environmental_only | 0.7841 | 0.4868 | 0.5560 |

## Permutation Test (Environmental-Only Binary HistGB)

| disease | observed_auc | perm_mean | perm_std | p_value | effect_size |
| --- | --- | --- | --- | --- | --- |
| acute flare-up of triaditis/chronic enteropathy | 0.5074 | 0.5099 | 0.0502 | 0.5423 | -0.0025 |
| acute gastroenteritis | 0.5962 | 0.5024 | 0.0596 | 0.0647 | 0.0938 |
| acute pancreatitis | 0.4776 | 0.4970 | 0.0468 | 0.6418 | -0.0194 |
| parvovirus enteritis | 0.6200 | 0.4979 | 0.0664 | 0.0498 | 0.1221 |

## Note

These robustness checks evaluate stability/significance patterns in exploratory association modeling; they do not establish causal effects.
