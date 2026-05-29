# BUN Rule Validation Summary

## Baseline
- Total N: 315
- BUN_increased prevalence: 38.41% (121/315)
- Antecedent prevalence: precipitation_hours_mean_7d_low=27.94%, precipitation_hours_peak_14d_low=30.79%, surface_pressure_max_day1_high=26.03%
- Full conjunction prevalence: 8.25% (26/315)

## Full Rule Metrics
- Support: 0.0635 (count=20)
- Confidence: 0.7692
- Lift: 2.0025
- Apriori confidence reference: 0.7692
- Apriori lift reference: 2.0025
- Apriori support reference: 0.0635

## Ablation Survival (>1.5 lift)
- Strongest ablation lift: 1.5479
- Survives ablation criterion: no

## Discretization Sensitivity (20/80)
- 20/80 lift: 1.6020
- Survives sensitivity criterion (>1.5): yes

## Disease Composition in Rule-Covered Subset
- acute pancreatitis: subset 10 (38.46%), overall 124 (39.37%), ratio 0.98
- acute flare-up of triaditis/chronic enteropathy: subset 9 (34.62%), overall 90 (28.57%), ratio 1.21
- acute gastroenteritis: subset 5 (19.23%), overall 60 (19.05%), ratio 1.01
- parvovirus enteritis: subset 2 (7.69%), overall 41 (13.02%), ratio 0.59

## Interpretation
- Robustness classification: **Moderately sensitive**.
- This is a post-hoc stability check of one association rule; it remains exploratory and non-causal.