# Netflix Viewership Analysis

## Project Overview

This project analyzes Netflix viewership data to identify patterns in global popularity, ranking longevity, ranking distribution, country-level content variety, early viewership performance, and the relationship between runtime and audience engagement.

Three Netflix datasets are used to examine viewing behavior from multiple perspectives.

## Business Problem

Streaming platforms need to understand which titles attract large audiences, which content remains popular over time, and how viewing patterns differ across markets.

This project is aimed at accomplishing the following goals:

- Identify the most viewed Netflix titles globally.
- Examine how long titles remain in the Top 10.
- Analyze the distribution of ranking levels.
- Compare content variety across countries.
- Identify titles with the strongest first 91-day performance.
- Examine whether runtime appears related to early viewership.

## Dataset

The project uses three Netflix datasets:

- `all-weeks-countries-netflix.xlsx`
- `all-weeks-global-netflix.xlsx`
- `most-popular-netflix.xlsx`

The datasets contain information about Netflix Top 10 rankings, weekly views, cumulative weeks in the Top 10, country-level rankings, runtime, and views during the first 91 days.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- OpenPyXL

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded the three Netflix datasets.

2. **Data Cleaning and Preparation**
   - Standardized column names.
   - Converted date and numeric fields.
   - Created combined movie and season titles.
   - Removed duplicate records.

3. **Global Viewership Analysis**
   - Aggregated total weekly views by title.
   - Identified the most viewed titles globally.

4. **Top 10 Longevity Analysis**
   - Measured cumulative weeks in the Netflix Top 10.

5. **Ranking Distribution Analysis**
   - Grouped ranking positions into top, middle, and lower ranges.

6. **Country-Level Analysis**
   - Compared the number of unique popular titles by country.

7. **Early Viewership Analysis**
   - Compared views during the first 91 days.
   - Examined the relationship between runtime and early viewership.

## Visualizations

The analysis includes:

- Top 10 most viewed Netflix titles globally
- Titles with the most weeks in the Top 10
- Distribution of ranking levels
- Content variety by country
- Most popular titles based on first 91-day views
- Runtime versus first 91-day views

## Key Findings

The analysis showed that Netflix performance varies across titles, countries, and time.

Key findings include:

- A relatively small number of titles generate very high global viewership.
- Some titles remain in the Top 10 for much longer than others.
- Content variety differs across countries.
- Strong early viewership is concentrated among a small number of titles.
- Runtime alone does not show a clear relationship with early viewership.

## Outcome

This project provides a visual summary of Netflix audience behavior and content performance.

The findings can support content planning, promotion, audience engagement, and international programming decisions.

## Installation / Running the Project

1. Clone the repository.

2. Place the three Excel files in the `data/` folder.

3. Install the required packages:

```bash
pip install pandas matplotlib openpyxl
```

4. Open and run:

`notebooks/Netflix_Viewership_Analysis.ipynb`
