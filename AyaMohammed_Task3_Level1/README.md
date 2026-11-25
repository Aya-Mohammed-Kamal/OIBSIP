# Task 3: Data Cleaning

## Overview
This folder contains my data cleaning workflow for Oasis Infobyte (OIBSIP) Task 3 using `dirty_cafe_sales.csv` (10,000 rows and 8 columns). The goal was to inspect the raw dataset, handle missing values and invalid placeholders, standardise text and dates, check numeric outliers, fix column data types, and save a clean dataset ready for analysis.

## Folder Structure
- `Dataset/dirty_cafe_sales.csv` — Raw input dataset.
- `Dataset/cleaned_cafe_sales.csv` — Cleaned output dataset saved after completing all steps.
- Notebook (`.ipynb`) — Step-by-step cleaning code with markdown notes explaining each decision.
- `README.md` — Summary of the task and cleaning steps.

## Cleaning Steps
- **Data Quality Report:** Checked dataset shape, missing values (`6,826` total nulls after cleaning placeholders), duplicate rows (`0` exact duplicates), data types (all columns loaded as `str`), and value logic.
- **Missing Data Handling:** Replaced placeholders (`"ERROR"`, `"UNKNOWN"`, empty strings, and extra spaces) with `NaN`, then filled numeric columns (`Quantity`, `Price Per Unit`, `Total Spent`) with the median, categorical columns (`Item`, `Payment Method`, `Location`) with the mode, and `Transaction Date` with forward fill.
- **Duplicate Removal:** Checked for exact duplicate rows (`0` found and `0` removed, keeping all `10,000` rows).
- **Standardisation:** Cleaned text casing/spacing on categorical columns and converted `Transaction Date` into `datetime`.
- **Outlier Detection:** Checked numeric columns using the IQR method and applied capping (`clip`) to keep rows while limiting extreme values.
- **Data Type Correction:** Set IDs and text columns to `string`, numeric columns to `float64`, and `Transaction Date` to `datetime`, bringing data type accuracy from `0 / 8` to `8 / 8`.
- **Before vs. After & Export:** Compared key metrics before and after cleaning and exported the final dataset to `Dataset/cleaned_cafe_sales.csv`.

## Tools Used
- Python (`pandas`, `numpy`)
- VS Code / Jupyter Notebook
