# Bank Term Deposit Prediction

## Project Overview

This project applies machine learning classification techniques to predict whether a customer will subscribe to a bank term deposit. Using customer demographic and account-related information from the UCI Bank Marketing dataset, **multiple classification models were developed and compared** to identify the most effective approach.

The business goal is to improve the efficiency of marketing campaigns by targeting customers with a higher likelihood of subscribing, helping reduce campaign costs and improve conversion rates.

## Business Problem

The business objective is to improve the effectiveness of the bank's direct marketing campaigns by identifying customers who are most likely to subscribe to a term deposit. Using customer demographic information, previous campaign interactions, and economic indicators, the bank aims to predict the target variable y, which indicates whether a client subscribes to a long term deposit (yes) or not (no). By identifying potential subscribers before making contact, the bank can allocate marketing resources more efficiently, reduce campaign costs, and improve overall campaign success rates.

## Dataset
**Source** : UCI Machine Learning Repository - Bank Marketing Dataset
The dataset used in this study represents 17 direct marketing campaigns carried out by a Portuguese banking institution between May 2008 and November 2010. The campaigns resulted in 79,354 customer contacts, with the objective of promoting long-term deposit subscriptions. Customer responses from these campaigns form the basis for the classification problem analyzed in this project.

### Data Preparation 
The following preprocessing steps were performed:

- Selected customer-related features:
  - Age
  - Job
  - Marital Status
  - Education
  - Credit Default Status
  - Housing Loan Status
  - Personal Loan Status
- One-hot encoded categorical variables
- Converted the target variable to binary values (0/1)
- Standardized features using StandardScaler
- Applied an 80/20 stratified train-test split

## Models Evaluated

The following classifiers were compared:
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
-Support Vector Machine (SVM)

Performance was evaluated using:
- Training Accuracy
- Test Accuracy
- Training Time
- Precision, Recall, and F1-Score

 ## Key Findings

| Model       | Train Accuracy        | Test Accuracy   |
|------------|------------|-----------|
| Logistic Regression      | 88.73%  | 88.74%       |
| KNN        | 89.20%   | 87.95%        |
| Decision Tree    | 91.71%    | 86.39%    |
| SVM    | 88.76%    | 88.75%    |

Although Logistic Regression and SVM achieved the highest accuracy, further analysis showed that accuracy alone was misleading due to class imbalance. Both models primarily predicted the majority class, making F1-score a more appropriate evaluation metric.

## Model Improvement

To address class imbalance:
- Accuracy was replaced with F1-score as the primary evaluation metric.
- Logistic Regression was retrained using class_weight='balanced'.
- Hyperparameter tuning was performed using GridSearchCV.

Best Results
- Best Logistic Regression Parameter: C = 10
- Best Cross-Validated F1-Score: 0.256
- Logistic Regression outperformed both KNN and Decision Tree based on cross-validated F1-score

**Logistic Regression** was selected as the final model because it provided the best balance between predictive performance, interpretability, and computational efficiency.

## Conclusion 
Because the target variable is highly imbalanced, F1-score was used as the primary evaluation metric instead of accuracy. Logistic Regression was retrained using class_weight='balanced', which significantly improved performance on the minority class, increasing recall from 0.00 to 0.62 and improving the F1-score to 0.25. GridSearchCV was then used to tune model hyperparameters. Logistic Regression achieved the best cross-validated F1-score (0.256) with C=10, outperforming both Decision Tree (0.138) and KNN (0.130). These results indicate that Logistic Regression is the most effective classifier for this dataset and was selected as the final model.

### Limitations
Although Logistic Regression outperformed KNN and Decision Tree models, the overall F1-score remained relatively low (0.256), indicating room for improvement. The dataset's significant class imbalance and low precision for the subscriber class suggest that the model still struggles to accurately identify positive cases without producing false positives.

### Recommendations
Future work should investigate advanced techniques for handling class imbalance, including SMOTE and ensemble methods such as Random Forest or XGBoost. Additional feature engineering and a broader hyperparameter search may further improve the model's ability to identify potential subscribers while reducing false positive predictions.

## Project Outcome
This project demonstrates the importance of selecting evaluation metrics that align with the business objective. By accounting for class imbalance and optimizing for F1-score rather than accuracy, the final model more effectively identifies potential subscribers and provides actionable insights for improving bank marketing campaigns.
