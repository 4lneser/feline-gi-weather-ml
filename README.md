[![DOI](https://zenodo.org/badge/1252925985.svg)](https://doi.org/10.5281/zenodo.20437783)

# AI Modeling of Meteorological Influences on Acute Gastrointestinal Disease in Cats

This repository contains the reproducibility artifacts, notebook mirrors, and supporting outputs accompanying the bachelor's thesis:

**AI Modeling of Meteorological Influences on Acute Gastrointestinal Disease in Cats**<br>
Omar Alneser, Lancaster University Leipzig (2026)

## Overview

This project investigates whether meteorological and environmental variables can be used to model acute gastrointestinal disease presentations in cats.

The study combines veterinary clinical records with environmental observations, including weather conditions, UV exposure, and lunar phase features. The analysis uses machine learning, clustering, explainable AI, permutation testing, and association rule mining to evaluate whether environmental signals show useful predictive or descriptive relationships with acute gastrointestinal disease presentations.

This public repository is an artifact release. It includes notebook versions of the thesis production scripts, selected helper notebooks, manifests, generated figures and tables, and non-sensitive supporting outputs. Raw clinical records and row-level prediction exports are excluded for privacy and institutional reasons.

## Methods

The analysis artifacts cover:

- Data preprocessing and feature engineering
- Weather, UV, and lunar feature enrichment
- Missing-value imputation and preprocessing comparisons
- HistGradientBoosting, Random Forest, Logistic Regression, and LightGBM-based validation analyses
- Stratified cross-validation, permutation testing, and holdout evaluation
- SHAP explainability and feature-importance summaries
- PCA, K-Means clustering, and hierarchical clustering
- Apriori association rule mining and clinical-threshold extensions
- Lunar-phase incidence and sensitivity analyses
- Thesis figure and table regeneration workflows

## Repository Structure

```text
.
|-- README.md
|-- .gitattributes
|-- manifests/
|   |-- helper_notebooks.csv
|   |-- production_notebooks.csv
|   `-- script_inventory.md
|-- notebooks_helpers/
|   `-- Notebook mirrors of supporting and legacy helper scripts
|-- notebooks_production/
|   `-- Notebook mirrors of final thesis production scripts
`-- supporting_outputs/
    |-- appendix summary CSV files
    |-- lunar analysis outputs and plots
    |-- eda_v3 and d7 comparison outputs
    `-- thesis-paper figures and tables
```

The `manifests/` directory maps notebooks back to the source scripts used during thesis development. The original script inventory is included in `manifests/script_inventory.md`.

## Data and Privacy

The following materials are intentionally not included:

- Raw veterinary clinical source records
- Row-level prediction exports
- Sensitive intermediate datasets that could expose clinical record details

The included outputs are intended to support thesis inspection and reproducibility without distributing restricted clinical data.

## Requirements

The notebooks were developed in Python using common scientific computing and machine learning libraries, including:

- NumPy
- Pandas
- scikit-learn
- Matplotlib
- SHAP
- LightGBM
- mlxtend or equivalent Apriori association-rule tooling

No locked `requirements.txt` is included in this artifact snapshot. Re-running the full workflow may require reconstructing the original analysis environment and access to the restricted source data.

## Reproducibility Notes

The production notebooks preserve the analysis logic used to generate the thesis outputs, but this repository should be treated as a reproducibility artifact rather than a fully self-contained public dataset release. Some notebooks require source data that cannot be publicly distributed.

Large generated logs are tracked with Git LFS. If cloning this repository for inspection, install Git LFS first:

```bash
git lfs install
git clone https://github.com/4lneser/feline-gi-weather-ml.git
```

## Citation

If you use this repository, please cite:

Alneser, O. (2026). *AI Modeling of Meteorological Influences on Acute Gastrointestinal Disease in Cats*. Lancaster University Leipzig.

DOI: Pending Zenodo publication<br>
arXiv: Pending submission

## License

This repository is released under the MIT License unless otherwise specified.
