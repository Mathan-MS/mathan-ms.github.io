# Telecom Customer Churn Prediction

## Project Overview

Customer churn is one of the major challenges for telecommunications companies because it can negatively affect revenue and increase customer acquisition costs. This project uses telecom customer data to identify factors associated with churn and applies machine learning models to predict customers who may leave.

An end-to-end data science workflow is used to prepare the data, explore churn patterns, address class imbalance, train classification models, and compare model performance.

## Business Problem

Telecommunications companies serve customers with different services, contracts, and billing arrangements. Identifying customers who are at risk of churning can help support customer-retention efforts.

This project is aimed at accomplishing the following goals:

- Identify features associated with customer churn.
- Examine how services, contracts, and account characteristics relate to customer retention.
- Build predictive models for customer churn.
- Compare multiple classification models.

## Dataset

The project uses the Telco Customer Churn dataset, which contains 7,043 customer records and 21 variables.

The dataset includes customer demographics, account information, subscribed services, billing information, and churn status.

**Dataset Source:** https://www.kaggle.com/datasets/blastchar/telco-customer-churn

Key variables include:

- Tenure
- Contract Type
- Internet Service
- Online Security
- Tech Support
- Payment Method
- Monthly Charges
- Total Charges
- Churn

The target variable is `Churn`, which indicates whether a customer discontinued service.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn
- XGBoost

## Project Workflow

The project follows these main steps:

1. **Data Cleaning and Preparation**
   - Reviewed the dataset for missing or incorrect values.
   - Converted variables to appropriate data types.
   - Prepared categorical and numeric features.

2. **Exploratory Data Analysis**
   - Examined customer characteristics and churn patterns.
   - Analyzed relationships between churn and tenure, contract type, services, and charges.
   - Used visualizations to identify trends.

3. **Feature Engineering**
   - Converted categorical variables into numeric form.
   - Split the data into training and testing sets.

4. **Class Imbalance Handling**
   - Applied SMOTE to the training data.
   - Kept the test data separate for final evaluation.

5. **Model Development**
   - Logistic Regression
   - Random Forest
   - XGBoost

6. **Model Evaluation**
   - Compared the classification models using multiple evaluation metrics.

## Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix

Particular emphasis was placed on recall for churned customers because failing to identify customers who are likely to leave may result in missed retention opportunities.

## Key Findings

The analysis showed that churn behavior is related to several customer and account characteristics.

Key findings include:

- Customer tenure was an important factor in understanding churn behavior.
- Contract type was related to customer retention behavior.
- Monthly charges and subscribed services were associated with churn.
- Service-related variables such as internet service, online security, and technical support provided useful insight into churn behavior.

## Outcome

This project demonstrates how customer data and machine learning can be used to identify customers who may be at risk of churning.

The findings can help telecommunications companies better understand customer behavior and support customer-retention strategies.

## Installation / Running the Project

1. Clone the repository:

```bash
git clone <repo_url>
cd <repository_name>
```

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook:

```bash
jupyter notebook
```

4. Open and run:

`notebooks/Telecom_Churn_Prediction.ipynb`
