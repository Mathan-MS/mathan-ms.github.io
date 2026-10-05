# TSA Complaints Analysis

## Project Overview

This project analyzes Transportation Security Administration (TSA) complaint data across U.S. airports. The analysis examines complaint activity over time, complaint subcategories, monthly complaint distributions at major airports, geographic complaint patterns, complaint-category rankings, and airport distribution by region.

Four TSA-related datasets are used to create six visualizations that summarize important complaint and airport patterns.

## Business Problem

Understanding where and when passenger complaints occur can help identify areas of concern within airport security operations and passenger service.

This project explores several questions:

- How do TSA complaint volumes change by month and year?
- Which complaint subcategories contribute the most complaints?
- Which major airports show the highest complaint levels and variability?
- Where are TSA complaints geographically concentrated?
- Which complaint categories occur most frequently?
- How are airports distributed across regions?

## Datasets

The project uses four CSV files:

- `complaints-by-airport.csv`
- `complaints-by-category.csv`
- `complaints-by-subcategory.csv`
- `iata-icao.csv`

The complaint datasets contain complaint counts by airport, category, and subcategory. The airport reference dataset provides airport codes, geographic coordinates, and regional information.

## Methods

The project follows these main steps:

1. Load the four TSA-related datasets
2. Standardize column names
3. Convert date fields
4. Create year and month variables
5. Remove missing or blank airport codes
6. Standardize airport-code formatting
7. Replace missing complaint counts with zero
8. Aggregate complaint activity by time period
9. Analyze major complaint subcategories and categories
10. Compare complaint distributions across major airports
11. Merge complaint data with airport-location data
12. Visualize airport distribution by region

## Visualizations

The notebook creates six visualizations:

- Complaint activity by month and year
- Complaint trends by subcategory over time
- Monthly complaint distribution across top airports
- Spatial distribution of TSA complaints by airport
- Complaint category ranking
- Airport distribution by region

All generated images are saved in the `figures/` folder.

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- Matplotlib
- Seaborn

## Repository Structure

```text
TSA_Complaints_Analysis/
│
├── README.md
│
├── data/
│   ├── complaints-by-airport.csv
│   ├── complaints-by-category.csv
│   ├── complaints-by-subcategory.csv
│   └── iata-icao.csv
│
├── figures/
│   ├── complaint_activity_by_month_and_year_heatmap.jpg
│   ├── complaint_trends_by_subcategory_over_time.jpg
│   ├── monthly_complaint_distribution_top_airports.jpg
│   ├── spatial_distribution_of_tsa_complaints.jpg
│   ├── complaint_category_ranking.jpg
│   └── airport_distribution_by_region.jpg
│
└── notebooks/
    └── TSA_Complaints_Analysis.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Place all four CSV files in the `data/` folder.

3. Install the required Python packages:

```bash
pip install pandas matplotlib seaborn
```

4. Open:

```text
notebooks/TSA_Complaints_Analysis.ipynb
```

5. Run the notebook cells in order.

The notebook automatically creates the `figures/` folder if it does not already exist.

## Key Skills Demonstrated

- Data cleaning and preparation
- Data aggregation
- Time-based analysis
- Airport-level comparison
- Geographic data integration
- Exploratory data analysis
- Data visualization
- Heat maps
- Stacked area charts
- Box plots
- Spatial scatter plots
- Lollipop charts
- Python and pandas
- Matplotlib and Seaborn

## Outcome

The analysis identifies major patterns in TSA complaint activity, including a sharp decline in 2020 followed by strong growth beginning in 2022. Screening-related complaints represent a major portion of complaint activity, while major airports show differences in both complaint volume and variability.

The project also highlights the geographic concentration of complaints at major metropolitan airports and differences in airport distribution across U.S. regions.

## Limitations

The analysis is descriptive and is based only on the complaint and airport-reference variables available in the supplied datasets. Higher complaint totals may reflect factors such as passenger volume, airport size, or travel disruptions, but those factors are not directly measured in the complaint data.

## Future Improvements

Potential enhancements include:

- Normalizing complaint counts by airport passenger volume
- Comparing complaint rates rather than raw counts
- Adding airport traffic or delay data
- Analyzing complaint trends by category and airport together
- Creating interactive geographic maps
- Building dashboards for airport-level complaint monitoring
