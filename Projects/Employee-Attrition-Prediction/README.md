# Employee Attrition Prediction Using Machine Learning

## Project Overview

This project investigates employee attrition using the IBM HR Analytics Employee Attrition & Performance dataset. It compares **Logistic Regression, Decision Tree, Random Forest, and XGBoost** across class-imbalance strategies and tuning approaches to evaluate how well recorded departures can be identified. The analysis emphasizes minority-class performance, model interpretability, and responsible use rather than accuracy alone.

## Business Problem

Employee departures can create recruitment costs, workforce disruption, and loss of organizational knowledge. Understanding patterns associated with attrition may inform workforce research and retention planning. However, attrition is relatively uncommon in this dataset, so a model that predicts most employees will stay can achieve high overall accuracy while missing many departures. Incorrectly flagging employees who remain also creates risks, especially if predictions influence employment decisions.

## Business Objectives

- Examine the distribution of attrition and its relationships with recorded employee characteristics.
- Compare four classification algorithms using cross-validation and a separate validation set.
- Evaluate original class distributions, class weighting, and SMOTE to address imbalance.
- Select a classification threshold that makes the precision–recall trade-off explicit.
- Assess feature importance and subgroup error patterns, then evaluate the selected approach once on a held-out test set.

## Dataset

**Source:** [IBM HR Analytics Employee Attrition & Performance (Kaggle)](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

**Expected input:** `data/WA_Fn-UseC_-HR-Employee-Attrition.csv`

The dataset contains **1,470 employee records and 35 columns**, including the `Attrition` target (`Yes`/`No`). There are **237 attrition records (16.1%)** and **1,233 non-attrition records (83.9%)**. The notebook reports zero exact duplicate rows. The data are **synthetic**; findings do not establish validity for actual employees or workplaces.

## Tools & Technologies

Python, Jupyter Notebook, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Imbalanced-learn (SMOTE), XGBoost, and Joblib.

## Project Workflow

1. **Data audit:** Load the CSV, inspect column types, missingness, duplicates, and class distribution.
2. **Exploratory analysis:** Visualize attrition alongside age, monthly income, years at company, job satisfaction, and overtime.
3. **Leakage review:** Exclude the employee identifier and constant fields; document predictor-availability concerns.
4. **Data partitioning:** Use stratified **60% training / 20% validation / 20% test** splits (**882 / 294 / 294 records**).
5. **Preprocessing:** Impute and scale numerical variables, and impute and encode categorical variables within training pipelines.
6. **Model comparison:** Evaluate **24 configurations**: four algorithms × three imbalance strategies (original, class weights, SMOTE) × baseline/tuned versions. Use five-fold stratified cross-validation and randomized hyperparameter search for tuned versions.
7. **Model and threshold selection:** Rank configurations by training cross-validation average precision (AP), with validation AP used only for exact ties; select the classification threshold on validation data.
8. **Interpretation and ethics:** Examine precision–recall and ROC curves, permutation importance, and validation subgroup metrics.
9. **Final evaluation:** Refit the chosen configuration on training plus validation data, apply the frozen threshold to the held-out test set, and save the metrics, plots, and model.

## Visualizations

The notebook saves figures to `figures/`, including:

- `attrition_distribution.png`
- `eda_age.png`, `eda_monthlyincome.png`, `eda_yearsatcompany.png`, `eda_jobsatisfaction.png`, `eda_overtime.png`
- `threshold_tradeoffs.png`
- `validation_pr_curve.png`, `validation_roc_curve.png`
- `feature_importance.png`
- `validation_subgroup_recall.png`
- `final_test_confusion_matrix.png`

## Model Evaluation

The selected configuration was **tuned Logistic Regression with class weighting**, using a **validation-selected threshold of 0.60**. The held-out test set contained **294 records**, including **47 recorded departures**.

| Held-out test measure | Result |
|---|---:|
| Average precision (AP) | **0.6179** |
| Attrition prevalence baseline AP | 0.1599 |
| ROC-AUC | **0.8045** |
| Accuracy | **80.27%** |
| Balanced accuracy | **75.34%** |
| Attrition precision | **42.67%** |
| Attrition recall | **68.09%** |
| Specificity | **82.59%** |

**Confusion matrix:** 32 true positives, 15 false negatives, 43 false positives, and 204 true negatives. Thus, the model identified **32 of 47** recorded departures but incorrectly flagged **43 employees who did not leave**.

## Key Findings

- The target is imbalanced: only **16.1%** of records indicate attrition, making accuracy insufficient as a standalone evaluation measure.
- The selected model's **0.6179 test AP** exceeds the **0.1599** test prevalence baseline, indicating useful ranking performance within this synthetic dataset.
- At the chosen threshold, **68.09% recall** comes with **42.67% precision**; the model misses some departures and produces substantial false-positive flags.
- Validation permutation importance identifies **OverTime** and **JobSatisfaction** among the more influential recorded predictors. Predictive importance does **not** demonstrate causation.
- Subgroup evaluation is descriptive and cannot establish fairness, legal compliance, or generalization to real employees.

## Outcome

The project provides an end-to-end educational classification workflow with model comparisons, imbalance handling, threshold selection, held-out evaluation, and responsible-AI analysis. It produces reproducible figures and results files and saves the final fitted model. **It is not a validated employee risk assessment or a basis for employment decisions.**

## Installation / Running the Project

1. Clone the portfolio repository and enter the project folder:

   ```bash
   git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
   cd mathan-ms.github.io/Projects/Employee-Attrition-Prediction
   ```

2. Confirm that `data/WA_Fn-UseC_-HR-Employee-Attrition.csv` is present. If it is not included in the repository, obtain the dataset from the source linked above and place it in `data/`.

3. Install the project dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Launch Jupyter Notebook:

   ```bash
   python -m notebook
   ```

5. Open `notebooks/Employee_Attrition_Prediction.ipynb` and select **Restart Kernel and Run All Cells**. Run Jupyter from the project directory or its `notebooks/` directory so the notebook can resolve the relative paths.

**Expected output directories:** `figures/` and `results/`. The notebook creates these directories if needed. Model search and cross-validation may take time depending on hardware.

## Saved Results

The notebook writes the following files to `results/`:

- `model_comparison.csv`
- `validation_threshold_tradeoffs.csv`
- `validation_permutation_importance.csv`
- `validation_subgroups.csv`
- `final_test_metrics.csv`
- `final_model.joblib`

## Limitations

The dataset is synthetic and cross-sectional; it does not establish real-world performance, causal relationships, or when an employee might leave. Only **47** positive examples appear in the held-out test set, so estimates are uncertain. Cross-validation model selection and validation-based threshold selection can be optimistic, and the final refit may shift probability scores. Real-world use would require independent, appropriately governed data, prospective validation, privacy safeguards, and detailed fairness assessment. This work is for educational and portfolio demonstration purposes only.
