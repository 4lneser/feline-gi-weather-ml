# Permutation Protocol Summary

This is a read-only verification of the permutation design implemented in `/Users/omaralneser/Documents/TYP/run_eda_v3.py` (HistGB and LightGBM env-only permutation blocks).

## 1) What was permuted?
- The **entire binary target vector** for a given disease (`y_array`) was permuted globally per permutation index.
- Implementation: `y_perm_array = np.random.default_rng(random_state + perm_idx).permutation(y_array)` inside `_single_perm_auc`.
- Code references: `run_eda_v3.py:955-960` (HistGB) and `run_eda_v3.py:1755-1760` (LightGBM).

## 2) Was stratification preserved?
- Yes for the **fold construction** step: `StratifiedKFold(...).split(X, y)` is built using the original (non-permuted) binary labels.
- During permutation, labels are shuffled and then indexed by these fixed fold indices; therefore fold sizes remain fixed, but strict class-balance-per-fold after permutation is not explicitly enforced.
- Code references: `run_eda_v3.py:950-953` and `run_eda_v3.py:1750-1752`.

## 3) When was permutation applied relative to CV?
- Fold indices are computed once first (`fixed_splits`), then permutation is applied to `y_array`, and model fit/evaluation is run across those fixed train/test indices.
- So permutation is **before per-fold model fitting/evaluation**, but after defining fixed CV split indices.
- It is not applied only on validation labels; it is applied to the full target vector, then sliced into train/test by fold indices.

## 4) How was AUC computed?
- For each permutation and disease:
  - train model on each fold train set with permuted labels,
  - compute ROC-AUC on that fold test predictions,
  - take the **mean AUC across folds** as `perm_mean_auc`.
- The null distribution is the set of these per-permutation fold-mean AUC values.
- Observed AUC is taken from the existing CV summary (`roc_auc_mean` for environmental_only).
- p-value: `(count(perm_mean_auc >= observed_auc) + 1) / (n_perm + 1)`.

## 5) Is N=200 fixed?
- Not hard-coded fixed: `n_perm` comes from CLI argument `--perm-n` (default = 200).
- Therefore protocol default is 200, but configurable.
- In current HistGB output (`outputs/eda_v3/tables/permtest_envonly_auc_summary.csv`), observed `n_perm` values: [200].
- In current LightGBM output (`outputs/eda_v3/final_validation/lgbm_permtest_env_only.csv`), observed `n_perm` values: [200].