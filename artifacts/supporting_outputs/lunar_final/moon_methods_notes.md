# Lunar Final Methods Notes

- Input: `outputs/imputed_dataset_enriched.csv`.
- Phase angle basis: `moon_phase_angle_deg` normalized to [0, 360).
- Circular incidence binning: 15° bins with Wilson 95% CI for per-bin risk; moving-average smoothing window = 3 bins.
- Category definition: normalized to `new`, `waxing`, `full`, `waning` (existing category if mappable, otherwise angle-derived fallback).
- Window sensitivity definitions: `near_new` and `near_full` using angular windows W in {15°, 30°}.
- RR calculation: risk in level divided by disease baseline prevalence (OvR).
- RR CI: derived using Wilson intervals on level risk and baseline risk, then ratio-bounded.
- Stratification: sex mapped to {male,female,unknown}; neuter mapped to {neutered,intact,unknown}; combined stratum `sex_neuter` retained for all rows (including unknown).
- Plot/table stratum inclusion rule: strata shown in stratified visuals only if total_n >= 20.
- Small-strata excluded from stratified visuals: 1 strata (listed in `sex_neuter_distribution.csv`).
- Caution: imbalance and small cells can widen uncertainty; results are exploratory and non-causal.
