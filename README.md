# AML Account Risk Classification

Machine learning project for identifying suspicious financial accounts based on transaction behavior using synthetic AML data.

## Overview

This project explores how machine learning can support Anti-Money Laundering (AML) analysis by identifying accounts with potentially suspicious activity.

Using synthetic financial transaction data from AMLSim, I developed an account-level classification approach based on behavioral features derived from transaction records.

## Dataset

The analysis includes:
- 10,000 accounts.
- 1,323,234 transactions.
- 1,685 suspicious accounts (16.85%).

The dataset was synthetically generated using AMLSim. The fraud label (`IS_FRAUD`) was used as the target variable.

## Methodology

**Feature Engineering**

I developed six account-level behavioral features:
- Number of sent and received transactions.
- Average sent and received transaction amounts.
- Number of unique senders and receivers.

**Model Development**

I implemented and compared two classification models:
- Logistic Regression with feature standardization and balanced class weights.
- Random Forest with balanced class weights.

A stratified train-test split (80/20) was used for model evaluation.

## Results

| Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Accuracy | 0.748 | 0.907 |
| Precision | 0.340 | 0.927 |
| Recall | 0.528 | 0.487 |
| F1-score | 0.414 | 0.638 |
| ROC-AUC | 0.710 | 0.901 |

Random Forest achieved the best overall performance, particularly in Precision, F1-score, and ROC-AUC. However, Logistic Regression achieved slightly higher Recall.

Feature importance analysis identified the number of unique receivers and average sent transaction amount as the two most influential features in the Random Forest model.

## Limitations and Future Work

The models identified approximately half of the suspicious accounts. The analysis also relies on synthetic data and a limited set of behavioral features.

Potential improvements include:
- Developing temporal and transaction velocity features.
- Exploring XGBoost and LightGBM.
- Hyperparameter tuning with cross-validation.
- Evaluating different classification thresholds to improve Recall.

## Tools

Python · Pandas · NumPy · Scikit-learn · Matplotlib · Seaborn · Jupyter Notebook

## Repository Structure

```text
AML-transaction-fraud-detection/
│
└── AML_Account_Risk_Classification.ipynb
```

## Author

Aurora Mata Sánchez

[GitHub](https://github.com/amata31)
