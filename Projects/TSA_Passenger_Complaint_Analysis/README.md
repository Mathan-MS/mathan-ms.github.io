# TSA Passenger Complaint & Airport Operations Analysis

## Project Overview

This project analyzes Transportation Security Administration (TSA) passenger complaint records to examine changes over time, identify leading complaint categories and subcategories, compare major airports, and visualize geographic patterns. Six visualizations summarize complaint volumes and the coverage of an airport reference dataset.

## Business Problem

Airport and security operations teams need to understand when and where passenger concerns are reported and which types of complaints account for the largest workloads. This project aims to:

- Examine monthly and annual complaint trends.
- Identify leading complaint subcategories and categories.
- Compare the distribution and variability of complaints at major airports.
- Map airports with high recorded complaint volumes.
- Assess geographic coverage of the airport reference data.
- Identify areas for further operational investigation without treating raw complaint counts as passenger-adjusted performance measures.

## Dataset

Four CSV files are included in the project's `data/` folder:

- `complaints-by-airport.csv` — airport-level complaint counts over time.
- `complaints-by-category.csv` — complaint counts grouped by broad category.
- `complaints-by-subcategory.csv` — complaint counts grouped by more detailed subcategory.
- `iata-icao.csv` — airport-code and location reference data, including international airports.

The complaint records span **2015 through January 2024**. **Only January is available for 2024**, so its count is not comparable with complete years. Category and subcategory data describe different groupings of complaint activity and should not be summed together.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Seaborn

## Project Workflow

1. **Data Loading**
   - Loaded the three complaint datasets and the airport reference file.
2. **Data Cleaning and Preparation**
   - Standardized field names and airport codes, converted dates, derived year/month fields, and handled missing complaint counts.
3. **Monthly and Annual Analysis**
   - Created a heatmap of recorded complaints by month and year.
4. **Subcategory Trends**
   - Examined monthly trends for the five leading complaint subcategories.
5. **Airport-Level Analysis**
   - Compared the monthly complaint distributions of the ten highest-total airports.
6. **Geographic Analysis**
   - Matched airport complaint records to geographic coordinates and mapped the 50 highest-total matched airports.
7. **Category Ranking and Reference Coverage**
   - Ranked the ten leading complaint categories and summarized airport entries by region in the international reference file.

## Visualizations

The notebook generates six `.jpg` charts in `figures/`:

- Monthly and annual TSA complaint heatmap.
- Leading complaint subcategories over time.
- Monthly complaint distributions across the top ten airports.
- Geographic distribution of complaints at matched airports.
- Top ten complaint categories.
- Regional distribution of airport entries in the international IATA/ICAO reference file.

Each chart is followed by a detailed interpretation in the notebook.

## Key Findings

- **Annual complaint trend:** Airport-level complaints declined from **112,610 in 2019** to **45,326 in 2020**, a decrease of approximately **59.7%**. They subsequently increased to **172,729 in 2023**. The 2024 data covers January only.
- **Leading complaint category:** **Expedited Passenger Screening Program** accounts for **569,943 of 1,021,281 category-level complaints**, approximately **55.8%**.
- **Leading subcategories:** **Expedited Passenger Screening Program (380,103)** and **Expedited Passenger Screening Program – TSA PreCheck (141,096)** are the two largest subcategory labels. They remain separate labels in the source data.
- **Airports with the highest recorded totals:** **Los Angeles (LAX): 24,794**, **New York JFK: 24,677**, and **Newark (EWR): 24,405**. These are absolute counts, not passenger-adjusted complaint rates.
- **Geographic pattern:** Larger cumulative complaint totals appear at major metropolitan airports. The map includes only airports successfully matched to geographic coordinates.
- **Reference-data coverage:** The regional chart counts airports in the **international** IATA/ICAO reference dataset, not TSA complaints by U.S. state. Alaska (331 entries) and Queensland (213 entries) are among its leading regions.

## Outcome

The analysis identifies periods, complaint types, and airports that warrant further review. The prominence of expedited-screening complaints suggests a useful area for targeted investigation, while the variation across airports and months can help guide workload monitoring.

A recommended next step is to combine complaint totals with passenger-screening volumes to calculate **complaints per million screened passengers**. This would support fairer comparisons across airports and time periods.

### Limitations

- Raw complaint totals do not account for differences in passenger traffic or establish airport service quality.
- The available 2024 complaint data covers January only.
- Category and subcategory files represent alternative classifications and must not be added together.
- The airport map excludes records without matched coordinates; the regional chart describes an international reference file rather than TSA complaint locations.
- The analysis is descriptive and does not establish causes of complaints.

## Installation / Running the Project

### Prerequisites

- Python 3.11 (recommended, subject to dependency compatibility)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/TSA_Passenger_Complaint_Analysis
```

### Step 2: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

The four CSV files are included in the project's `data/` folder.

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

Open `notebooks/TSA_Passenger_Complaint_Analysis.ipynb`, select the appropriate Python kernel, and choose **Kernel → Restart Kernel and Run All Cells**.

The notebook saves six `.jpg` visualizations to `figures/`. Execution time may vary depending on the system's hardware and available resources.
