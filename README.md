
# Seattle Traffic Collision Severity Prediction

This repository contains a capstone project completed for the IBM Data Science Professional Certificate on Coursera. The project uses historical Seattle traffic collision records to predict whether a collision is likely to be severe.

## Project Goal

The objective is to build a binary classifier that predicts collision severity:

- `0`: Lower severity
- `1`: Higher severity

The target comes from `SEVERITYCODE` in the source dataset, where the original values are remapped:

- `1 -> 0`
- `2 -> 1`

## Repository Contents

- `Capstone Project - Seattle Collisions.ipynb`: Main notebook with exploration, feature engineering, modeling, and evaluation.
- `seattle_collisions.py`: Script version of the analysis workflow.
- `Data-Collisions.csv`: Input dataset used by both notebook and script.
- `Predicting Collisions.pptx`: Presentation summary of project findings.
- `README.md`: Project documentation.

## Workflow Summary

The implemented workflow includes:

1. Data loading and profiling
2. Missing-value and datatype inspection
3. Time feature extraction from date/time fields (`year`, `month`, `day`, `weekday`, `HOUR`, `AMPM`)
4. Exploratory analysis with count plots and heatmaps
5. Rule-based feature engineering for high-risk indicators
6. Categorical encoding using one-hot encoding
7. Train/test split
8. Class balancing with random oversampling (`RandomOverSampler`)
9. Model training and evaluation using multiple classifiers

## Models Used

The project trains and evaluates several supervised classifiers:

- LightGBM
- Gaussian Naive Bayes
- XGBoost
- MLPClassifier (neural network)

Each model is evaluated using:

- Confusion matrix
- ROC AUC
- Sensitivity (recall for positive class)
- Specificity
- Accuracy
- Classification report (precision/recall/F1)

## Prerequisites

Use Python 3.8+ (recommended) and install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn lightgbm xgboost eli5 ipython
```

## How To Run

### Option 1: Notebook (recommended)

1. Open `Capstone Project - Seattle Collisions.ipynb` in Jupyter or VS Code.
2. Ensure `Data-Collisions.csv` is in the same folder.
3. Run cells in order.

### Option 2: Python script

1. Open `seattle_collisions.py`.
2. Update the hard-coded working directory (`os.chdir(...)`) to your local path, or remove it if running from the repository root.
3. Run:

```bash
python seattle_collisions.py
```

## Notes And Limitations

- The script contains hard-coded local paths from the original development environment.
- The workflow is not currently modularized into reusable functions/classes.
- No pinned dependency file (`requirements.txt`) is included yet.
- Model comparison is performed via console metrics; artifact logging is minimal.

## Suggested Improvements

- Refactor script into reusable pipeline functions.
- Add `requirements.txt` or `environment.yml` for reproducibility.
- Add cross-validation and hyperparameter tuning.
- Save trained models and metrics to disk.
- Add tests for preprocessing and feature engineering logic.

## Acknowledgment

This project was developed as part of the IBM Data Science Professional Certificate capstone on Coursera.

