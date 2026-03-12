# Churn-Recommendation-Project

Overview

Customer churn is one of the most critical problems faced by subscription-based businesses. Losing existing customers directly impacts revenue and long-term growth.

This project builds an end-to-end Machine Learning pipeline to:

Predict customer churn probability

Segment customers into risk levels

Generate actionable retention recommendations

Estimate potential business impact

Instead of focusing only on prediction accuracy, this project emphasizes business value, interpretability, and actionable insights.

Project Objectives

The main objectives of this project are:

Build a machine learning model to predict customer churn.

Identify the most important factors influencing churn.

Segment customers based on their churn risk.

Provide personalized recommendations to reduce churn.

Simulate business impact using retention strategies.

Dataset

This project uses the Telco Customer Churn dataset.

The dataset contains customer information including:

Demographic details

Account information

Service usage

Billing information

Churn status

Key Variables
Feature	Description
tenure	Number of months the customer stayed
MonthlyCharges	Monthly billing amount
TotalCharges	Total amount billed
Contract	Contract type
InternetService	Type of internet service
PaymentMethod	Payment method used
Churn	Target variable (Yes/No)
Project Workflow

The project follows a complete Machine Learning lifecycle.

Data Collection
↓
Data Cleaning & Preprocessing
↓
Exploratory Data Analysis
↓
Feature Engineering
↓
Model Training
↓
Model Evaluation
↓
Model Interpretation
↓
Churn Risk Segmentation
↓
Recommendation System
↓
Business Impact Analysis
↓
Model Saving
1. Data Collection

The dataset was loaded using Pandas and inspected to understand its structure.

Steps performed:

Loaded dataset

Examined dataset shape

Checked column names

Reviewed data types

Identified missing values

Purpose:
To understand the dataset before preprocessing.

2. Data Cleaning & Preprocessing

Data preprocessing ensures the dataset is suitable for machine learning.

Key steps

Handling Missing Values

Some records contained missing values in the TotalCharges column.
These were converted to numeric and missing values were filled.

Dropping Unnecessary Columns

The customerID column was removed because it does not provide predictive value.

Encoding Target Variable

The churn column was converted from text to numeric:

Yes → 1
No → 0

Encoding Binary Features

Binary categorical columns were mapped to numeric values.

Yes → 1
No → 0

Handling Service Columns

Values such as "No internet service" were mapped to 0 to simplify analysis.

3. Exploratory Data Analysis (EDA)

Exploratory analysis helps identify patterns and relationships in the data.

Key analyses performed:

Churn distribution analysis

Churn by contract type

Churn vs tenure

Churn vs monthly charges

Churn by service features

Key Observations

Month-to-month customers show higher churn rates.

Customers with higher monthly charges tend to churn more.

Customers with longer tenure have lower churn probability.

Customers using multiple services are less likely to churn.

EDA helps guide feature engineering and model design.

4. Feature Engineering

Feature engineering was performed to create more meaningful predictors.

Tenure Group

Customers were grouped by tenure length:

0-12 months
13-24 months
25-48 months
49+ months

This helps capture customer lifecycle stages.

Monthly Charge Group

Monthly charges were segmented into:

Low
Medium
High

This represents pricing tiers.

Service Engagement Score

A new feature called ServiceCount was created.

It represents the number of services a customer uses.

ServiceCount = Sum of service features

Customers using more services typically show stronger engagement and lower churn risk.

5. Feature Selection

After feature engineering, some raw columns were removed because their information was already captured by engineered features.

Examples:

tenure

MonthlyCharges

Individual service columns

This reduces redundancy and improves model generalization.

6. Encoding Categorical Variables

Machine learning models require numerical input.

Categorical columns were converted using One-Hot Encoding.

Example:

Contract
Month-to-month
One year
Two year

becomes

Contract_OneYear
Contract_TwoYear

To avoid multicollinearity, the first category was dropped.

7. Train-Test Split

The dataset was split into training and testing sets.

80% Training Data
20% Testing Data

Stratified splitting was used to preserve class distribution.

8. Feature Scaling

StandardScaler was applied to standardize numerical features.

Standardization ensures features have:

Mean = 0

Standard deviation = 1

This is important for models like Logistic Regression.

9. Model Training

A Logistic Regression model was used as the baseline model.

Why Logistic Regression?

Interpretable

Efficient

Works well for binary classification

Handling Class Imbalance

The dataset was imbalanced, so class weighting was applied:

class_weight = "balanced"

This prevents the model from favoring the majority class.

10. Model Evaluation

The model was evaluated using several metrics.

Metrics Used
Metric	Purpose
Accuracy	Overall correctness
Precision	Correct positive predictions
Recall	Ability to detect churn
F1 Score	Balance between precision & recall
ROC-AUC	Overall classification performance
Results
Recall ≈ 78%
ROC-AUC ≈ 0.83

These results indicate good churn detection capability.

11. Model Interpretation

Logistic regression coefficients were analyzed to identify:

Top Churn Drivers

Examples:

Month-to-month contracts

High monthly charges

Certain internet services

Retention Indicators

Examples:

Long-term contracts

Higher tenure

Higher service engagement

Understanding these factors helps design retention strategies.

12. Churn Risk Segmentation

Predicted churn probabilities were converted into risk levels.

High Risk   → probability ≥ 0.7
Medium Risk → probability ≥ 0.4
Low Risk    → probability < 0.4

This makes the model easier to use for business decision making.

13. Recommendation System

A rule-based recommendation engine was developed to generate customer-specific actions.

Example Recommendations

High Risk Customers:

Offer long-term contract discounts

Provide monthly charge discounts

Recommend service bundles

Encourage auto-pay enrollment

Medium Risk Customers:

Send personalized retention campaigns

Suggest additional services

Low Risk Customers:

Offer loyalty rewards

Upsell premium services

14. Business Impact Simulation

Retention success rates were assumed for each risk segment:

High Risk → 40%
Medium Risk → 25%
Low Risk → 10%

Using these assumptions, the model estimates:

Expected retained customers

Potential churn reduction percentage

This step connects machine learning predictions with business outcomes.

15. Model Saving

The trained model and scaler were saved using Joblib.

churn_model.pkl
scaler.pkl

This allows future predictions without retraining the model.

Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

Joblib

Project Structure
churn-prediction-project
│
├── data
│   ├── raw
│   └── processed
│
├── notebooks
│   ├── data_preprocessing.ipynb
│   └── model_training.ipynb
│
├── models
│   ├── churn_model.pkl
│   └── scaler.pkl
│
├── README.md
Key Takeaways

This project highlights that Machine Learning models should not stop at prediction accuracy.

Real value comes from:

Model interpretability

Business alignment

Actionable recommendations

Impact estimation

Combining predictive analytics with business strategy creates practical and scalable solutions.

Future Improvements

Potential improvements include:

Testing additional models (Random Forest, XGBoost)

Hyperparameter tuning

Deploying the model using APIs

Building a dashboard for churn monitoring
