# Unsupervised Protocol Summary

Read-only method verification of the unsupervised block in `/Users/omaralneser/Documents/TYP/run_eda_v3.py`.

## 1) PCA preprocessing
- Numeric matrices are standardized with `StandardScaler()` before PCA (`fit_transform` on numeric matrix).
- This applies centering + variance scaling (z-score standardization), not centering-only.
- Missing numeric values are median-imputed beforehand (`build_numeric_matrix` + `fillna(median)` in unsupervised path).

## 2) Missingness indicators in clinical PCA
- Yes. Clinical numeric PCA includes missingness indicator columns (`__missing`).
- Count in clinical numeric block: **13** indicators out of 27 clinical numeric features.
- Indicators: Albumin concentration (in g/l)__missing, BUN concentration__missing, CREA concentration __missing, Cl value__missing, Initial total protein concentration (in g/l)__missing, K value__missing, Na value__missing, body weight__missing, hospitalization time (days)__missing, initial hematocrit__missing, leukocyte count__missing, lymphocyte count__missing, neutrophil count (x 10^9/L)__missing

## 3) KMeans configuration
- Algorithm: `sklearn.cluster.KMeans`.
- Initialization count: `n_init=50` (explicitly set).
- `random_state=42` (passed from seed argument).
- Candidate `k` scanned in silhouette step: `k=2..8`; then evaluated explicitly at `k=4`, `k=6`, and `k_best`.

## 4) Meaning of k=6
- `k=6` refers to **clustering only** (number of clusters for KMeans and hierarchical cut labels in contingency evaluation).
- It is **not** discretization binning.
- In this pipeline, discretization is a separate concept used elsewhere (e.g., Apriori item binning), not in PCA/clustering.