# Binary Classification Project

## Project Overview

This project develops a machine learning model to predict whether a customer is happy or unhappy based on responses to six survey questions.

The target variable is:

- `Y = 0`: Unhappy customer
- `Y = 1`: Happy customer

The six input features represent customer ratings from 1 to 5.

## Dataset

The dataset contains 126 customer responses and seven columns:

- `Y`: Customer happiness
- `X1`: Order delivered on time
- `X2`: Contents were as expected
- `X3`: Customer ordered everything they wanted
- `X4`: Customer paid a good price
- `X5`: Customer was satisfied with the courier
- `X6`: The app made ordering easy

The dataset contains no missing values. There are 69 happy customers and 57 unhappy customers.

## Project Workflow

The analysis includes:

1. Data validation and exploratory data analysis
2. Stratified training and test split
3. Comparison of classification models
4. Hyperparameter tuning
5. Evaluation on an untouched test set
6. Permutation feature importance
7. Evaluation of different feature subsets

## Models Compared

The following models were evaluated:

- Logistic Regression
- Support Vector Machine
- Random Forest
- Gradient Boosting

Repeated stratified cross-validation was used to compare the models.

## Final Model

Gradient Boosting was selected based on its cross-validation F1-score.

The final test results were:

| Metric | Result |
|---|---:|
| Accuracy | 73.1% |
| Precision | 66.7% |
| Recall | 100% |
| F1-score | 0.800 |

## Feature Selection

The most useful features were:

- `X1`: Order delivered on time
- `X6`: App made ordering easy

The combination of `X1` and `X6` produced the strongest compact feature subset.

The remaining questions may be candidates for removal. However, this is only an initial finding because the dataset contains 126 observations. More customer responses should be collected before permanently changing the survey.

## Project Structure

```text
wW3Y6TuEBcZyqkBS/
├── data/
│   └── ACME-HappinessSurvey2020.xlsx
├── src/
│   └── happy_customers_analysis.py
├── outputs/
│   ├── confusion_matrix.png
│   ├── data_overview.png
│   ├── feature_importance.png
│   ├── feature_importance.csv
│   ├── feature_subset_results.csv
│   ├── final_summary.csv
│   └── model_comparison.csv
├── .gitignore
├── README.md
└── requirements.txt
