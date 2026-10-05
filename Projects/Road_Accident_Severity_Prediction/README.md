# Road Accident Severity Prediction Using Machine Learning

## Project Overview

This project analyzes road traffic accident data and builds machine-learning models to predict accident severity.

The analysis examines relationships between accident severity and weather, lighting, road surface conditions, time of day, day of week, and collision type.

## Business Problem

Understanding the factors associated with severe road accidents can support transportation safety analysis and help identify conditions that may require additional attention.

This project is aimed at accomplishing the following goals:

- Identify environmental and road-related variables associated with accident severity.
- Build classification models for accident severity.
- Compare multiple machine-learning algorithms.
- Evaluate model performance under class imbalance.
- Examine feature importance and statistical association.

## Dataset

The project uses:

`RTA Dataset.csv`

The dataset contains road traffic accident records with information about accident severity, weather conditions, lighting conditions, road characteristics, collision type, time, casualty information, and other accident-related variables.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn
- XGBoost

## Project Workflow

The project follows these main steps:

1. **Data Cleaning and Preparation**
   - Reviewed missing values and duplicates.
   - Prepared accident-related variables for analysis.

2. **Feature Engineering**
   - Created time-of-day features.

3. **Exploratory Data Analysis**
   - Analyzed severity by weather, light, road surface, time, day, and collision type.

4. **Statistical Analysis**
   - Used Chi-square tests and Cramer's V to measure association.

5. **Model Preparation**
   - Removed target leakage.
   - Prepared numeric and categorical preprocessing pipelines.
   - Performed a stratified train-test split.

6. **Model Development**
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - XGBoost

7. **Model Evaluation**
   - Compared model performance.
   - Performed stratified cross-validation.
   - Evaluated multiclass ROC-AUC and confusion matrices.

8. **Class Imbalance Analysis**
   - Tested weighted XGBoost.

9. **Feature Importance**
   - Reviewed grouped feature importance from a tree-based model.

## Model Evaluation

The models were evaluated using:

- Accuracy
- Balanced Accuracy
- Macro Precision
- Macro Recall
- Macro F1
- Weighted F1
- Multiclass ROC-AUC
- Stratified Cross-Validation Macro F1
- Confusion Matrix

Macro-level metrics were emphasized because the accident-severity classes are imbalanced.

## Key Findings

The analysis showed that accident severity is related to several environmental and road conditions.

The project also demonstrated that class imbalance affects model performance and that macro-level metrics provide a more balanced view of performance across severity classes.

## Outcome

This project provides a reproducible machine-learning workflow for road accident severity prediction.

The analysis combines predictive modeling, statistical association testing, class-imbalance evaluation, and feature-importance analysis.

## Installation / Running the Project

1. Clone the repository.

2. Place `RTA Dataset.csv` in the `data/` folder.

3. Install the required packages:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn xgboost
```

4. Open and run:

`notebooks/Road_Accident_Severity_Prediction.ipynb`
