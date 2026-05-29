# BUN Rule Validation Summary

## Baseline
- Total N: 314
- BUN_increased prevalence: 38.54% (121/314)
- Antecedent prevalence: precipitation_hours_mean_7d_low=28.03%, precipitation_hours_peak_14d_low=30.89%, surface_pressure_max_day1_high=26.11%
- Full conjunction prevalence: 8.28% (26/314)

## Full Rule Metrics
- Support: 0.0637 (count=20)
- Confidence: 0.7692
- Lift: 1.9962
- Apriori confidence reference: 0.7692
- Apriori lift reference: 1.9962
- Apriori support reference: 0.0637

## Ablation Survival (>1.5 lift)
- Strongest ablation lift: 1.5430
- Survives ablation criterion: no

## Discretization Sensitivity (20/80)
- 20/80 lift: 1.5969
- Survives sensitivity criterion (>1.5): yes

## Disease Composition in Rule-Covered Subset
- acute pancreatitis: subset 10 (38.46%), overall 124 (39.49%), ratio 0.97
- acute flare-up of triaditis/chronic enteropathy: subset 9 (34.62%), overall 89 (28.34%), ratio 1.22
- acute gastroenteritis: subset 5 (19.23%), overall 60 (19.11%), ratio 1.01
- parvovirus enteritis: subset 2 (7.69%), overall 41 (13.06%), ratio 0.59

## Interpretation
- Robustness classification: **Moderately sensitive**.
- This is a post-hoc stability check of one association rule; it remains exploratory and non-causal.