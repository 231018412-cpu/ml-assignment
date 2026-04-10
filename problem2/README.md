###  Bank Marketing Prediction 

# Introduction:
A banking institution aims to predict whether a customer will subscribe to a **term deposit** based on their demographic and banking behavior data. This is a **binary classification problem**, where the target variable indicates:

* `yes` → Customer subscribed
* `no` → Customer did not subscribe

Dataset Description:
The dataset used is the **Bank Marketing Dataset**, which contains information collected from past marketing campaigns.

Features include:

>**Demographics**: age, job, marital status, education.

> **Financial info**: balance, housing loan, personal loan.

> **Campaign-related**: contact type, duration, previous outcomes.

>**Target variable**:
  >`y` → subscription to term deposit (yes/no)

# Objective:
To build a **Logistic Regression model** that predicts whether a new customer will subscribe to a term deposit.

# Methodology:
1.Data Loading:

        > Imported dataset (`bank-full.csv`).
        > Inspected structure, data types, and missing values.
        
 2.Data Preprocessing:
 Converted categorical variables using:
 
             > **Label Encoding / One-Hot Encoding**
             > Handled missing or unknown values (if present)
             > Feature scaling applied (if needed for numerical stability)

3. Exploratory Data Analysis (EDA):
   
       > Checked class distribution of target variable
       > Analyzed relationships between features and subscription
       > Identified important predictors such as:
            > call duration
            > previous campaign outcome
            > contact type

 4.Train-Test Split:
> Split dataset into:

      > **Training set (80%)**
      > **Testing set (20%)**

5.Model Building:
>Used **Logistic Regression** because:

     > Suitable for binary classification
     > Interpretable coefficients
     > Efficient on structured/tabular data

6.Model Evaluation:
>Evaluated model using:

     > Accuracy Score
     > Confusion Matrix
     > Precision, Recall, F1-score

# Results & Findings:

>Model Performance

| Metric | Value |
|--------|-------|
| Accuracy | 0.81 |
| Total Test Samples | 9,043 |

>Classification Report

| Class | Precision | Recall | F1-Score | Support |
|-------|----------|--------|----------|--------|
| 0 (No) | 0.95 | 0.83 | 0.88 | 7,952 |
| 1 (Yes) | 0.35 | 0.69 | 0.46 | 1,091 |

>Confusion Matrix

| Actual \ Predicted | No (0) | Yes (1) |
|------------------|---------|---------|
| No (0) | 6,567 | 1,385 |
| Yes (1) | 342 | 749 |

> Top Feature Importance

| Feature   | Importance |
|-----------|-----------|
| duration  | 1.96      |
| pdays     | 0.23      |
| previous  | 0.21      |
| balance   | 0.08      |
| month     | 0.08      |
| poutcome  | -0.02     |
| job       | -0.08     |
| day       | -0.10     |
| default   | -0.18     |
| education | -0.20     |



>Limitations:

     > Dataset is **imbalanced**
     > Logistic Regression assumes **linear relationships**
     > Sensitive to irrelevant or highly correlated features

>Future Improvements:

    > Apply **SMOTE / class balancing techniques**
    > Try advanced models:
       -> Random Forest
       -> XGBoost
    > Perform hyperparameter tuning.
    > Feature selection for better performance.
    
>Technologies Used:

    > Python.
    > Pandas & NumPy
    > Scikit-learn
    > Matplotlib / Seaborn

> Project Structure

```
├── bank-full.csv
├── Problem2.ipynb
├── README.md
```

# Conclusion:

Logistic Regression provides a solid baseline model for predicting customer subscription behavior. With proper preprocessing and feature engineering, the model can be further improved for real-world banking applications.



