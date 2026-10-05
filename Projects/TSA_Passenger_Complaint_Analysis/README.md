# TSA Complaints Analysis

## Project Overview

This project analyzes Transportation Security Administration (TSA) complaint data across U.S. airports.

The analysis examines complaint activity over time, complaint subcategories, complaint distributions at major airports, geographic complaint patterns, complaint-category rankings, and airport distribution by region.

## Business Problem

Understanding when and where passenger complaints occur can help identify areas of concern within airport security operations and passenger service.

This project is aimed at accomplishing the following goals:

- Analyze complaint volume by month and year.
- Identify major complaint subcategories.
- Compare complaint distributions across major airports.
- Examine the geographic distribution of complaints.
- Rank major complaint categories.
- Compare airport distribution across regions.

## Dataset

The project uses four TSA-related CSV files:

- `complaints-by-airport.csv`
- `complaints-by-category.csv`
- `complaints-by-subcategory.csv`
- `iata-icao.csv`

The complaint datasets contain complaint counts by airport, category, and subcategory. The airport reference dataset provides airport codes, geographic coordinates, and regional information.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Seaborn

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded the complaint and airport reference datasets.

2. **Data Cleaning and Preparation**
   - Standardized column names.
   - Converted date fields.
   - Created year and month variables.
   - Removed missing or blank airport codes.
   - Standardized airport-code formatting.
   - Replaced missing complaint counts with zero.

3. **Time-Based Complaint Analysis**
   - Analyzed complaint activity by month and year.

4. **Complaint Subcategory Analysis**
   - Identified the most common complaint subcategories and their trends.

5. **Airport-Level Analysis**
   - Compared complaint distributions across major airports.

6. **Geographic Analysis**
   - Combined complaint data with airport coordinates.

7. **Complaint Category and Regional Analysis**
   - Ranked complaint categories.
   - Compared airport distribution across regions.

## Visualizations

The analysis includes:

- Complaint activity by month and year
- Complaint trends by subcategory over time
- Monthly complaint distribution across top airports
- Spatial distribution of TSA complaints by airport
- Complaint category ranking
- Airport distribution by region

## Key Findings

The analysis identified several major patterns:

- TSA complaints fell sharply in 2020 and increased strongly beginning in 2022.
- Expedited Passenger Screening Program complaints account for a large share of complaint activity.
- Major airports such as JFK and LAX show relatively high complaint levels and greater variability.
- Complaint activity is concentrated around major metropolitan airports.
- Airport distribution differs significantly across regions.

## Outcome

This project provides a structured view of TSA complaint patterns across time, complaint types, airports, and regions.

The findings can support further analysis of airport service quality, passenger experience, and security operations.

## Installation / Running the Project

1. Clone the repository:

```bash
git clone <repo_url>
cd <repository_name>
```

2. Place the four CSV files in the `data/` folder.

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:

```bash
jupyter notebook
```

5. Open and run:

`notebooks/TSA_Complaints_Analysis.ipynb`
