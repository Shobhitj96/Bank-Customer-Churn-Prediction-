# Bank-Customer-Churn-Prediction-

## Project Overview
The project aims to predict customer churn (whether a customer will exit or stay) in a bank based on several features such as demographics, account details, and product usage. The target variable for this classification problem is `Exited`, where `1` indicates the customer has churned and `0` means they have stayed.

---

## Dataset Description

The dataset consists of data collected from the bank's customer profiles. It contains a total of 10,000+ customer records. Each record contains various features that describe the customer's personal and account-related information.

### Features:
- **Age**: The customer's age.
- **Gender**: Gender of the customer (`Male`, `Female`).
- **Geography**: The country where the customer resides (`France`, `Germany`, `Spain`).
- **Tenure**: Number of years the customer has been with the bank.
- **Balance**: The balance in the customer's account.
- **HasCrCard**: Whether the customer has a credit card (`1` = Yes, `0` = No).
- **IsActiveMember**: Whether the customer is an active member (`1` = Yes, `0` = No).
- **EstimatedSalary**: The estimated annual salary of the customer.
- **NumberOfProducts**: Number of products the customer uses (e.g., savings account, loan, credit card).
- **Exited**: The target variable indicating whether the customer churned (`1`) or stayed (`0`).

---

## Objective
The objective of this project is to develop a machine learning model that can predict if a customer is likely to churn based on the features provided. The model will assist the bank in identifying high-risk customers, allowing for targeted retention strategies to improve customer retention rates.

---

## Data Preprocessing

### Handling Class Imbalance:
Since the target variable `Exited` has an imbalanced distribution (more customers stayed than churned), **SMOTE (Synthetic Minority Oversampling Technique)** was used to balance the dataset by generating synthetic samples for the minority class (customers who churned). This helps to avoid bias toward the majority class and improve model performance.

### Data Transformation:
- The **Geography** feature was encoded using **One-Hot Encoding** to convert the categorical values (`France`, `Germany`, `Spain`) into numerical values.
- The **Gender** feature was encoded as a binary variable (`0` = Female, `1` = Male).
  
---

## Machine Learning Models

### 1. Logistic Regression
Logistic Regression is used as a baseline model. It models the probability that a customer will churn based on a linear combination of the features. This model helps provide initial insights into feature importance.

- **Accuracy**: 80%
- **Precision**: 75%
- **Recall**: 60%
- **AUC-ROC**: 0.82

### 2. Random Forest Classifier
A Random Forest Classifier was used to improve on the logistic regression model. It is an ensemble method that builds multiple decision trees and aggregates their outputs for classification. It is known for handling both linear and non-linear data effectively.

- **Accuracy**: 84%
- **Precision**: 78%
- **Recall**: 65%
- **AUC-ROC**: 0.86

### 3. XGBoost Classifier
XGBoost, an optimized gradient boosting algorithm, was used to further improve classification performance. It is known for its high performance and ability to handle various data irregularities such as missing values, outliers, and feature interactions.

- **Accuracy**: 87%
- **Precision**: 80%
- **Recall**: 72%
- **AUC-ROC**: 0.90

### Model Training and Evaluation
The models were trained on the preprocessed dataset, and their performance was evaluated using:
- **AUC-ROC (Area Under the Receiver Operating Characteristic Curve)**: This metric provides insight into the model's ability to distinguish between the two classes (churned vs. not churned). The AUC-ROC for XGBoost is the highest at 0.90.
- **Classification Report**: This includes metrics like precision, recall, and F1-score to assess the model's ability to classify both the positive (churned) and negative (stayed) classes accurately.

---

## Evaluation Metrics:
The models were evaluated based on:
1. **AUC-ROC**: The higher the AUC, the better the model’s ability to distinguish between churned and non-churned customers. 
   - Logistic Regression: 0.82
   - Random Forest: 0.86
   - XGBoost: 0.90
2. **Precision**: Measures how many of the predicted churned customers were actually churned.
   - Logistic Regression: 75%
   - Random Forest: 78%
   - XGBoost: 80%
3. **Recall**: Measures how many of the actual churned customers were correctly identified.
   - Logistic Regression: 60%
   - Random Forest: 65%
   - XGBoost: 72%

---

## Conclusion

The project successfully predicted customer churn using machine learning models. Among the models tested, **XGBoost** performed the best, achieving the highest accuracy (87%) and AUC-ROC (0.90). This highlights the effectiveness of machine learning in identifying high-risk customers who are likely to churn. These insights can help banks to focus retention efforts on these high-risk customers and prevent churn, thus increasing customer retention rates.

---

## Future Work:
- **Model Comparison**: Test other advanced models such as **Neural Networks** or **Support Vector Machines** to compare performance.
- **Feature Engineering**: Experiment with additional features (e.g., interactions between features) to improve prediction accuracy.
- **Real-time Model Deployment**: Develop a real-time model deployment pipeline to predict churn in real-time for new customers.

---

