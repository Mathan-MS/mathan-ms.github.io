# Netflix Viewership Analysis

## Project Overview

This project analyzes Netflix viewership data to identify patterns in global popularity, ranking longevity, ranking distribution, country-level content variety, early viewership performance, and the relationship between runtime and audience engagement.

Three Netflix datasets are used to examine viewing behavior from multiple perspectives. The project generates six visualizations that summarize important trends in Netflix content performance.

## Business Problem

Streaming platforms must understand which titles attract large audiences, which content remains popular over time, and how viewing patterns differ across markets.

This project explores several questions:

- Which Netflix titles receive the most global views?
- Which titles remain in the Top 10 for the longest periods?
- How are Top 10 ranking positions distributed?
- Which countries show the greatest variety of popular Netflix titles?
- Which titles receive the most views during their first 91 days?
- Is there a visible relationship between runtime and early viewership?

## Datasets

The project uses three Netflix datasets:

- `all-weeks-countries-netflix.xlsx`
- `all-weeks-global-netflix.xlsx`
- `most-popular-netflix.xlsx`

The datasets contain information about Netflix Top 10 rankings, weekly views, cumulative weeks in the Top 10, country-level rankings, runtime, and views during the first 91 days.

## Methods

The analysis includes:

1. Loading three Netflix datasets
2. Standardizing column names
3. Converting date and numeric fields
4. Creating combined title fields
5. Removing duplicate records
6. Aggregating global weekly views
7. Measuring cumulative Top 10 longevity
8. Grouping ranking positions
9. Counting unique popular titles by country
10. Comparing views during the first 91 days
11. Examining the relationship between runtime and viewership

## Visualizations

The notebook generates six visualizations:

- Top 10 most viewed Netflix titles globally
- Titles with the most weeks in the Top 10
- Distribution of ranking levels
- Content variety by country
- Most popular titles based on first 91-day views
- Runtime versus first 91-day views

All generated images are saved in the `figures/` folder.

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- Matplotlib
- Excel datasets

## Repository Structure

```text
Netflix_Viewership_Analysis/
│
├── README.md
│
├── data/
│   ├── all-weeks-countries-netflix.xlsx
│   ├── all-weeks-global-netflix.xlsx
│   └── most-popular-netflix.xlsx
│
├── figures/
│   ├── top10_most_viewed_titles_globally.jpg
│   ├── weeks_titles_remain_in_top10.jpg
│   ├── distribution_of_ranking_levels.jpg
│   ├── content_variety_by_country.jpg
│   ├── most_popular_titles_first_91_days.jpg
│   └── runtime_vs_views.jpg
│
└── notebooks/
    └── Netflix_Viewership_Analysis.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Place the three Excel datasets in the `data/` folder.

3. Install the required Python packages:

```bash
pip install pandas matplotlib openpyxl
```

4. Open:

```text
notebooks/Netflix_Viewership_Analysis.ipynb
```

5. Run the notebook cells in order.

The notebook automatically creates the `figures/` folder if it does not already exist.

## Key Skills Demonstrated

- Data cleaning and preparation
- Data aggregation
- Exploratory data analysis
- Data visualization
- Business interpretation of analytics
- Time-based viewership analysis
- Country-level comparison
- Python and pandas
- Matplotlib chart development

## Outcome

The project provides a visual overview of Netflix content performance and audience behavior. It highlights globally popular titles, long-running Top 10 content, differences in content variety across countries, and patterns in early title performance.

The findings can support content planning, marketing strategy, audience engagement, and international programming decisions.

## Limitations

The analysis is descriptive and is based only on the variables available in the supplied Netflix datasets. The visualizations identify patterns and relationships but do not establish causal relationships between content characteristics and viewership.

## Future Improvements

Potential extensions include:

- Comparing movies and television series separately
- Analyzing viewership changes over time
- Comparing regional viewing patterns
- Examining genre-level performance
- Adding interactive dashboards
- Building predictive models for content popularity
