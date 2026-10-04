# U.S. Childcare Affordability Analysis

## Project Overview

Childcare expenses are among the major financial burdens on families in America. The research project focuses on childcare expenses in America to distinguish differences across locations, types of childcare, and family income levels.

Data analysis and visualization methods will be used throughout the research project in order to study affordability trends in childcare.

## Business Problem

Childcare costs can impact family budgets, career decisions, and accessibility to childcare services. It can be beneficial to know whether childcare costs differ from family incomes, as this will reveal where affordability issues exist.

The objectives of this project are:

- To analyze the trends in childcare costs through time.
- To analyze childcare costs between different states.
- To analyze differences between childcare types.
- To analyze childcare costs relative to family incomes.
- To find out where there are more affordability issues.
- To present the information by using visualization techniques.

## Dataset

This project uses the National Database of Childcare Prices, which contains information on childcare prices in the United States.

The analysis uses data from 2008-2018 and covers childcare costs, geographic area, type of childcare, and income levels.

**Dataset Source:** https://www.dol.gov/agencies/wb/topics/featured-childcare

Key variables include:

- State
- Year
- Childcare prices
- Age group of children
- Type of childcare
- Household income
- Geographic characteristics

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Project Workflow

The project follows these main steps:

1. **Data Cleaning and Preparation**
   - Examined the structure of the data and variables provided.
   - Identified missing values and inconsistencies.
   - Prepared the data on prices for child care and family income for the analysis.
   - Sorted the data by year, state, and type of child care.

2. **Exploratory Data Analysis**
   - Explored the distribution of prices for child care.
   - Comparing the prices for child care across different states and years.
   - Comparing differences between types of child care and ages.

3. **Affordability Analysis**
   - Comparing prices of child care to the family income.
   - Exploring the proportion of family income needed to cover the expenses of child care.
   - Identifying differences in affordability by geographical location.

4. **Data Visualization**
   - Visualizing trends in prices for child care.
   - Comparing costs between states and types of child care.
   - Understandably visualizing patterns of affordability.

## Key Findings

Several significant patterns of U.S. childcare costs and affordability were revealed during the analysis:

- There were great differences in childcare costs among different locations.
- Childcare cost changes were observed throughout the period of the analysis.
- Cost of childcare varied depending on the age of the child and the childcare type.
- Infants' childcare costs were among the highest of all childcare types.
- A comparison of childcare costs and income made it possible to understand that there are differences in the financial impact of childcare expenses for different people living in different locations.
- Some locations and childcare types have been revealed where expenses may significantly take up the family budget.

## Outcome

This project shows how analytics can be applied to study the affordability of one of the family's expenses.

The application of the three variables (cost of child care, location, and income) helps provide a better understanding of the affordability of child care services in the USA. The results would provide input for debates about child care accessibility and affordability.

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

`US_Childcare_Affordability_Analysis.ipynb`
