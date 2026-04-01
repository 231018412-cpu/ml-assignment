
# Bank Marketing Prediction using Logistic Regression

## 1. Introduction
 This project uses the Bank Marketing dataset to predict whether a customer will subscribe to a term deposit. The dataset contains customer details like age, job, balance, and previous campaign interactions. We apply Logistic Regression to model the likelihood of subscription. The goal is to identify key factors that influence customer decisions and improve marketing efficiency.
**Dataset:** 45,211 entries, 17 attributes  

---

## 2. Approach
1. Load and explore the dataset.  
2. Preprocess the data:
   - Handle categorical variables with encoding.  
   - Handle missing or inconsistent values.  
3. Split the dataset into training (80%) and testing (20%) sets.  
4. Train a Logistic Regression model.  
5. Evaluate model performance using accuracy, confusion matrix, and classification metrics.  
6. Analyze feature importance to determine which factors influence customer subscription.  

---

## 3. Methodology

### Data Preprocessing
- Checked for null/missing values.  
- Encoded categorical variables using **Label Encoding / One-Hot Encoding**.  
- Defined features (`X`) and target (`y`).  
- Target mapping: `No = 0`, `Yes = 1`.  

### Model Training
- Split data: 80% train, 20% test.  
- Used **Logistic Regression** classifier.  
- Trained the model on the training set and predicted on the test set.  

### Evaluation Metrics
- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1-Score**  
- **Confusion Matrix**  

---
## 4. Findings 

### Model Performance

| Metric | Value |
|--------|-------|
| Accuracy | 0.81 |
| Total Test Samples | 9,043 |

### Classification Report

| Class | Precision | Recall | F1-Score | Support |
|-------|----------|--------|----------|--------|
| 0 (No) | 0.95 | 0.83 | 0.88 | 7,952 |
| 1 (Yes) | 0.35 | 0.69 | 0.46 | 1,091 |

### Confusion Matrix

| Actual \ Predicted | No (0) | Yes (1) |
|------------------|---------|---------|
| No (0) | 6,567 | 1,385 |
| Yes (1) | 342 | 749 |

### Top Feature Importance

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

**Explanation:**  
- `duration` (call duration) is the most influential feature.  
- Recent contacts (`pdays`) and previous campaign success (`previous`) increase subscription likelihood.  
- Some features like `education` and `default` have negative influence on prediction.  



## 5. Conclusion
The Logistic Regression model achieved 81% accuracy, performing well at predicting customers who will not subscribe, but less precise for those who will. Call duration, previous contacts, and campaign history were the most important features. The model can help banks target potential subscribers more effectively. Further improvements could include feature engineering, scaling, and using advanced models like Random Forest or XGBoost.  

