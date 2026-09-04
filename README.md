# Customer Churn Prediction

Machine Learning project to predict whether a telecom customer is likely to churn.

## Problem Statement

Customer churn is an important business problem for telecom companies because losing existing customers can negatively impact revenue.

The objective of this project is to build a machine learning classification model that predicts whether a customer will churn based on their demographic information, services, contract details, and billing information.

## Dataset

The project uses the Telco Customer Churn dataset.

The original dataset contains 7,043 customer records and 21 columns.

## Approach

The following approach was used:

1. Load and inspect the dataset.
2. Handle missing values.
3. Check and remove duplicate records.
4. Remove the `customerID` column.
5. Convert `TotalCharges` into numeric format.
6. Perform Exploratory Data Analysis (EDA).
7. Encode categorical variables using One-Hot Encoding.
8. Split the data into training and testing sets using an 80:20 ratio.
9. Apply feature scaling for Logistic Regression.
10. Train Logistic Regression and Random Forest models.
11. Evaluate both models using Accuracy, Precision, Recall, and F1-score.
12. Compare the models and select the best-performing model.
13. Create a prediction function for new customers.

## Exploratory Data Analysis

The following visualizations were created:

- Churn Distribution
- Feature vs Churn
- Correlation Heatmap

## Key Insights

- The dataset contains more non-churn customers than churn customers, indicating class imbalance.
- Customers with shorter tenure tend to have a higher likelihood of churn.
- Higher monthly charges are associated with increased churn.
- Customers with longer-term contracts tend to have lower churn.

## Data Preprocessing

- Removed `customerID` because it is an identifier and does not provide useful predictive information.
- Converted `TotalCharges` from object to numeric.
- Handled missing values.
- Removed duplicate records.
- Applied One-Hot Encoding to categorical variables.
- Used `StandardScaler` for Logistic Regression.

## Models Used

### Logistic Regression

Logistic Regression was used as the baseline model because customer churn is a binary classification problem. It is simple, interpretable, and provides probability estimates.

### Random Forest

Random Forest was selected as the second model because it can capture non-linear relationships and interactions between features. Feature scaling is not required for tree-based models.

## Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score

## Results

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 0.794 | 0.597 |0.543 | 0.568 |
| Random Forest | 0.789 | 0.601 | 0.474 | 0.530 |


## Best Model

The final model was selected by comparing Accuracy, Precision, Recall, and F1-score.

Particular attention was given to Recall and F1-score because correctly identifying customers who are likely to churn is important for customer retention.

## Prediction

A prediction function was created that takes customer information as input and predicts whether the customer is likely to churn.

The function also provides the probability of churn.

## Limitations

- The dataset contains class imbalance.
- The model is trained on a specific telecom dataset and may not generalize perfectly to other companies.
- The dataset may not contain all factors influencing customer churn, such as customer satisfaction, complaints, or competitor offers.
- Model performance may vary when applied to new real-world data.

## Future Improvements

- Perform hyperparameter tuning using GridSearchCV or RandomizedSearchCV.
- Evaluate class imbalance techniques such as SMOTE or class weights.
- Perform feature engineering.
- Use cross-validation for more reliable evaluation.
- Try additional models such as XGBoost and Gradient Boosting.
- Tune the classification probability threshold according to business requirements.

## Project Structure

```text
Customer-Churn-Prediction/
│
├── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── Churn_Prediction.ipynb
├── README.md
└── requirements.txt
