# Lunar Incidence Analysis Summary

## Scope

This module performs lunar association screening with exposure normalization. It is exploratory and non-causal.

## Dataset

- N presentations: 315
- Outcome column: `group`
- Disease counts:
  - acute pancreatitis: 124
  - acute flare-up of triaditis/chronic enteropathy: 90
  - acute gastroenteritis: 60
  - parvovirus enteritis: 41

## Exposure Distributions

- moon_category=new: 45
- moon_category=waxing: 109
- moon_category=full: 38
- moon_category=waning: 123
- moon_category=unknown: 0
- is_full_moon=1: 38
- is_new_moon=1: 45

## Key Risk-Ratio Findings

- acute flare-up of triaditis/chronic enteropathy | new: RR=1.400 (95% CI 0.933 to 1.840)
- acute gastroenteritis | waxing: RR=1.252 (95% CI 0.943 to 1.608)
- acute gastroenteritis | new: RR=0.817 (95% CI 0.295 to 1.367)
- acute pancreatitis | waning: RR=1.157 (95% CI 0.982 to 1.327)
- acute pancreatitis | new: RR=0.847 (95% CI 0.501 to 1.173)
- parvovirus enteritis | new: RR=0.854 (95% CI 0.213 to 1.572)
- acute gastroenteritis | waning: RR=0.854 (95% CI 0.579 to 1.153)
- parvovirus enteritis | waxing: RR=1.128 (95% CI 0.734 to 1.556)

## Circular Logistic Screening

- acute flare-up of triaditis/chronic enteropathy | model_1_moon_only_circular: fitted AUC=0.520, pseudo-R2=-0.157, periodicity_supported=False
- acute flare-up of triaditis/chronic enteropathy | model_2_plus_sex_neuter: fitted AUC=0.645, pseudo-R2=-0.104, periodicity_supported=False
- acute flare-up of triaditis/chronic enteropathy | model_3_plus_seasonality: fitted AUC=0.584, pseudo-R2=-0.141, periodicity_supported=False
- acute flare-up of triaditis/chronic enteropathy | model_4_full: fitted AUC=0.677, pseudo-R2=-0.088, periodicity_supported=False
- acute gastroenteritis | model_1_moon_only_circular: fitted AUC=0.569, pseudo-R2=-0.411, periodicity_supported=False
- acute gastroenteritis | model_2_plus_sex_neuter: fitted AUC=0.599, pseudo-R2=-0.391, periodicity_supported=False
- acute gastroenteritis | model_3_plus_seasonality: fitted AUC=0.632, pseudo-R2=-0.371, periodicity_supported=False
- acute gastroenteritis | model_4_full: fitted AUC=0.657, pseudo-R2=-0.348, periodicity_supported=False
- acute pancreatitis | model_1_moon_only_circular: fitted AUC=0.545, pseudo-R2=-0.029, periodicity_supported=False
- acute pancreatitis | model_2_plus_sex_neuter: fitted AUC=0.614, pseudo-R2=0.001, periodicity_supported=False
- acute pancreatitis | model_3_plus_seasonality: fitted AUC=0.585, pseudo-R2=-0.016, periodicity_supported=False
- acute pancreatitis | model_4_full: fitted AUC=0.614, pseudo-R2=0.008, periodicity_supported=False
- parvovirus enteritis | model_1_moon_only_circular: fitted AUC=0.538, pseudo-R2=-0.784, periodicity_supported=False
- parvovirus enteritis | model_2_plus_sex_neuter: fitted AUC=0.845, pseudo-R2=-0.279, periodicity_supported=False
- parvovirus enteritis | model_3_plus_seasonality: fitted AUC=0.677, pseudo-R2=-0.663, periodicity_supported=False
- parvovirus enteritis | model_4_full: fitted AUC=0.865, pseudo-R2=-0.236, periodicity_supported=False

## Sex/Neuter + Seasonality Notes

- Sex/neuter adjustment enabled: True (unknown retained; never dropped).
- Seasonality adjustment enabled: True.

## Window Analysis Note

- Near-full/new windows use an approximate dataset-timeline definition: rows within ±2 days of observed full/new anchor rows.

## Limitations

- Observational association screening only; no causal inference.
- Moon-window proximity is approximate and depends on available row dates.
- Multiple testing risk across diseases/models/metrics.
- Internal-only validation context.
