# Interpretable Credit Risk ML

A credit scoring project aimed at predicting customer creditworthiness for a bank, focusing on interpretable machine learning models.

## Project Objective

The goal is to develop a classification model to predict whether a customer is creditworthy (`TARGET = 1`) or not (`TARGET = 0`), based on a variety of socio-demographic and economic features.

A bonus requirement was to ensure the model can provide interpretable insights — that is, explain why a customer was denied a credit card.

## Dataset Description

The dataset consists of anonymized data from clients who applied for a credit card and either paid their installments regularly (creditworthy) or not.

Each row represents a single applicant. The `TARGET` column is the label to be predicted.

### Features

| Feature | Description |
|--------|-------------|
| `ID` | Unique customer identifier |
| `CODE_GENDER` | Customer gender |
| `FLAG_OWN_CAR` | Owns a car (1 = yes, 0 = no) |
| `FLAG_OWN_REALTY` | Owns real estate |
| `CNT_CHILDREN` | Number of children |
| `AMT_INCOME_TOTAL` | Annual income |
| `NAME_INCOME_TYPE` | Income type |
| `NAME_EDUCATION_TYPE` | Education level |
| `NAME_FAMILY_STATUS` | Marital status |
| `NAME_HOUSING_TYPE` | Type of housing |
| `DAYS_BIRTH` | Days since birth |
| `DAYS_EMPLOYED` | Days since employment began (positive values = unemployed) |
| `FLAG_MOBIL` | Has a mobile phone |
| `FLAG_WORK_PHONE` | Has a work phone |
| `FLAG_PHONE` | Has a phone number |
| `FLAG_EMAIL` | Has an email address |
| `OCCUPATION_TYPE` | Job type |
| `CNT_FAM_MEMBERS` | Number of family members |
| `TARGET` | 1 = creditworthy, 0 = not creditworthy |

## Models Trained

- Logistic Regression: Interpretable linear model, used as baseline. Feature coefficients were examined.
- Decision Tree: Configured with `class_weight="balanced"` to handle class imbalance. Feature importances and full tree plotted for interpretability.
- Random Forest: Ensemble model to improve performance and stability. Feature importance analyzed. Tree visualization omitted due to large number of trees.
- K-Nearest Neighbors (K-NN): Non-interpretable model used for performance comparison only.

## Evaluation Metrics

All models were evaluated using:
- Accuracy
- Precision, Recall, F1-score (for both classes)
- Confusion Matrix (on train and test sets)
- Feature importance analysis
- Interpretability insights (where applicable)

## Notes on Interpretability

- Decision Trees and Logistic Regression provided valuable, interpretable insights.
- The top features across models consistently included:
  - `AMT_INCOME_TOTAL`
  - `DAYS_BIRTH`
  - `DAYS_EMPLOYED`
- Logistic Regression showed that being a pensioner (`OCCUPATION_TYPE_Pension`) or having a pension income (`NAME_INCOME_TYPE_Pensioner`) significantly reduced the probability of being classified as creditworthy.

## Final Thoughts

This project emphasizes the balance between performance and model interpretability in credit risk scoring — a crucial factor in financial decision-making.

