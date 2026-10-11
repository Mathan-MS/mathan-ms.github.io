# Telecom Customer Churn Prediction Using Machine Learning

## Project Overview

This project analyzes the Telco Customer Churn dataset to explore customer characteristics associated with churn and compare three classification algorithms: **Logistic Regression, Random Forest, and XGBoost**. The workflow covers data cleaning, feature engineering, outlier handling, encoding, scaling, a stratified train/test split, training-only SMOTE, model evaluation, and interpretation of results.

## Business Problem

Customer churn can reduce recurring revenue and increase the cost of acquiring replacement customers. Predicting churn risk may help telecommunications providers prioritize retention analysis and customer engagement. A prediction of churn risk does not, by itself, explain why a customer leaves or establish that an intervention will prevent churn.

## Research Questions

1. Which customer account, service, contract, and billing characteristics are associated with churn?
2. How do Logistic Regression, Random Forest, and XGBoost compare in identifying customers who churn?
3. What trade-offs exist among recall, precision, F1-score, accuracy, and ROC-AUC for retention-oriented decisions?

## Dataset

- **Source:** [Telco Customer Churn dataset on Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Original records:** 7,043
- **Original columns:** 21, including the target
- **Target:** `Churn` (binary: Yes/No)
- **Example predictors:** `tenure`, `Contract`, `InternetService`, `OnlineSecurity`, `TechSupport`, `PaymentMethod`, `MonthlyCharges`, and `TotalCharges`

The notebook searches for `Telco-Customer-Churn.csv` or `WA_Fn-UseC_-Telco-Customer-Churn.csv` in `data/`, or uses the sole CSV in that directory if only one exists. The dataset must be placed there before running the notebook.

## Tools & Technologies

Python, Jupyter Notebook, pandas, NumPy, Matplotlib, seaborn, scikit-learn, imbalanced-learn (SMOTE), and XGBoost.

## Project Workflow

1. **Data review and cleaning:** Inspect the dataset, remove the customer identifier, convert `TotalCharges` to numeric, and fill missing values using the median.
2. **Feature engineering:** Add log-transformed charge variables and tenure groupings.
3. **Outlier handling:** Apply IQR-based clipping to selected charge variables.
4. **Encoding and scaling:** Convert categorical variables to indicator columns and scale numeric predictors.
5. **Train/test split and class balancing:** Create a stratified 80/20 split; apply SMOTE only to the training partition.
6. **Model development:** Fit Logistic Regression, Random Forest, and XGBoost.
7. **Evaluation and interpretation:** Review classification reports, confusion matrices, ROC curves, predicted-probability visualizations, and feature importance outputs.

## Model Evaluation and Selection

The saved test set contains **1,409 customers**, including **374 churners**. The training partition contains **5,634 records before SMOTE** and **8,278 after SMOTE**. The metrics below are from the executed notebook; precision, recall, and F1-score refer to the churn class.

| Model | Accuracy | Churn precision | Churn recall | Churn F1 | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.7559 | 0.5281 | **0.7540** | **0.6211** | **0.8415** |
| Random Forest | **0.7637** | **0.5469** | 0.6390 | 0.5894 | 0.8255 |
| XGBoost | 0.7630 | 0.5395 | 0.7299 | 0.6205 | 0.8358 |

**Logistic Regression** is the strongest candidate when churn detection is the main priority: it has the highest churn recall, F1-score, and ROC-AUC in this test run. **Random Forest** has the highest overall accuracy and churn precision. These are results from one test split, not proof of universal model superiority.

## Key Findings

- Logistic Regression identified approximately **75.4%** of churners in the test set, with churn precision of **52.81%**.
- XGBoost achieved churn recall of **72.99%**, close to Logistic Regression, while Random Forest achieved **63.90%**.
- Tenure, contract type, charges, and service-related characteristics appeared among the factors associated with churn in the analysis.
- The Random Forest importance ranking highlighted `tenure` (0.1232), `TotalCharges_log` (0.1066), and `TotalCharges` (0.1028).
- The XGBoost importance ranking highlighted `Contract_Two year` (0.3028), `OnlineSecurity_No internet service` (0.1572), and `Contract_One year` (0.1116).

Feature importance reflects model behavior and should not be interpreted as a causal effect.

## Limitations and Responsible Use

- The dataset is a demonstration dataset and may not represent other telecom providers or customer populations.
- In the existing notebook, some imputation, outlier thresholds, and scaling are calculated before the train/test split. This may introduce information leakage; reported scores should therefore be treated as illustrative rather than strictly independent holdout estimates.
- The comparison uses a single test split without cross-validated model selection or external validation.
- Predictions may be wrong. False negatives can miss customers who churn, while false positives can lead to unnecessary outreach.
- Customer information should be handled with appropriate privacy safeguards, and retention strategies should be assessed for fairness and customer impact.

## Conclusion and Recommendations

The project demonstrates how customer and account data can support churn-risk analysis. In the executed comparison, Logistic Regression achieved the highest churn recall (**0.7540**), F1-score (**0.6211**), and ROC-AUC (**0.8415**), making it a promising candidate for prioritizing potential churners. Random Forest had slightly higher accuracy (**0.7637**), reinforcing that the best metric depends on the business objective.

Telecommunications providers could use these insights to investigate churn patterns and prioritize customer engagement. Before operational use, the model would require further validation on new customer data and an assessment of retention-intervention outcomes, privacy, and fairness.

## Installation / Running the Project

The project is located in the `Projects/Telecom_Churn_Prediction` directory of the portfolio repository. The dataset should be placed in the `data/` folder, and the required Python packages are listed in `requirements.txt`.

### Prerequisites

- **Python 3.11** (recommended, subject to dependency compatibility)
- **Git** — Download from [git-scm.com](https://git-scm.com/downloads) if not already installed.
- **Telco Customer Churn dataset** — Download from [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) if the CSV is not already included in the `data/` folder.

### Step 1: Clone the Repository

Open Command Prompt or a terminal and run:

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/Telecom_Churn_Prediction
```

### Step 2: Install Project Dependencies

From the project directory, run:

```bash
python -m pip install -r requirements.txt
```

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

In Jupyter Notebook, open:

`notebooks/Telecom_Churn_Prediction.ipynb`

Select **Kernel → Restart Kernel and Run All Cells** to execute the notebook sequentially.

The notebook reads the churn dataset from `data/` (recognizing `Telco-Customer-Churn.csv` or `WA_Fn-UseC_-Telco-Customer-Churn.csv`, or a single CSV in that folder). It performs data preparation, exploratory analysis, feature engineering, class-imbalance handling with SMOTE, model training and evaluation for Logistic Regression, Random Forest, and XGBoost, and feature-importance analysis. It saves generated figures to `figures/` and results files to `results/`.

**Note:** Execution time may vary depending on the computer's processing capabilities.
