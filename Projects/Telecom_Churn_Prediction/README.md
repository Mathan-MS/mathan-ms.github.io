# Telecom Customer Churn Prediction

## Project Overview

Customer churn has emerged as one of the biggest challenges for telecommunications firms, as it can negatively impact revenue and increase customer acquisition costs. This project will use telecom customer data to determine the factors driving customer churn and apply machine learning models to predict churners.

An end-to-end process will be followed in this project to address customer churn using data science methods.

## Business Problem

Telecommunications firms deal with clients who are on various services and contracts. It is beneficial for organizations to identify clients at risk of churn, as this enables better client retention.

This project is aimed at accomplishing the following goals:

- To identify features that are associated with customer churn.
- To find out how services, contracts, and account features are related to customer retention.
- To build predictive models of customer churn using machine learning.
- To compare different classification models.

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

The target variable is Churn, which indicates whether a customer discontinued service.

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
   - Conducted an analysis of the dataset for any missing or incorrect data values.
   - Changed the type of the variable where required.
   - Preliminary preparation of categorical and numeric features.

2. **Exploratory Data Analysis**
   - Identifying details regarding the customers and their pattern of churn.
   - Analyzing the correlation between customer churn and tenure, contract type, services, charges, etc.
   - Conducted analysis using the help of visualizations to detect any trends.

3. **Feature Engineering**
   - Transforming the categorical features into numeric features.
   - Splitting the data set into training and testing sets.

4. **Class Imbalance Handling**
   - Applying the SMOTE technique on the training dataset to handle the class imbalance problem.
   - Reserving the test data set separately to evaluate the model.

5. **Model Development**
   - Logistic Regression
   - Random Forest
   - XGBoost

6. **Model Evaluation**
   - Evaluation of the classification models based on several evaluation metrics.

## Model Evaluation

The models were evaluated based on:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix

Particular emphasis was placed on the metric Recall for churned customers because you may miss the opportunity to retain them if you fail to recognize them as churned.

Comparing different models made it possible to determine which one offered the best trade-off.

## Key Findings

The analysis made it clear that churn behavior is related to several characteristics of customers and accounts.

The key findings from the analysis are:

- Tenure of the customer was one of the significant factors in understanding churn behavior.
- The type of contract had some significance in terms of customer retention behavior.
- Churn behavior is linked to monthly charges and the types of services subscribed to by the customers.
- The different service-related attributes, including internet service, online security, and technical support, gave useful insights into customer churn behavior.

## Outcome

In this project, it was shown that customer information and machine learning techniques could be applied to identify potential churn customers.

The findings will assist telecommunications companies in gaining a better understanding of customer behavior and in detecting customers at high risk of churning.

## Installation / Running the Project

1. Clone the repository

```bash
git clone <repo_url>
cd <repository_name>
```

2. Install the required packages

```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook

```bash
jupyter notebook
```

4. Open and run:

`Telecom_Churn_Prediction.ipynb`
