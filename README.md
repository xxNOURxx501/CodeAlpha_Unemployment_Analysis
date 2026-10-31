# Unemployment Analysis with Python

**CodeAlpha Data Science Internship — Task 2**

| Detail | Value |
|---|---|
| Student | Nour Ali Mohamed |
| Student ID | CA/DF1/414910 |
| Domain | Data Science |
| Project | Unemployment Analysis with Python |

## Project Overview

This project explores unemployment indicators in India using two supplied monthly datasets. It examines unemployment-rate distributions, differences between rural and urban observations, state and broad-region comparisons, monthly trends, and changes around the COVID-19 period beginning in March 2020.

## Objectives

- Clean and validate both supplied datasets.
- Explore unemployment, employment, and labour-force participation indicators.
- Visualize unemployment patterns across areas, states, and broad regions.
- Examine changes around the COVID-19 period.
- Discuss observable trends and possible economic or social implications.

## Datasets

Both CSV files were supplied for this project and are stored in `dataset/`.

### 1. `Unemployment in India.csv`
- Original shape: 768 rows × 7 columns.
- Contains state-level observations split by `Rural` and `Urban` areas.
- Date range after cleaning: May 2019 to June 2020.
- Inspection found 28 fully empty rows and 27 exact duplicate rows.
- After removing fully empty rows and exact duplicates: 740 rows × 7 columns, with no remaining missing values.

### 2. `Unemployment_Rate_upto_11_2020.csv`
- Shape: 267 rows × 9 columns.
- Contains monthly state-level observations, broad region labels, and geographic coordinates.
- Date range: January 2020 to October 2020.
- No missing values or exact duplicate rows were found.

The notebook strips whitespace from headers and text values, parses dates using day-first format, converts measurement fields to numeric values, and retains meaningful geographic/category fields. The identifier-like geographic columns are not used to calculate unemployment-rate summaries.

## Technologies

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Workflow

1. Import libraries and load both CSV files.
2. Inspect dimensions, columns, data types, missing values, duplicates, and descriptive statistics.
3. Clean whitespace, empty rows, duplicates, dates, and numeric fields.
4. Explore unemployment distributions and summary statistics.
5. Compare rural and urban observations.
6. Visualize monthly trends, state-level averages, and broad-region averages.
7. Compare observations before March 2020 with observations from March 2020 onward.
8. Explore calendar-month patterns while explaining the limits of the short time range.
9. Present findings and policy-relevant considerations.

## Main Findings from the Supplied Data

The following are descriptive averages calculated from the cleaned files:

- In the first dataset, the average unemployment rate was **13.17% for urban observations** and **10.32% for rural observations**.
- The five highest state/region averages in the first dataset were Tripura (28.35%), Haryana (26.28%), Jharkhand (20.58%), Bihar (18.92%), and Himachal Pradesh (18.54%).
- In the second dataset, the highest broad-region average was North (15.89%), while the lowest was West (8.24%).
- In the first dataset, the observation-level average unemployment rate was 9.51% before March 2020 and 17.77% from March 2020 onward.
- In the second dataset, the corresponding observation-level averages were 9.23% and 12.96%.

These period averages are calculated over available state/area observations, not as a population-weighted national unemployment rate. The datasets have different date coverage and grouping structures, so their values should be interpreted within each file rather than directly compared as identical samples.

## COVID-19 Interpretation

March 2020 is used as a descriptive marker for the COVID-19 period. The data show a clear increase in unemployment observations around April and May 2020. This temporal association does not prove that COVID-19 alone caused the change; other economic and measurement factors may also contribute.

## Seasonality Limitation

The first dataset spans approximately 14 months and the second spans 10 months. This is insufficient to confirm a repeating annual seasonal pattern. Calendar-month averages are included as exploratory summaries only. Multiple years of consistent monthly observations would be needed for stronger seasonal analysis.

## Installation

Use Python 3.12 for the pinned dependencies. Open a terminal in this project folder and create a virtual environment.

### Windows PowerShell

```powershell
py -3.12 -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Run the Notebook

1. Open the `Task_2_Unemployment_Analysis` folder in VS Code.
2. Install the Microsoft Python and Jupyter extensions.
3. Open `unemployment_analysis.ipynb`.
4. Select the `.venv` interpreter/kernel.
5. Click **Run All**.

The notebook uses relative paths and expects both CSV files inside `dataset/`.

## Project Structure

```text
Task_2_Unemployment_Analysis/
├── unemployment_analysis.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── dataset/
    ├── Unemployment in India.csv
    └── Unemployment_Rate_upto_11_2020.csv
```

## Notes

- The notebook is a descriptive data analysis project, not a causal-impact study.
- Do not merge the two files blindly: their time coverage and geographic aggregation differ.
- The original supplied CSV files are preserved unchanged in the `dataset` folder.
