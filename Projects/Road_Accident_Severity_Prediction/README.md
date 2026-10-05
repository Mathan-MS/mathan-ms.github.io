# Road Accident Severity Prediction Using Machine Learning

## Project Overview

This project analyzes road traffic accident data and builds machine-learning models to predict accident severity.

The analysis examines how accident severity relates to weather, lighting, road surface conditions, time of day, day of week, and collision type. Four classification algorithms are evaluated, and additional analysis includes statistical association testing, cross-validation, multiclass ROC-AUC, class-imbalance handling, and feature importance.

## Business Problem

Understanding the factors associated with severe road accidents can support transportation safety analysis and help identify conditions that may require additional attention.

This project explores several questions:

- Which environmental and road-related variables are associated with accident severity?
- How well can machine-learning models distinguish between accident-severity classes?
- Which classification model performs best when class imbalance is considered?
- Does class weighting improve XGBoost performance on underrepresented severity classes?
- Which predictors contribute most strongly to the best-performing tree-based model?

## Dataset

The project uses:

`RTA Dataset.csv`

The dataset contains road traffic accident records with information about accident severity, weather conditions, lighting conditions, road characteristics, collision type, time, casualty information, and other accident-related variables.

## Methods

The project follows these main steps:

1. Load and inspect the accident dataset
2. Review missing values and duplicate records
3. Engineer time-of-day features
4. Explore accident-severity distributions
5. Analyze severity by weather, light, road surface, time, day, and collision type
6. Measure statistical association using Chi-square and Cramer's V
7. Remove target leakage and prepare modeling features
8. Perform a stratified train-test split
9. Build numeric and categorical preprocessing pipelines
10. Train multiple classification models
11. Compare model performance
12. Perform five-fold stratified cross-validation
13. Evaluate the best model using a confusion matrix
14. Compare multiclass ROC-AUC
15. Test a weighted XGBoost model for class imbalance
16. Compare baseline and weighted XGBoost results
17. Analyze grouped feature importance

## Models

The project compares:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost

The weighted XGBoost experiment applies balanced sample weights to examine whether additional emphasis on minority severity classes improves classification performance.

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Balanced Accuracy
- Macro Precision
- Macro Recall
- Macro F1
- Weighted F1
- Multiclass ROC-AUC
- Stratified Cross-Validation Macro F1
- Confusion Matrix

Macro-level metrics are emphasized because they give equal importance to each accident-severity class.

## Statistical Analysis

Chi-square tests are used to identify statistical associations between categorical accident factors and accident severity.

Cramer's V is used to measure the strength of those associations.

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- scikit-learn
- XGBoost

## Project Outputs

### Figures

`figures/`

- `accident_severity_distribution.png`
- `severity_by_weather.png`
- `severity_by_light_conditions.png`
- `severity_by_road_surface.png`
- `severity_by_time_of_day.png`
- `severity_by_day_of_week.png`
- `severity_by_collision_type.png`
- `model_comparison.png`
- `best_model_confusion_matrix.png`
- `weighted_xgboost_confusion_matrix.png`
- `feature_importance.png`

### Results

`results/`

- `model_comparison.csv`
- `cross_validation_results.csv`
- `association_results.csv`
- `multiclass_roc_auc_results.csv`
- `weighted_xgboost_results.csv`
- `baseline_vs_weighted_xgboost.csv`
- `class_recall_comparison.csv`
- `feature_importance.csv`
- `missing_value_summary.csv`

## Repository Structure

```text
Road_Accident_Severity_Prediction/
│
├── README.md
│
├── data/
│   └── RTA Dataset.csv
│
├── figures/
│   ├── accident_severity_distribution.png
│   ├── severity_by_weather.png
│   ├── severity_by_light_conditions.png
│   ├── severity_by_road_surface.png
│   ├── severity_by_time_of_day.png
│   ├── severity_by_day_of_week.png
│   ├── severity_by_collision_type.png
│   ├── model_comparison.png
│   ├── best_model_confusion_matrix.png
│   ├── weighted_xgboost_confusion_matrix.png
│   └── feature_importance.png
│
├── results/
│   ├── model_comparison.csv
│   ├── cross_validation_results.csv
│   ├── association_results.csv
│   ├── multiclass_roc_auc_results.csv
│   ├── weighted_xgboost_results.csv
│   ├── baseline_vs_weighted_xgboost.csv
│   ├── class_recall_comparison.csv
│   ├── feature_importance.csv
│   └── missing_value_summary.csv
│
└── notebooks/
    └── Road_Accident_Severity_Prediction.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Place the dataset in:

```text
data/RTA Dataset.csv
```

3. Install the required Python packages:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn xgboost
```

4. Open:

```text
notebooks/Road_Accident_Severity_Prediction.ipynb
```

5. Run the notebook cells in order.

The notebook automatically creates the `figures/` and `results/` folders if they do not already exist.

## Key Skills Demonstrated

- Data cleaning and preprocessing
- Feature engineering
- Exploratory data analysis
- Statistical association testing
- Machine-learning classification
- Logistic Regression
- Decision Trees
- Random Forest
- XGBoost
- Class-imbalance handling
- Stratified cross-validation
- Multiclass ROC-AUC
- Feature-importance analysis
- Pipeline-based preprocessing
- Model evaluation and comparison

## Outcome

The project provides a reproducible framework for predicting road accident severity and evaluating multiple classification approaches under class imbalance.

The analysis combines predictive modeling with statistical association testing and feature-importance analysis to provide both model-performance and interpretability perspectives.

## Limitations

The model is limited by the variables and class distribution available in the supplied dataset. Accident severity may also depend on contextual factors that are not captured in the data.

Class imbalance can make minority severity classes more difficult to predict, which is why macro-level metrics and weighted modeling are included in the evaluation.

## Future Improvements

Potential enhancements include:

- Hyperparameter tuning
- Additional class-balancing techniques such as SMOTE
- Calibration of predicted probabilities
- Additional external road or weather data
- Geographic accident analysis
- Explainability methods such as SHAP
- Deployment through an interactive prediction interface
