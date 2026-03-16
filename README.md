# Credit Risk Prediction Engine

An end-to-end machine learning pipeline for predicting loan default risk using borrower financial data.  
This project builds a production-style credit risk model that identifies whether a loan is likely to become **bad (default / charged off)** or **good (fully paid)**.

The system performs data cleaning, feature engineering, leakage prevention, model training, and threshold optimization to build a reliable credit risk prediction framework.

---

## Project Objective

Financial institutions need reliable systems to assess the risk of lending money.  
This project aims to build a machine learning model that can predict the probability of loan default using borrower and loan characteristics.

The final model can be used to:

- Identify high-risk borrowers
- Assist credit approval decisions
- Improve portfolio risk management
- Reduce financial losses from loan defaults

---

## Dataset

The dataset contains historical loan records with borrower information, loan attributes, and repayment outcomes.

Example features include:

- Loan amount
- Interest rate
- Employment length
- Annual income
- Debt-to-income ratio
- Home ownership status
- Credit history length
- Loan term
- Loan status

Target variable:
target_bad
1 = Bad Loan (Default / Charged Off)
0 = Good Loan (Fully Paid)


---

## Project Pipeline

The project follows a structured machine learning workflow.


Raw Loan Data
↓
Data Cleaning
↓
Missing Value Handling
↓
Feature Engineering
↓
Data Leakage Removal
↓
Exploratory Data Analysis
↓
Train/Test Split
↓
Model Training
↓
Threshold Optimization
↓
Model Evaluation


---

## Data Preprocessing

The dataset required extensive cleaning and preprocessing.

Key preprocessing steps include:

- Standardizing column names
- Handling missing values
- Creating missing value indicator features
- Converting categorical variables
- Parsing date features
- Removing constant and sparse columns
- Removing highly correlated features
- Eliminating data leakage variables

Special attention was given to removing **post-loan outcome features** such as:

- recovery fees
- total payments received
- last payment date

These features would otherwise leak future information into the model.

---

## Feature Engineering

Several transformations were applied to improve model performance.

Examples include:

- Numeric extraction from loan terms
- Missing value indicator variables
- Date conversion for credit history features
- Binary encoding of categorical flags
- Removal of redundant correlated variables

---

## Machine Learning Models

Two machine learning models were implemented and compared.

### Logistic Regression

Used as a baseline model.

Advantages:

- interpretable
- commonly used in financial risk models
- stable performance

Class imbalance was handled using:

class_weight = "balanced"



---

### Gradient Boosting Model

A more powerful non-linear model was trained using:

HistGradientBoostingClassifier



Advantages:

- handles complex feature relationships
- strong performance on tabular data
- efficient training

---

## Threshold Optimization

Instead of using the default probability threshold of 0.5, multiple thresholds were evaluated to improve classification performance.

This is important in credit risk modeling because missing a bad borrower can be costly.

Thresholds tested:


0.05
0.10
0.15
0.20
0.25
...
0.50


The optimal threshold was selected based on precision, recall, and F1 score.

---

## Model Evaluation

The model was evaluated using standard classification metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC AUC
- Confusion Matrix

Evaluation ensures the model balances:

- identifying risky borrowers
- minimizing false positives

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---


---

## Key Learnings

This project demonstrates how to build a robust credit risk model by:

- handling messy real-world financial data
- preventing data leakage
- engineering meaningful features
- comparing machine learning models
- optimizing decision thresholds

These techniques are widely used in fintech, banking, and lending platforms.

---

## Future Improvements

Potential enhancements include:

- adding cross-validation
- model explainability using SHAP values
- feature selection using Information Value (IV)
- hyperparameter tuning
- probability calibration
- deployment as an API service

---

## Author

This project was built as part of a machine learning portfolio to demonstrate real-world credit risk modeling techniques.
