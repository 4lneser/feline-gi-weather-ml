# Moon Integration Summary

## Normalization Interpretation
Exposure-normalized risk ratios were derived as case risk within lunar exposure strata divided by overall disease baseline risk. This controls for uneven lunar state frequency in the observed presentation timeline.

## Adjusted vs Unadjusted Circular Screening
Comparison used model_1_moon_only_circular (unadjusted) vs model_4_full (includes moon fraction, sex/neuter, and seasonality terms when available).
- acute flare-up of triaditis/chronic enteropathy: moon amplitude unadjusted=0.115, adjusted=0.090; fitted AUC model1=0.520, model4=0.677.
- acute gastroenteritis: moon amplitude unadjusted=0.294, adjusted=0.316; fitted AUC model1=0.569, model4=0.657.
- acute pancreatitis: moon amplitude unadjusted=0.233, adjusted=0.208; fitted AUC model1=0.545, model4=0.614.
- parvovirus enteritis: moon amplitude unadjusted=0.211, adjusted=0.188; fitted AUC model1=0.538, model4=0.865.

## Sex/Neuter Stratification (Unknown Included)
Stratified rows were retained only for strata with total exposure_n (stratum total_n) >= 20, including unknown categories (e.g., unknown_unknown).
Retained stratified rows: 16.
Rows containing unknown sex/neuter levels retained: 0.

## Multiplicity Caution
Multiple comparisons are present across diseases, lunar encodings, windows, and strata. P-value multiplicity correction (e.g., FDR) was not applied in this consolidation because only derived summary outputs were available; treat findings as exploratory.

## Scope
This integration is a post-hoc consolidation of precomputed outputs only. No preprocessing or model reruns were performed.