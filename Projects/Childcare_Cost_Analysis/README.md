# U.S. Childcare Affordability Analysis

## Project Overview

This project analyzes U.S. childcare price data to explore childcare affordability patterns across states and over time.

The analysis focuses on childcare cost trends, state-level differences, household income relationships, and the affordability of infant childcare across the United States.

## Business Problem

Childcare costs can place a significant financial burden on families and may vary considerably by location and income level.

This project is aimed at accomplishing the following goals:

- Examine national childcare cost trends over time.
- Compare childcare costs across states.
- Explore the relationship between household income and childcare costs.
- Identify states with relatively high and low infant childcare costs.
- Present the findings through clear visualizations.

## Dataset

The project uses:

`nationaldatabaseofchildcareprices.xlsx`

The dataset contains childcare price information for U.S. states and includes measures related to childcare costs, geography, and household economic conditions.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- OpenPyXL

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded the childcare price dataset from the `data/` folder.

2. **Data Cleaning and Preparation**
   - Reviewed the dataset structure.
   - Cleaned and prepared fields used in the analysis.
   - Saved the cleaned dataset for reuse.

3. **National Trend Analysis**
   - Examined childcare cost trends over time.

4. **Cost Distribution Analysis**
   - Reviewed the distribution of childcare costs.

5. **Income and Childcare Cost Analysis**
   - Examined the relationship between household income and childcare costs.

6. **State-Level Analysis**
   - Identified states with the highest infant childcare costs.
   - Identified states with the lowest infant childcare costs.

7. **Summary Visualization**
   - Created an infographic-style summary of the main findings.

## Visualizations

The analysis includes:

- National childcare cost trend
- Childcare cost distribution
- Income versus childcare cost
- Top 15 states by infant childcare cost
- Lowest 15 states by infant childcare cost
- Childcare affordability infographic

## Key Findings

The analysis shows that childcare costs vary considerably across states and over time.

The project also highlights differences in affordability by comparing childcare costs with household income and by identifying states with relatively high and low infant childcare costs.

## Outcome

This project provides a visual overview of childcare affordability in the United States.

The findings can support further analysis of family expenses, regional affordability, and childcare policy considerations.

## Installation / Running the Project

1. Clone the repository:

```bash
git clone <repo_url>
cd <repository_name>
```

2. Place the dataset in the `data/` folder.

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:

```bash
jupyter notebook
```

5. Open and run:

`notebooks/Childcare_Affordability_Analysis.ipynb`
