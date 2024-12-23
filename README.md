# Credit Card Fraud Detection Pipeline

## Overview
Credit card fraud detection is crucial for preventing financial losses and ensuring customers are not charged for unauthorized transactions. This project aims to accurately identify fraudulent transactions in real-time while minimizing false positives. 

With the increase in online transactions, the challenge lies in processing large datasets and identifying fraud effectively.

---

## Dataset
The project uses the [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud), containing:

- Transactions made by European cardholders in September 2013.
- A total of **284,807 transactions**, including **492 fraud cases** (~0.172%).
- Features derived from PCA, except for `Time` and `Amount`.

### Key Features:
- **Time**: Seconds elapsed between transactions.
- **Amount**: Transaction amount.
- **Class**: Target variable (1 for fraud, 0 otherwise).

---

## Tools and Libraries
- **Python**: Primary programming language.
- **Pandas**: Data manipulation and preprocessing.
- **NumPy**: Numerical computations.
- **Scikit-learn**: Count vectorization and cosine similarity.
- **Imbalanced-learn**: Data resampling methods (e.g., SMOTE, NearMiss).

---

## Methodology

### 1. Data Analysis
- Identified the skewness in the dataset.
- Normalized and scaled data using `RobustScaler`.

### 2. Handling Imbalanced Data
- **Outlier Removal**: Removed extreme outliers from features like `V10`, `V12`, and `V14`.
- **Under-Sampling**: Balanced the dataset using random under-sampling and the NearMiss technique.
- **Over-Sampling**: Used SMOTE (Synthetic Minority Oversampling Technique) to increase the minority class size.

### 3. Model Implementation
- Built a pipeline with NearMiss / SMOTE and logistic regression.

### 4. Evaluation
Evaluated models using metrics such as:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**
- **AUC (Area Under Curve)**

---

## Key Results
- Correlation analysis revealed:
  - **Negative Correlations**: `V10`, `V12`, `V14`, and `V17` indicate higher fraud likelihood at lower values.
  - **Positive Correlations**: `V2`, `V4`, `V11`, and `V19` indicate higher fraud likelihood at higher values.

- Final model performance achieved balanced metrics across all evaluation criteria.

| Technique               | Accuracy | Recall  |
| :---------------------: | :------: | :-----: |
| Random Undersampling    | 0.95767  | 0.91209 |
| NearMiss Undersampling  | 0.95767  | 0.91209 |
| SMOTE Undersampling     | 0.95767  | 0.91209 |

---

## Installation and Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/PratiekSonare/CreditCardFraudDetection.git
