# U.S. Retail Sales Forecasting

## Project Overview

This project analyzes monthly U.S. retail sales from January 1992 through June 2021 and builds a SARIMA time-series model to forecast the final 12 months of the dataset.

The analysis focuses on long-term growth, recurring seasonal behavior, historical disruptions, and forecast accuracy.

## Business Problem

Retail sales forecasting can support planning, budgeting, inventory management, and broader economic analysis.

This project is aimed at accomplishing the following goals:

- Identify long-term and seasonal patterns in U.S. retail sales.
- Build a SARIMA forecasting model.
- Forecast the final 12 months of the dataset.
- Compare predicted and actual retail sales.
- Evaluate forecasting accuracy using RMSE.

## Dataset

The project uses:

`us_retail_sales.csv`

The dataset contains monthly U.S. retail sales from January 1992 through June 2021.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- statsmodels
- SARIMA

## Project Workflow

The project follows these main steps:

1. **Data Preparation**
   - Loaded the retail sales dataset.
   - Reshaped yearly columns into a monthly time series.

2. **Exploratory Time-Series Analysis**
   - Reviewed long-term trends and recurring seasonal patterns.

3. **Train-Test Split**
   - Used historical data through June 2020 for training.
   - Reserved July 2020 through June 2021 for testing.

4. **Model Development**
   - Built a SARIMA(1,1,1)(1,1,1,12) model.

5. **Forecasting**
   - Forecasted the final 12 months of the dataset.

6. **Model Evaluation**
   - Compared actual and predicted retail sales.
   - Evaluated forecast error using RMSE.

## Model Evaluation

The forecasting model was evaluated using:

- AIC
- BIC
- HQIC
- Parameter significance
- RMSE

## Key Findings

The analysis identified several important patterns:

- U.S. retail sales show a long-term upward trend.
- Recurring year-end patterns indicate strong seasonality.
- Sales declined during the 2008–2009 financial crisis and the 2020 COVID-19 disruption.
- The SARIMA model captured historical seasonality but underestimated the rapid sales rebound in 2021.

## Outcome

This project demonstrates the use of SARIMA for seasonal retail-sales forecasting.

The results also show the limitations of historical time-series models when a series experiences rapid structural change.

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

`notebooks/US_Retail_Sales_Forecasting.ipynb`
