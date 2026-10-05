# U.S. Retail Sales Forecasting

## Project Overview

This project analyzes monthly U.S. retail sales from January 1992 through June 2021 and builds a SARIMA time-series model to forecast retail sales for the final 12 months of the dataset.

The analysis examines long-term growth, recurring seasonal behavior, historical disruptions, and forecasting accuracy.

## Business Problem

Retail sales forecasting can support planning, budgeting, inventory management, and broader economic analysis. This project explores whether historical monthly U.S. retail sales can be used to forecast future sales while accounting for trend and seasonality.

Key questions include:

- What long-term and seasonal patterns are visible in U.S. retail sales?
- Can a SARIMA model capture those patterns?
- How well does the model forecast the final 12 months of the dataset?
- How large is the forecast error during a period of rapid post-COVID change?

## Dataset

The project uses:

`us_retail_sales.csv`

The dataset contains monthly U.S. retail sales from January 1992 through June 2021.

## Methods

The project follows these main steps:

1. Load and reshape the retail sales dataset into a monthly time series
2. Explore long-term and seasonal sales patterns
3. Split the data chronologically into training and test sets
4. Fit a SARIMA(1,1,1)(1,1,1,12) forecasting model
5. Forecast the final 12 months of the dataset
6. Compare predicted and actual retail sales
7. Evaluate forecast accuracy using RMSE
8. Save figures and forecasting results for portfolio use

## Model

The forecasting model is:

`SARIMA(1,1,1)(1,1,1,12)`

The seasonal period of 12 represents annual seasonality in monthly retail sales.

Model diagnostics include:

- AIC
- BIC
- HQIC
- Parameter significance
- RMSE

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- statsmodels
- SARIMA time-series forecasting

## Project Outputs

### Figures

`figures/`

- `us_monthly_retail_sales_trend.png`
- `actual_vs_predicted_retail_sales.png`

### Results

`results/`

- `forecast_results.csv`
- `model_metrics.csv`

## Repository Structure

```text
US_Retail_Sales_Forecasting/
│
├── README.md
│
├── data/
│   └── us_retail_sales.csv
│
├── figures/
│   ├── us_monthly_retail_sales_trend.png
│   └── actual_vs_predicted_retail_sales.png
│
├── results/
│   ├── forecast_results.csv
│   └── model_metrics.csv
│
└── notebooks/
    └── US_Retail_Sales_Forecasting.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Place the dataset in:

```text
data/us_retail_sales.csv
```

3. Install the required Python packages:

```bash
pip install pandas numpy matplotlib statsmodels
```

4. Open:

```text
notebooks/US_Retail_Sales_Forecasting.ipynb
```

5. Run the notebook cells in order.

The notebook automatically creates the `figures/` and `results/` folders if they do not already exist.

## Key Skills Demonstrated

- Time-series data preparation
- Exploratory time-series analysis
- Chronological train-test splitting
- SARIMA forecasting
- Seasonal modeling
- Forecast visualization
- Model evaluation with RMSE
- Python and pandas
- statsmodels

## Outcome

The SARIMA model captures the historical trend and seasonal structure of U.S. retail sales but underestimates the rapid sales increase during the 2021 test period. The project demonstrates both the value and limitations of traditional time-series forecasting when a series experiences sudden structural change.

## Limitations

The model relies only on historical retail sales and does not include external variables such as inflation, employment, government stimulus, consumer confidence, or other economic indicators. These factors may help explain unusual changes during periods such as the COVID-19 recovery.

## Future Improvements

Potential improvements include:

- Testing additional SARIMA parameter combinations
- Comparing SARIMA with exponential smoothing or Prophet
- Adding external economic indicators
- Using rolling-window validation
- Testing machine-learning or deep-learning forecasting approaches
- Evaluating forecast performance across multiple historical periods
