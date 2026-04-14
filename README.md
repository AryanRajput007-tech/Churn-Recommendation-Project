# 📊 Customer Churn Prediction & Recommendation System

An end-to-end Machine Learning project focused on predicting customer churn, segmenting users based on risk, and generating actionable business recommendations. This project goes beyond prediction by emphasizing **interpretability, decision-making, and business impact**.

---

## 🧠 Problem Statement

Customer churn is a major challenge for subscription-based businesses. Losing customers directly impacts revenue and long-term growth.

This project aims to:
- Predict which customers are likely to churn  
- Understand key factors driving churn  
- Provide actionable recommendations to retain customers  
- Estimate the potential business impact of retention strategies  

---

## 🎯 Objectives

- Build a machine learning model to predict churn probability  
- Identify important churn-driving features  
- Segment customers into risk categories  
- Generate personalized retention strategies  
- Simulate business impact of interventions  

---

## 📊 Dataset

- **Dataset**: Telco Customer Churn Dataset  
- **Features include**:
  - Demographics  
  - Account information  
  - Service usage  
  - Billing details  
  - Churn status (target variable)  

---

## 🔄 Project Workflow

```
Data Collection
↓
Data Cleaning & Preprocessing
↓
Exploratory Data Analysis (EDA)
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
```

---

## 🧹 Data Preprocessing

- Handled missing values in `TotalCharges`  
- Removed irrelevant columns (`customerID`)  
- Encoded categorical variables (binary + one-hot encoding)  
- Converted target variable:
  - Yes → 1  
  - No → 0  
- Standardized numerical features using **StandardScaler**  

---

## 📈 Exploratory Data Analysis (EDA)

Key insights:
- Month-to-month contracts show higher churn  
- Higher monthly charges → higher churn probability  
- Longer tenure → lower churn  
- More services → lower churn risk  

---

## ⚙️ Feature Engineering

- **Tenure Groups**: (0–12, 13–24, 25–48, 49+)  
- **Monthly Charge Segments**: Low / Medium / High  
- **Service Engagement Score**:
  - `ServiceCount = number of active services`  

---

## 🤖 Model Training

- **Model Used**: Logistic Regression  
- **Why?**
  - Interpretable  
  - Efficient  
  - Suitable for binary classification  

### ⚖️ Handling Imbalance
- Used `class_weight = "balanced"`  

---

## 📊 Model Evaluation

| Metric     | Description                      |
|------------|----------------------------------|
| Accuracy   | Overall correctness              |
| Precision  | Correct positive predictions     |
| Recall     | Ability to detect churn          |
| F1 Score   | Balance of precision & recall    |
| ROC-AUC    | Overall performance              |

### 📌 Results
- **Recall** ≈ 78%  
- **ROC-AUC** ≈ 0.83  

---

## 🔍 Model Interpretation

### 🚨 Key Churn Drivers
- Month-to-month contracts  
- High monthly charges  
- Certain internet services  

### ✅ Retention Indicators
- Long-term contracts  
- Higher tenure  
- Higher service usage  

---

## 📊 Churn Risk Segmentation

Customers are segmented based on predicted probability:

- 🔴 High Risk → ≥ 0.7  
- 🟡 Medium Risk → ≥ 0.4  
- 🟢 Low Risk → < 0.4  

---

## 💡 Recommendation System

A rule-based engine generates actionable strategies:

### 🔴 High Risk
- Offer long-term contract discounts  
- Provide pricing incentives  
- Recommend bundled services  

### 🟡 Medium Risk
- Personalized retention campaigns  
- Suggest additional services  

### 🟢 Low Risk
- Loyalty rewards  
- Upsell premium services  

---

## 📈 Business Impact Simulation

Estimated retention impact:

- High Risk → 40% retention  
- Medium Risk → 25% retention  
- Low Risk → 10% retention  

Outputs:
- Expected retained customers  
- Estimated churn reduction  

---

## 💾 Model Saving

- `churn_model.pkl`  
- `scaler.pkl`  

Saved using **Joblib** for future predictions.

---

## 🚀 Tech Stack

- **Language**: Python  
- **Data Processing**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Machine Learning**: Scikit-learn  
- **Model Saving**: Joblib  

---

## 📂 Project Structure

```bash
churn-prediction-project/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── data_preprocessing.ipynb
│   └── model_training.ipynb
│
├── models/
│   ├── churn_model.pkl
│   └── scaler.pkl
│
├── README.md
```

---

## 🔑 Key Takeaways

- ML is not just about accuracy  
- Real value comes from:
  - Interpretability  
  - Business alignment  
  - Actionable insights  
  - Impact estimation  

---

## 🔮 Future Improvements

- Try advanced models (Random Forest, XGBoost)  
- Perform hyperparameter tuning  
- Deploy model using APIs (Flask / FastAPI)  
- Build an interactive dashboard  

---

## ⚡ Author

**Aryan Singh Rajput**  
End-to-End ML Project | Data Science & AI Enthusiast  

---

## ❤️ About

This project focuses on solving a real-world business problem by combining **Machine Learning with strategic decision-making**, making it practical, scalable, and industry-relevant.
