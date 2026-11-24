# Steel Industry Energy Consumption Prediction — Machine Learning Pipeline

## Project Overview

This repository contains an end-to-end machine learning pipeline for predicting and analyzing industrial electrical load and energy consumption in the steel manufacturing sector. Using high-frequency sensor and operational data across 35,040 records, the project models energy usage patterns to optimize factory power management and operational efficiency. I did this project in collaboration with United Network Of Professionals (UNP) on Credit Card Risk Prediction Using Python.This is a group project completed as part of our internship. 
The link for the project materials(code and PPT) is :

GOOGLE COLAB FILE LINK: https://drive.google.com/file/d/1Qi0W6WXufgNEA1FNdK1uCt97FHC8mEEh/view?usp=sharing

PROJECT PRESENTATION FILE LINK: https://docs.google.com/presentation/d/1M-Ka7LDKdC2miXN138mPePIfSluGL2Ds/edit?usp=sharing&ouid=109298726136836996811&rtpof=true&sd=true

## Problem Statement

Steel manufacturing is an energy-intensive industrial process characterized by heavy machinery, continuous operations, and fluctuating electrical loads. Unoptimized power consumption leads to high utility costs and demand charges. The business problem is to build an accurate predictive regression model capable of forecasting energy usage (`Usage_kWh`) based on electrical characteristics, reactive power metrics, and temporal patterns.

## Objectives

* Load and clean high-frequency industrial datasets comprising 35,040 observations captured at 15-minute intervals.

* Perform feature engineering to extract cyclic temporal features (such as seconds from midnight) and operational indicators.

* Drop data leakage variables (e.g., `CO2(tCO2)`) to ensure robust out-of-sample generalization.

* Train and evaluate machine learning regression models (Random Forest) to accurately predict electrical load.

* Evaluate predictive performance using standard regression metrics ($R^2$, RMSE, and MAE).

## Technologies Used

* **Language:** Python 3

* **Environment:** Jupyter Notebook / Google Colab

* **Libraries:**

  * `pandas` & `numpy` — Data loading, cleaning, manipulation, and numerical computations

  * `matplotlib` & `seaborn` — Statistical visualizations, feature distribution plots, and actual vs. predicted trend lines

  * `scikit-learn` — Model training (Random Forest Regressor), cross-validation, and performance evaluation metrics

## Methodology

### 1. Data Loading & Inspection

* Loaded the raw industrial dataset containing **35,040 records** capturing factory operations at 15-minute intervals.

* Inspected feature data types, checked for missing values, and verified data integrity across electrical and operational columns.

### 2. Feature Engineering & Data Cleaning

* **Temporal Extraction:** Derived cyclic time features from timestamps, specifically calculating the number of seconds from midnight to capture daily operational cycles and shift patterns.

* **Leakage Removal:** Excluded post-hoc or target-derived columns (such as `CO2(tCO2)`) to prevent data leakage during model training.

* **Data Cleansing:** Handled outliers and normalized feature distributions where necessary.

### 3. Exploratory Data Analysis (EDA)

* Analyzed power consumption distribution (`Usage_kWh`) across different hours of the day and days of the week.

* Examined correlations between energy consumption, lagging/leading reactive power, and power factors.

### 4. Model Training

* Implemented **Random Forest Regression** to model non-linear relationships between electrical parameters and energy usage.

* Split data into training and testing sets to validate model robustness against unseen operational cycles.

## Model Evaluation & Performance

The Random Forest model achieved exceptional predictive performance on the test dataset:

* $R^2$ **Score:** `0.9995` (explaining 99.95% of the variance in energy consumption)

* **Root Mean Squared Error (RMSE):** `0.72 kWh`

* **Mean Absolute Error (MAE):** `0.28 kWh`

## Key Insights

* **Peak Production Patterns:** The model effectively captures high-load operational cycles and factory shift transitions, providing actionable insights into industrial electrical demand.

* **Reactive Power Importance:** Lagging and leading reactive power metrics serve as strong predictors for electrical load fluctuations.

## Project Structure

```text
├── data/
│   └── steel_industry_data.csv   # Raw operational dataset (35,040 records)
├── notebooks/
│   └── energy_prediction.ipynb   # Jupyter notebook containing EDA, feature engineering, and modeling
└── README.md                     # Project documentation
```

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter openpyxl
```

### 3. Run the Notebook

1. Place your dataset inside the `data/` directory (or update the file path in the notebook).

2. Launch Jupyter Notebook:

```bash
jupyter notebook
```
