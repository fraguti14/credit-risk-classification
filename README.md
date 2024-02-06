# credit-risk-classification
This is a repository for "credit-risk-classification"

# Overview of the Analysis

The primary goal of this analysis was to develop a predictive model to assess the creditworthiness of borrowers for a peer-to-peer lending services company. By leveraging historical lending data, the model aims to identify whether a loan is at high risk of defaulting or is healthy. This task is crucial for financial institutions to minimize losses due to bad loans and to determine the risk associated with lending activities.

The analysis used a dataset with financial attributes of borrowers and their loans, focusing on the loan_status column to predict loan health (0) or high default risk (1), including credit history, loan amounts, interest rates, income levels, and other financial details.

The target variable for prediction was loan_status, with other columns as features for model training. The value_counts of loan_status showed the distribution of healthy vs. high-risk loans, indicating dataset balance or imbalance.

### Stages of the Machine Learning Process
- **Data Preparation:** Loaded lending data into a table, separating the target outcome and other data.
- **Data Splitting:** Divided the data into training and testing groups to check the model on new data.
- **Model Training:** Used a simple model good for yes/no predictions, trained with the training data.
- **Prediction and Evaluation:** Made predictions on new data and checked how well the model did using simple metrics to understand its accuracy and performance.

### Methods Used:
- **Logistic Regression:** Chosen for its strength in yes/no predictions and for estimating the likelihood of outcomes, showing how confident the model is in its predictions.
- **Train-Test Split:** Used to verify the model's accuracy on unseen data by dividing the dataset into parts for training and testing.
- **Evaluation Metrics:** Utilized to gauge the model's accuracy through a confusion matrix and classification report, focusing on its success in identifying high-risk and healthy loans, precision, recall, and F1-scores.


# Results

### Machine Learning Model 1:
- The logistic regression model performs very well in predicting both the healthy loans and 1 high-risk loans, as indicated by the metrics provided:

  - **Healthy Loans (0) Pecision & Recall:**
      - **Precision: 1.00** - extremely accurate with very few false positives (102 out of 18,765 misclassified).
      - **Recall: 0.99** - successfully identifies 99% of healthy loans, missing only 56.
  - **High-Risk Loans (1) Pecision & Recall:**
    - **Precision:** 0.85 - correct 85% of the time when predicting high-risk loans.
    - **Recall:** 0.91 - identifies 91% of actual high-risk loans, missing 56 out of 619.
  - **Balanced Accuracy Score:** 0.952 - indicates strong performance across both classes despite significant class imbalance (18,765 healthy vs. 619 high-risk loans).
  - **F1-Scores:** 1.00 for healthy loans and 0.88 for high-risk loans, indicating strong performance. Overall Accuracy: 0.99 - 99% of all model predictions are correct.
  - **Confusion Matrix:**
      - Healthy loans correctly identified (**True negative**): 18663
      - High-risk loans correctly identified (**True prositive**): 563
      - Healthy loans incorrectly labeled as high-risk (**False positive**): 102
      - High-risk loans missed (**False negative**): 56



### Machine Learning Model 2:
- The model is highly effective, especially in identifying high-risk loans, demonstrating the success of using oversampling to account for class imbalance.

  - **Balanced Accuracy Score:** 0.9937, indicating excellent overall performance in predicting both classes.
  - **Confusion Matrix:**
    - Healthy loans (0): 18649 correctly identified, 116 misclassified as high risk.
    - High-risk loans (1): 615 correctly identified, 4 misclassified as healthy.
  -  **Precision:**
      - Class 0 (healthy loans): Nearly perfect.
      - Class 1 (high-risk loans): 0.84, indicating 84% of high-risk predictions are correct.
    -  **Recall:**
      - Class 0: Nearly perfect.
      - Class 1: 0.99, capturing 99% of actual high-risk loans.
    - **F1-Score:**
      - Class 0: Perfect score of 1.00.
      - Class 1: 0.91, indicating a strong balance between precision and recall for high-risk loans.
    - **Overall Accuracy:** 0.99, with high effectiveness in identifying both healthy and high-risk loans.


# Summary

Both machine learning models did a great job at predicting loan risks, but they have small differences:

- Model 1 is very accurate in picking out both safe and risky loans, with almost perfect scores across the board and 99% overall accuracy. It's great at finding safe loans and also good at spotting risky ones.

- Model 2 is slightly better at dealing with the challenge of having more safe loans than risky ones, with a very high accuracy of 99% and especially good at identifying risky loans.

**Recommendation:**
- Choose Model 2 if finding risky loans is the top priority because it's slightly better at catching these without missing many. It's more suited for reducing bad loans and managing risk.

