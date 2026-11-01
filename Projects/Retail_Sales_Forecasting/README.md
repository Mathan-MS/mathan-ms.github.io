# U.S. Retail Sales Forecasting Using Time-Series Analysis

## Project Overview

This project analyzes monthly U.S. retail sales from **January 1992 through June 2021** and evaluates a **Seasonal Autoregressive Integrated Moving Average (SARIMA)** model on the final 12 observed months. It combines data preparation, historical trend analysis, chronological model validation, and an actual-versus-predicted sales comparison.

## Business Problem

Reliable retail-sales forecasts can support inventory management, budgeting, staffing, and business planning. This project investigates whether historical trends and seasonal patterns provide useful forecasts when retail sales experience substantial changes.

The analysis aims to:

- Examine long-term sales trends and recurring seasonal behavior.
- Prepare a monthly time series from the source dataset's year-by-month layout.
- Fit a SARIMA model using historical observations only.
- Forecast the final 12 observed months and compare predictions with actual sales.
- Evaluate forecast accuracy and identify where the model performed poorly.

## Dataset

**File:** `data/us_retail_sales.csv`

The source file contains **30 annual records and 13 columns**: a year field and 12 monthly sales fields. The July–December 2021 entries have no reported values. After reshaping the data and excluding these six missing observations, the analysis uses **354 monthly observations**, spanning **January 1992–June 2021**.

The original CSV is retained unchanged. Numerical results below use the source dataset's reported sales units.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas and NumPy
- Matplotlib
- statsmodels (`SARIMAX`)

## Project Workflow

1. **Load and prepare the data:** Read the CSV, reshape the monthly columns into a date-indexed series, and exclude unreported values.
2. **Explore historical trends:** Visualize monthly sales to examine growth, seasonality, and periods of disruption.
3. **Split chronologically:** Use **January 1992–June 2020 (342 months)** for training and **July 2020–June 2021 (12 months)** for testing.
4. **Fit the forecasting model:** Estimate **SARIMA(1,1,1)(1,1,1,12)** on the training observations.
5. **Generate forecasts:** Predict the 12-month test period without using its actual sales to fit the model.
6. **Evaluate performance:** Compare forecasts with observed sales and calculate root mean squared error (RMSE).
7. **Save outputs:** Export charts to `figures/` and evaluation tables to `results/`.

## Model Evaluation

| Measure | Saved notebook result |
|---|---:|
| Training observations | 342 months |
| Test observations | 12 months |
| AIC | 6,430.359 |
| BIC | 6,449.122 |
| HQIC | 6,437.855 |
| Test RMSE | **59,819.07** |

AIC, BIC, and HQIC describe the fitted model and are primarily useful for comparing candidate models on the same training data. **RMSE evaluates the forecasts against the held-out observations**; lower RMSE indicates smaller forecast errors in the source dataset's units.

## Key Findings

- **Long-term growth with seasonal variation:** Monthly retail sales generally increased from 1992 to 2021, with recurring within-year changes and notable disruptions around 2008–2009 and 2020.
- **Consistent underestimation:** The SARIMA forecast was **below actual sales in all 12 test months** from July 2020 through June 2021.
- **Largest monthly shortfall:** In **April 2021**, actual sales were **562,269**, compared with **436,617.4** predicted—a difference of approximately **125,652** in the source dataset's units.
- **Forecast accuracy:** The **12-month RMSE was 59,819.07**. The rapid increase in observed sales during 2021 was not captured by the fitted model's forecasts.

## Visualizations

The notebook generates the following files:

| File | Description |
|---|---|
| `figures/us_monthly_retail_sales_trend.png` | Historical monthly retail-sales trend |
| `figures/actual_vs_predicted_retail_sales.png` | Actual and predicted sales during the 12-month test period |
| `results/forecast_results.csv` | Monthly actual and predicted sales |
| `results/model_metrics.csv` | AIC, BIC, HQIC, and RMSE |

## Outcome

The project demonstrates an end-to-end seasonal forecasting workflow, including time-series preparation, chronological validation, model diagnostics, and communication of forecast errors. The consistent underestimation highlights the importance of reviewing forecasts when economic conditions shift rapidly.

Potential next steps include comparing the model against a **seasonal-naïve baseline**, evaluating alternative SARIMA specifications, and using rolling-origin validation. This project evaluates **one SARIMA specification on one 12-month test period**, so it does not establish superiority over simpler forecasting approaches.

## Installation / Running the Project

### Prerequisites

- **Python 3.11** (recommended, subject to dependency compatibility)
- **Git** — available from [git-scm.com](https://git-scm.com/downloads)

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/Retail_Sales_Forecasting
```

### Step 2: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

Open `notebooks/Retail_Sales_Forecasting.ipynb`, select the appropriate Python kernel, and choose **Kernel → Restart Kernel and Run All Cells**.

The notebook reads the included CSV from `data/`, saves charts in `figures/`, and saves forecast and metric tables in `results/`. **Execution time may vary depending on the system's hardware and available resources.**
