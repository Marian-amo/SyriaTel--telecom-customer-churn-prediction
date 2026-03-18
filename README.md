# SyriaTel--telecom-customer-churn-prediction
This project aims to develop a predictive model to identify customers likely to churn for SyriaTel, a telecommunication company.  By accurately predicting churn, SyriaTel can implement proactive retention strategies to mitigate its financial impact and improve customer satisfaction.   


## Overview

Customer churn is a major challenge for telecommunications companies, as losing customers directly impacts revenue and growth.

This project builds a **machine learning classification model** to predict whether a customer is likely to churn (leave SyriaTel). By identifying high-risk customers early, the business can take proactive steps to improve retention.

---

## Business Understanding

### Stakeholder

Customer Retention Team at SyriaTel

### Business Problem

SyriaTel is experiencing customer churn, which leads to:

* Revenue loss
* Increased customer acquisition costs
* Reduced market share

### Objective

Develop a predictive model to:

* Identify customers likely to churn
* Understand key factors driving churn
* Support targeted retention strategies

---

## Data Understanding

The dataset contains **3,333 customer records** with 21 features, including:

### Key Feature Categories

* Usage behavior (minutes, calls)
* Service plans (international plan, voicemail plan)
* Customer interactions (customer service calls)

### Target Variable

* **churn** (0 = No, 1 = Yes)

---

##  Data Preparation

The following preprocessing steps were applied:

* Converted target variable (`churn`) to numeric
* Removed identifiers (`phone number`)
* Removed redundant features (charge columns due to multicollinearity)
* Performed feature engineering:

  * Total minutes
  * Total calls
  * Service call rate
  * Usage ratios

To prevent **data leakage**, preprocessing and feature engineering were applied using **Scikit-learn pipelines**.

---

##  Exploratory Data Analysis (EDA)

Key insights from EDA:

* Customers with **more customer service calls** are more likely to churn
* Customers with **international plans** have higher churn rates
* High **daytime usage** is associated with churn
* Correlation analysis revealed **multicollinearity**, leading to feature removal

---

##  Modeling Approach

An **iterative modeling approach** was used:

### 1️⃣ Baseline Model

* Logistic Regression
* Interpretable but limited performance

### 2️⃣ Decision Tree

* Captures non-linear relationships
* Improved recall

### 3️⃣ Random Forest (Ensemble Model)

* Combines multiple trees
* Reduced overfitting
* Provided best overall performance

### 4️⃣ Tuned Random Forest

* Hyperparameter tuning using GridSearchCV
* Optimized for recall

---

##  Evaluation Metrics

The models were evaluated using:

* **Recall** → prioritized to reduce missed churners
* **Precision** → measures accuracy of churn predictions
* **F1-score** → balance between precision and recall
* **Confusion Matrix** → shows prediction errors
* **ROC Curve & AUC** → evaluates model discrimination ability

### Why Recall Matters

Missing a churner (false negative) means:

>  Lost customer with no intervention

---

## Final Model Performance

The **Tuned Random Forest model** performed best, achieving:

* High recall (better identification of churners)
* Strong ROC-AUC score (good class separation)
* Balanced performance across metrics

---

##  Key Insights

Top drivers of churn include:

* High number of **customer service calls**
* Presence of an **international plan**
* High **daytime usage**
* Low engagement with value-added services

---

## Business Recommendations

* Improve customer service experience to reduce repeated complaints
* Target high-risk customers with retention offers
*  Review pricing and value of international plans
* Monitor heavy users for dissatisfaction signals

---

## Limitations

* Dataset lacks customer satisfaction metrics
* No external data (e.g., competitor pricing)
* Model performance may change over time

---

## Next Steps

* Implement model in production for real-time churn prediction
* Tune classification threshold for business needs
* Explore advanced models (e.g., Gradient Boosting, XGBoost)
* Incorporate additional behavioral data

---
# Requirements

Key libraries used:

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* jupyter

---

## Project Structure

```
├── notebook.ipynb
├── README.md
├── requirements.txt
└── data/
    └── churn.csv
    
```

