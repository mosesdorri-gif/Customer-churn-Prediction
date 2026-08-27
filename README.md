
# Customer Churn Prediction

## Overview

This project develops a machine learning model to predict whether a customer is likely to churn based on customer demographics, account information, transaction behaviour, and service usage.

The goal is to identify customers at higher risk of leaving so that businesses can better understand churn drivers and prioritize potential retention strategies.

## Objectives

- Explore and clean customer data
- Perform exploratory data analysis (EDA)
- Engineer features related to customer behaviour and account activity
- Identify factors associated with customer churn
- Train and evaluate machine learning classification models
- Compare model performance using appropriate evaluation metrics
- Interpret model predictions and identify important churn drivers

## Dataset

The dataset contains customer-level information including variables related to:

- Customer demographics
- Account tenure
- Product usage
- Purchase behaviour
- Account balances
- Credit limits
- Payment activity
- Customer status

The target variable is customer churn, formulated as a binary classification problem.

## Methodology

### 1. Data Preparation

The dataset was inspected for:

- Missing values
- Duplicate observations
- Inconsistent data
- Outliers
- Categorical variables

Categorical variables were encoded and numerical variables were prepared for modelling.

### 2. Exploratory Data Analysis

Exploratory analysis was performed to understand:

- Churn rates
- Customer behaviour
- Relationships between variables
- Differences between churned and retained customers

Visualizations were created using Matplotlib to identify important patterns in the data.



### 3. Machine Learning

The project treats churn prediction as a binary classification problem.

Models were trained using `scikit-learn` and evaluated using metrics including:

- ROC-AUC
- Precision
- Recall
- F1-score
- Confusion matrix

Model performance was evaluated using cross-validation to obtain a more reliable estimate of generalization performance.

## Model Performance

The final model achieved a ROC-AUC score of approximately **0.86**, indicating strong ability to distinguish between customers who churn and customers who remain.

> Results may vary depending on the train/test split, preprocessing, and model configuration.

## Feature Analysis

Feature importance and statistical analysis were used to investigate which customer characteristics contributed most to the model's predictions.

This helps move beyond simply predicting churn and provides insight into **why customers may be classified as high-risk**.
Feature importance was examined to understand which variables contributed most strongly to the model's predictions.

The most influential features were:

| Feature | Importance |
|---|---:|
| `risk_score` | 0.755 |
| `balance` | 0.096 |
| `monthly_ir` | 0.062 |
| `tenure_ye` | 0.029 |
| `customer_segment_Mass` | 0.017 |

The model placed the greatest importance on `risk_score`, which accounted for approximately **75.5% of the model's total feature importance**. `balance`, `monthly_ir`, and `tenure_ye` were the next most influential variables.

These results provide insight into which behavioural and financial variables the model relied on most heavily when making predictions.

Feature importance is used for **model interpretation rather than causal inference**; a high feature importance indicates that a variable was useful to the model but does not imply that the variable directly causes the predicted outcome.

### Key Observation

The strong contribution of `risk_score` suggests that the model's predictions are heavily driven by the underlying behavioural information captured by this variable. Further analysis using SHAP can be used to investigate how individual features influence predictions and whether higher or lower feature values push predictions toward different outcomes.



## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook

## Project Structure

```text
customer-churn-prediction/
│
├── data/
│   └── dataset.csv
│
├── notebooks/
│   └── churn_analysis.ipynb
│
├── src/
│   └── model.py
│
├── README.md
└── requirements.txt
