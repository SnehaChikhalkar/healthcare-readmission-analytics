# Predicting 30-Day Hospital Readmission Using Explainable Machine Learning

## Project overview
This academic Healthcare Analytics mini-project compares machine-learning models for identifying hospital encounters associated with readmission within 30 days.

## Objectives
- Prepare and inspect the dataset.
- Compare Logistic Regression and Random Forest.
- Evaluate precision, recall, F1-score, F2-score and ROC-AUC.
- Explore Random Forest feature importance and SHAP explanations.
- Examine how changing the classification threshold affects recall and precision.

## Methodology
1. Data inspection and missing-value handling.
2. Binary target definition: `<30` is positive; `>30` and `NO` are negative.
3. Numerical imputation/scaling and categorical imputation/one-hot encoding.
4. Patient-grouped train/test split to avoid placing the same patient in both sets.
5. Logistic Regression and Random Forest model training.
6. Threshold selection on a validation split, followed by held-out test evaluation.
7. Feature-importance and SHAP analysis.

## Selected results
| Model | Precision | Recall | F1-score | F2-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression (0.50) | 0.1546 | 0.5328 | 0.2397 | 0.3578 | 0.6289 |
| Random Forest (0.50) | 0.1654 | 0.5253 | 0.2516 | 0.3660 | 0.6506 |
| Tuned Logistic Regression (0.35) | 0.1236 | 0.8350 | 0.2153 | 0.3881 | 0.6303 |

The tuned Logistic Regression has the highest recall and F2-score in this comparison, but its precision is lower and it generates many false positives. Random Forest has the highest ROC-AUC among these runs. These are experimental results, not proof of clinical usefulness.

## Repository contents
- `Healthcare_Readmission_Analytics.ipynb` — Google Colab/Jupyter notebook.
- `final_model_results.csv` — model metrics.
- `images/` — plots extracted from the notebook outputs, where available.
- `requirements.txt` — Python package list.

## Limitations
- The dataset represents historical U.S. hospital data from 1999–2008.
- Discrimination is moderate, and external validation has not been performed.
- Some features, such as discharge information, are only available at or near discharge; therefore, this workflow should be described as prediction at/near discharge, not at admission.
- Feature importance and SHAP associations are not causal explanations.
- The model is not clinically validated and must not be used for real patient-care decisions.

## Dataset and privacy note
The dataset is not included in this repository. Confirm with the course instructor that the dataset is approved for this project and follow the applicable dataset terms. Do not upload patient-level data, credentials, or private files.

## Reproducibility
Open the notebook in Google Colab or Jupyter and run the cells in order after obtaining the approved dataset and installing the packages listed in `requirements.txt`. The notebook currently contains Google Colab-specific setup cells, so review dataset-path cells before running it in another environment.

## Disclaimer
For academic learning and research only; not a clinically validated decision-support system.
