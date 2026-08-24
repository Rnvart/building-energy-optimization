# Building Energy Consumption Forecasting (ASHRAE Great Energy Predictor III)

## Project Overview
The goal of this project is to predict energy and water consumption (including water and wastewater services) for corporate and municipal facilities.

The dataset covers approximately 2,000 buildings across 16 global cities over a one-year historical period, combined with corresponding meteorological data. The task is to forecast energy consumption for these facilities 1.5 years into the future, leveraging known weather forecasts. To solve this regression task, a Linear Regression framework is implemented.

---

## ETL Pipeline Overview
The ETL phase encompasses data ingestion, cleaning, and structural merging to prepare the raw data for feature engineering and model training.

The pipeline extracts three datasets:
* **Building Metadata** (`building_metadata.csv.gz`): Structural features of the buildings.
* **Target Metrics** (`train.0.0.csv.gz`): Historical energy consumption logs.
* **Weather Data** (`weather_train.csv.gz`): Meteorological observations per location.

---

## Implemented Preprocessing & Cleaning Steps
* **Data Merging**: Integrated datasets via relational left joins using `building_id` and a composite key `[site_id, timestamp]`.
* **Anomaly Removal**: Filtered out dead zero-readings for Building 0 (January to June) discovered during time-series visualization.
* **Data Imputation**: Applied linear time-series interpolation for missing weather data and group-median transformation for missing building parameters (`floor_count`, `year_built`).
