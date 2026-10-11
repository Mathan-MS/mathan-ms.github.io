# U.S. Childcare Affordability Analysis

## Project Overview

This project uses exploratory data analysis and Python visualizations to examine U.S. childcare prices from **2008 to 2018**. Using the National Database of Childcare Prices, it explores historical price trends, differences across states, distributions of infant childcare prices, and relationships between childcare prices and household income. The results are presented through charts and an infographic rather than predictive models.

## Business Problem

Childcare expenses vary by location, provider type, and child age group. This project uses descriptive analysis and visual comparisons to help readers explore historical childcare price patterns and consider their implications for families, researchers, and policymakers.

The analysis addresses these questions:

- How do recorded childcare prices vary over time?
- How are infant childcare prices distributed across the analyzed records?
- How do average infant childcare prices compare across states?
- What relationship is visible between state-level household income and childcare prices?
- How can key childcare price measures be communicated in a concise infographic?

## Dataset

**Source:** National Database of Childcare Prices  
**Input file:** `data/nationaldatabaseofchildcareprices.xlsx`  
**Study period:** 2008–2018

The original dataset contains **34,567 records and 227 columns**, covering **51 states/jurisdictions** and **3,144 counties** as reported in the notebook. After selecting the analysis fields and removing records missing required numeric values, the cleaned dataset contains **23,342 records and 17 columns**.

The cleaned data is saved as `results/childcare_cleaned.xlsx`.

## Tools & Technologies

- Python
- Jupyter Notebook
- pandas and NumPy
- Matplotlib and Seaborn
- OpenPyXL

## Project Workflow

1. **Load and inspect the data:** Review the dataset structure, years, geographic coverage, and fields.
2. **Clean and prepare the data:** Check duplicates and missing values, select relevant fields, and create the analysis dataset.
3. **Visualize historical trends:** Plot the sum of recorded weekly infant childcare prices by study year.
4. **Explore price distributions:** Examine variation in weekly infant childcare prices.
5. **Compare income and prices:** Plot state-level average household income against average infant childcare prices.
6. **Compare states:** Identify the 15 states with the highest and lowest average infant childcare prices in the analyzed data.
7. **Summarize visually:** Produce an infographic of selected childcare price measures.

## Visualizations

The notebook creates six figures:

- National childcare price trend
- Infant childcare price distribution
- Household income versus infant childcare price
- Top 15 states by average infant childcare price
- Bottom 15 states by average infant childcare price
- Childcare affordability infographic

Figures are saved in the `figures/` directory.

## Key Findings

The following figures come from the executed notebook's infographic and describe **annualized childcare price estimates** (weekly recorded price measures multiplied by 52), not actual annual household expenditure:

- **Highest and lowest state/jurisdiction averages:** The District of Columbia had the highest average annualized center-based infant childcare price at **$15,786**, compared with **$4,088** in Mississippi, the lowest in the analyzed records—a difference of **$11,698**.
- **Provider type:** The annualized average infant childcare price was **$7,576** for center-based care and **$5,896** for home-based care, a difference of **$1,680**.
- **Child age:** The annualized average center-based price was **$7,576** for infants, **$6,765** for toddlers, and **$6,340** for preschool-age children. Preschool care was approximately **16.3% lower** than infant care based on these averages.
- **Price measures:** The annualized averages of recorded 75th-percentile center-based prices were **$8,614** for infants, **$7,743** for toddlers, and **$7,288** for preschoolers, compared with **$7,576**, **$6,765**, and **$6,340**, respectively, for averages of recorded median-price measures.

**Analysis Note:** The visualizations present descriptive comparisons of childcare prices across years and states. The national trend sums recorded weekly prices rather than calculating a national average. State comparisons are based on retained records and are not population-weighted; the income comparison does not establish causation.

## Outcome

The project delivers **six saved visualizations**, an executed Jupyter notebook, and a cleaned dataset containing **23,342 records and 17 selected columns**. The visualizations make differences by location, provider type, and age group accessible for exploratory analysis and policy discussions.

## Installation / Running the Project

The project is organized under `Projects/Childcare_Cost_Analysis` in the portfolio repository. The notebook expects the input Excel dataset in the `data/` folder.

### Prerequisites

- **Python 3.11** (recommended, subject to dependency compatibility)
- **Git** — Available from [git-scm.com](https://git-scm.com/downloads) if not already installed.

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/Childcare_Cost_Analysis
```

### Step 2: Check the Dataset

The project uses `nationaldatabaseofchildcareprices.xlsx` in the `data/` directory. Confirm that the file is present before running the notebook; if it is not included in your checkout, obtain it from the original dataset source and place it at this path.

### Step 3: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

### Step 4: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 5: Open and Run the Notebook

Open `notebooks/Childcare_Affordability_Analysis.ipynb`, select the appropriate Python kernel, and use **Restart Kernel and Run All Cells**. The notebook saves its figures in `figures/` and the cleaned dataset in `results/`.

**Note:** Execution time may vary depending on the system's hardware and available resources.
