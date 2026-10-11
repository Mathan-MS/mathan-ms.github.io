# Road Accident Severity Prediction Using Machine Learning

## Project Overview

This project analyzes **12,316 road traffic accident records** from Addis Ababa, Ethiopia (2017–2020), using exploratory analysis, statistical association tests, and machine-learning models to classify accidents as **Slight Injury, Serious Injury, or Fatal Injury**. The original dataset contains 32 features. The goal is to understand which recorded characteristics are informative and how reliably models recognize the less frequent, more severe outcomes.

## Business Problem

Understanding patterns associated with accident severity can inform transportation safety research. A central challenge is **class imbalance**: Slight Injury accounts for approximately 84.56% of records, Serious Injury for 14.15%, and Fatal Injury for 1.28%. Overall accuracy alone can therefore be misleading.

## Research Questions

1. What accident severity predictors are among the strongest?
2. Is there any relationship between environmental/weather conditions and accident severity?
3. How are time-related and road characteristics associated with accident severity?
4. How well can machine-learning algorithms classify accident severity?
5. Which algorithm provides the best results for accident severity prediction?

## Dataset

- Source file: `RTA Dataset.csv`
- Records: **12,316**
- Original features: **32**
- Location and period: **Addis Ababa, Ethiopia, 2017–2020**
- Target: **Accident_severity** (Slight Injury, Serious Injury, Fatal Injury)

The dataset includes weather, lighting, road, junction, vehicle, collision, and accident timing characteristics. The notebook should be consulted for exact preprocessing decisions and the final modeling feature set.

## Tools & Technologies

Python, Jupyter Notebook, pandas, NumPy, Matplotlib, seaborn, SciPy, scikit-learn, and XGBoost.

## Project Workflow

1. **Data review and preparation:** Inspect missing values, duplicates, and severity distribution.
2. **Feature engineering:** Derive `Hour` and `Time_of_day` from recorded accident timing.
3. **Exploratory and statistical analysis:** Examine accident characteristics using visual summaries, chi-square tests, and Cramér's V.
4. **Leakage prevention and preprocessing:** Exclude `Cause_of_accident` and `Number_of_casualties` from the predictors; prepare numeric and categorical features and use a stratified train/test split.
5. **Model development:** Tune Logistic Regression, Decision Tree, Random Forest, and XGBoost in **balanced and unbalanced configurations** (eight tuned configurations total).
6. **Model selection:** Use **five-fold stratified cross-validation Macro F1** on the training data as the primary selection criterion.
7. **Evaluation and interpretation:** Review test Macro F1, accuracy, balanced accuracy, class-level recall, confusion matrices, grouped feature importance, permutation importance, and subgroup performance.

## Model Evaluation and Selection

**Macro F1 is the primary model-selection metric** because it averages the F1 scores of the three severity classes equally. This is important when Fatal Injury cases are rare.

| Tuned configuration | CV Macro F1 | Test Macro F1 | Test accuracy |
|---|---:|---:|---:|
| Balanced Random Forest | **0.4295** | **0.4193** | 78.94% |
| Balanced XGBoost | 0.4236 | 0.4093 | 73.38% |
| Unbalanced Decision Tree | 0.3788 | 0.3818 | 76.22% |
| Balanced Decision Tree | 0.3595 | 0.3792 | 65.22% |
| Unbalanced XGBoost | 0.3351 | 0.3391 | 84.86% |
| Unbalanced Random Forest | 0.3319 | 0.3327 | 84.86% |
| Unbalanced Logistic Regression | 0.3078 | 0.3093 | 84.62% |
| Balanced Logistic Regression | 0.3033 | 0.3080 | 48.54% |

**Balanced Random Forest** was selected based on the highest cross-validation Macro F1, narrowly ahead of Balanced XGBoost. This does not mean it was superior on every metric.

## Key Findings

- **Selected model:** Balanced Random Forest achieved 78.94% test accuracy, 0.4193 test Macro F1, and 0.4184 test balanced accuracy.
- **Severe-outcome detection:** Its Serious Injury recall was **27.22%** and Fatal Injury recall was **9.68%** (3 of 31 Fatal Injury cases). Balanced XGBoost had higher recall for both severe classes, illustrating an important trade-off.
- **Leading grouped features:** Day of Week (0.1217), Hour (0.1179), and Number of Vehicles Involved (0.0718) were prominent in grouped tree-based importance. Permutation importance ranked Number of Vehicles Involved first.
- **Statistical associations:** Weather conditions (Cramér's V = 0.0323), Time of Day (V = 0.0441), and Junction Type (V = 0.0419) showed **very weak associations** with severity. The weather association had p = 0.0004. These results do not establish causation.

## Limitations and Responsible Use

The severe classes, particularly Fatal Injury, are underrepresented. The selected model misses most Fatal Injury cases and **should not be used for autonomous public-safety decisions**. Subgroup performance also varied, and results from smaller subgroups require caution. Some test results were reviewed during development, limiting strict holdout independence; future work should evaluate a finalized model on a completely untouched external dataset.

## Outcome and Future Work

The project demonstrates a reproducible analysis and model-comparison workflow while showing why accuracy alone is inadequate for imbalanced severity prediction. Next steps include collecting more severe-injury examples, testing alternative class-balancing and decision-threshold approaches, and performing independent external validation.

## Installation / Running the Project

The project is located in the `Projects/Road_Accident_Severity_Prediction` directory of the portfolio repository. Confirm the notebook, dataset, and dependency-file locations before running.

1. Clone your repository:

   ```bash
   git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
   cd mathan-ms.github.io/Projects/Road_Accident_Severity_Prediction
   ```

2. Place `RTA Dataset.csv` in the location expected by the notebook, and update its dataset path if necessary.
3. Install dependencies. If your repository includes a verified `requirements.txt`, run:

   ```bash
   pip install -r requirements.txt
   ```

4. Start Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open `Road_Accident_Severity_Prediction.ipynb` (or its actual path in your repository) and run the cells in order.

**Repository folder:** https://github.com/Mathan-MS/mathan-ms.github.io/tree/main/Projects/Road_Accident_Severity_Prediction

**Before publishing:** Confirm the notebook and CSV locations and ensure `requirements.txt` exists if you retain that installation command. The live GitHub folder contents could not be independently retrieved during this review.
