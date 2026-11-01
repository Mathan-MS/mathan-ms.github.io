# Portfolio Cleanup Log

This log records broken items corrected, files or folders renamed or reorganized, and materials archived or removed. Projects follow the order shown on the portfolio website. The nine existing projects have been reviewed; Project 10 remains a placeholder.

## Project Cleanup Entries

### 1. Telecom Customer Churn Prediction

**Status:** Reviewed

- **Broken or corrected:** Standardized notebook directory output to display relative folder names instead of local Windows paths. Updated README installation instructions and improved Markdown documentation and result interpretations.
- **Renamed or reorganized:** Organized project files into the GitHub folder structure (`data/`, `notebooks/`, `figures/`, and `results/`) and standardized notebook references.
- **Archived or removed:** None documented.

### 2. U.S. Childcare Affordability Analysis

**Status:** Reviewed

- **Broken or corrected:** Improved notebook Markdown and chart interpretations, verified reported dataset counts against saved outputs, and updated the README with numerical findings and working repository installation instructions.
- **Renamed or reorganized:** Standardized README references to the existing `data/`, `notebooks/`, `figures/`, and `results/` project folders; no file or folder renames confirmed during this review.
- **Archived or removed:** Removed redundant portfolio and repository links and unnecessary dataset-download instructions from the README. No project files archived or removed.

### 3. AI-Based Residential Energy Efficiency Optimization

**Status:** Reviewed

- **Broken or corrected:** Expanded notebook Markdown interpretations and verified reported training and evaluation figures against saved outputs. Updated the README with specific results, installation instructions, and the current notebook filename.
- **Renamed or reorganized:** Renamed the notebook from `Energy_Efficiency_Optimization.ipynb` to `Residential_Energy_Efficiency.ipynb` and updated its README reference.
- **Archived or removed:** None documented.

### 4. Netflix Top 10 Content & Viewership Analysis

**Status:** Reviewed

- **Broken or corrected:** Updated notebook Markdown so interpretations follow the corresponding dataset previews and charts; corrected the runtime chart axis from minutes to hours and replaced displayed local Windows paths with relative folder names. Updated the README with findings and working GitHub installation instructions.
- **Renamed or reorganized:** Confirmed README references to the existing `data/`, `notebooks/`, and `figures/` folders and `Netflix_Viewership_Analysis.ipynb`; no file or folder renames documented.
- **Archived or removed:** Removed duplicate and repetitive limitation statements and outdated path commentary from notebook Markdown. No project files archived or removed.

### 5. U.S. Retail Sales Forecasting Using Time-Series Analysis

**Status:** Reviewed

- **Broken or corrected:** Corrected notebook data preparation to exclude six unavailable July–December 2021 observations; expanded interpretations after results and charts. Reviewed the executed 12-month SARIMA forecast and updated the README with the reported RMSE (59,819.07), findings, and working installation instructions.
- **Renamed or reorganized:** Standardized the project folder as `Retail_Sales_Forecasting` and the notebook as `Retail_Sales_Forecasting.ipynb`; aligned the README notebook path with `notebooks/Retail_Sales_Forecasting.ipynb`.
- **Archived or removed:** No source dataset files archived or removed; the original CSV was retained.

### 6. Hybrid Movie Recommendation System Using MovieLens

**Status:** Reviewed

- **Broken or corrected:** Added detailed interpretations after recommendation and similarity outputs; corrected an outdated interactive-test interpretation to describe the latest *Toy Story 2* run. Updated the README with the 70% collaborative / 30% content-based approach, verified examples, and repository installation instructions. Confirmed the existing dependency list includes `fuzzywuzzy` and `tabulate`.
- **Renamed or reorganized:** Retained the project folder `Movie_Recommender_System` and notebook `Movie_Recommender_System.ipynb`; aligned README paths accordingly.
- **Archived or removed:** None documented.

### 7. TSA Passenger Complaint & Airport Operations Analysis

**Status:** Reviewed

- **Broken or corrected:** Expanded interpretations immediately after six chart outputs and updated the README with numerical findings and setup instructions. Clarified that 2024 complaint coverage is incomplete and that the airport reference file includes international airports, so its regional distribution must not be interpreted as U.S.-only TSA complaint activity. Preserved the existing Python code.
- **Renamed or reorganized:** Used `TSA_Passenger_Complaint_Analysis` in the README installation path; the final local folder name should be checked against the repository before publishing.
- **Archived or removed:** None documented.

### 8. Predicting Road Accident Severity Using Machine Learning

**Status:** Reviewed

- **Broken or corrected:** Clarified README setup and execution instructions. Verified that a separately downloaded project writes generated figures to the project-level `figures/` directory.
- **Renamed or reorganized:** Organized project files under `data/`, `notebooks/`, `figures/`, and `results/` to match the GitHub project structure.
- **Archived or removed:** No archived or removed files documented.

### 9. MNIST Image Classification Using CNN

**Status:** Reviewed

- **Broken or corrected:** Expanded interpretations after model training, evaluation, and confusion-matrix outputs. After rerunning, corrected stale training, validation, test-loss, and classification-error figures to match the latest saved results (99.00% test accuracy; 0.0309 test loss). Updated the README with verified findings, generated outputs, and installation instructions; Python code was preserved.
- **Renamed or reorganized:** Standardized README references to `notebooks/MNIST_Image_Classification_CNN.ipynb` within `MNIST_Image_Classification_CNN`.
- **Archived or removed:** None documented.

### 10. Course Project – TBD

**Status:** Not yet available for review

- **Broken or corrected:** None documented.
- **Renamed or reorganized:** None documented.
- **Archived or removed:** None documented.

## Notes

- Record only confirmed changes; write **None** if no changes occurred.
- Use the individual project README for details that need more explanation.
- Project 10 is currently listed as **Course Project – TBD** on the portfolio website.
- Confirm the final TSA project folder name and that all revised files are committed to GitHub before considering the repository-wide cleanup complete.
