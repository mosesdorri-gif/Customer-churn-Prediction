
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

### 3. Feature Engineering

Additional behavioural features were created to better represent customer financial activity.

Examples include:

- Payment-to-balance ratio
- Purchase-to-limit ratio
- Payment-to-purchase ratio
- Available credit
- Balance-to-purchase ratio

These features were designed to capture customer payment behaviour, credit utilization, and spending patterns.

### 4. Machine Learning

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
