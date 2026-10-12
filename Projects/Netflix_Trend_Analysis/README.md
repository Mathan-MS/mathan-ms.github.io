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
- NumPy
- Matplotlib
- OpenPyXL

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded the three Netflix datasets.

2. **Data Cleaning and Preparation**
   - Standardized column names.
   - Converted date and numeric fields.
   - Created combined title fields.
   - Removed duplicate records.

3. **Global Viewership Analysis**
   - Aggregated total weekly views by title.
   - Identified the most viewed titles globally.

4. **Top 10 Longevity Analysis**
   - Measured cumulative weeks in the Netflix Top 10.

5. **Ranking Distribution Analysis**
   - Grouped ranking positions into ranges.

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

- **Global viewership:** *Leave the World Behind* and *Extraction 2* are among the titles with the highest aggregated reported weekly views in the global Top 10 data.
- **Top 10 longevity:** *Yo Soy Betty, la fea* and *Manifest* stand out for sustained appearances in the global Top 10.
- **Ranking distribution:** The country-level ranking records fall into three bands: **30%** in ranks 1–3, **40%** in ranks 4–7, and **30%** in ranks 8–10. The middle band covers four positions, while the other bands cover three each.
- **Country-level variety:** Trinidad and Tobago, Canada, and New Zealand are among the countries with the most distinct titles appearing in the country-level Top 10 data.
- **First 91-day performance:** *Squid Game* and *Wednesday* feature among the strongest early-viewership titles. The source data also reports **230.9 million first-91-day views** for *Red Notice*.
- **Runtime and viewership:** The scatterplot shows high-viewership titles across different runtimes, without a clear linear pattern.

## Outcome

This project provides a visual summary of Netflix audience behavior and content performance.

The findings can support content planning, promotion, audience engagement, and international programming decisions.

## Installation / Running the Project

### Prerequisites

- **Python 3.11** (recommended, subject to dependency compatibility)
- **Git** — [Download Git](https://git-scm.com/downloads) if it is not installed.

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/Netflix_Trend_Analysis
```

### Step 2: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

The three Excel datasets are included in the project's `data/` folder.

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

Open `notebooks/Netflix_Viewership_Analysis.ipynb`, select the appropriate Python kernel, and choose **Kernel → Restart Kernel and Run All Cells**.

The notebook generates six `.jpg` visualizations in `figures/`.

**Note:** Execution time may vary depending on the system's hardware and available resources.
