# Building Energy Consumption Forecasting (ASHRAE Great Energy Predictor III)

##  Project Overview
The goal of this project is to predict energy and water consumption (including water and wastewater services) for corporate and municipal facilities. 

The dataset covers approximately **2,000 buildings** across **16 global cities** over a one-year historical period, combined with corresponding meteorological data. The task is to forecast energy consumption for these facilities **1.5 years into the future**, leveraging known weather forecasts.

To solve this regression task, we implement a **Linear Regression** framework.

##  ETL Pipeline Overview
The Extract, Transform, Load (ETL) phase serves as the foundation of this project. It encompasses data ingestion, cleaning, and structural merging to prepare the raw data for advanced analytics, feature engineering, and model training.

For this pipeline, we extract **three primary datasets**:
1. **Building Metadata**: `building_metadata.csv.gz`  Structural features of the buildings.
2. **Target Metrics (Train)**: `train.0.0.csv.gz`  Historical energy consumption logs.
3. **Weather Data**: `weather_train.csv.gz`  Meteorological observations per location.
