# Unsupervised Structure Summary

## Scope
- Numeric-only PCA and clustering aligned to modeling feature blocks.
- Environmental PCA uses globally correlation-filtered `kept_weather_numeric` features (not raw weather numeric list).
- This is exploratory structure analysis only; no causal interpretation.

## PCA Thresholds
- environmental_only: n_features=31, n_pcs_70=7, n_pcs_80=10, n_pcs_90=15.
- clinical_only: n_features=27, n_pcs_70=6, n_pcs_80=9, n_pcs_90=12.
- combined: n_features=58, n_pcs_70=12, n_pcs_80=17, n_pcs_90=20.

## PC1-PC3 Loading Signals (top contributors)
- environmental_only: PC1 [precipitation_hours__mean_7d, precipitation_hours__mean_13d, precipitation_hours__peak_7d, precipitation_hours__mean_2d, precipitation_sum__mean_7d]; PC2 [snowfall_sum__mean_3d, snowfall_sum__mean_2d, snowfall_sum__mean_7d, snowfall_sum__mean_13d, apparent_temperature_max__day1]; PC3 [wind_gusts_10m_max__mean_7d, wind_gusts_10m_max__day1, wind_gusts_10m_max__mean_13d, wind_gusts_10m_max__peak_14d, precipitation_sum__peak_14d].
- clinical_only: PC1 [K value__missing, Na value__missing, Cl value__missing, CREA concentration __missing, Initial total protein concentration (in g/l)__missing]; PC2 [leukocyte count, neutrophil count (x 10^9/L), Cl value, BUN concentration, Albumin concentration (in g/l)]; PC3 [Albumin concentration (in g/l), initial hematocrit, Initial total protein concentration (in g/l), body weight, Na value].
- combined: PC1 [Na value__missing, K value__missing, Cl value__missing, initial hematocrit__missing, Initial total protein concentration (in g/l)__missing]; PC2 [precipitation_hours__mean_7d, precipitation_hours__mean_13d, precipitation_hours__peak_7d, precipitation_hours__mean_2d, precipitation_sum__mean_7d]; PC3 [snowfall_sum__mean_3d, snowfall_sum__mean_2d, snowfall_sum__mean_7d, snowfall_sum__mean_13d, apparent_temperature_max__day1].

## Clustering Alignment to Diagnosis
- environmental_only: best KMeans setting Dfixed6 (k_best=2), ARI=0.018, NMI=0.014.
- clinical_only: best KMeans setting Dfixed6 (k_best=2), ARI=0.098, NMI=0.085.
- combined: best KMeans setting Dfixed6 (k_best=2), ARI=0.094, NMI=0.079.

## Caveat
- Clusters are not expected to perfectly reproduce clinician diagnosis labels; use as latent structure screening only.
- Results are exploratory and non-causal.