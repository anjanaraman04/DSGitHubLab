# ETL Data Processor
By: Anjana Raman and Hima Sineni

## Overview
This project implements an ETL (Extract, Transform, Load) pipeline that processes car accident data and with remote weather data. The ETL processor ingests from both local files (CSV or JSON) and remote API calls.

## Features
- **Data Ingestion:**
  - Reads accident data from a CSV or JSON file.
    - CSV file source: https://www.kaggle.com/datasets/mlgodsiddharth/usa-accidents-dataset49-states-subset-of
  - Fetches historical weather data using the Open-Meteo API.
    - API source: https://open-meteo.com/en/docs/historical-weather-api
  
- **Data Transformation:**
  - Converts the `Start_Time` column to a date (without the time portion).
  - Drops rows with invalid dates.
  - Merges weather data with accident data.
  - Adds new weather-related columns and drops unwanted columns.
  
- **Data Storage:**
  - Saves transformed data to a SQLite database.
  - Supports output in CSV, JSON, or SQL formats.
  
- **Data Analysis:**
  - Performs simple aggregations on the transformed data.
    - Frequency of accidents by precipitation type
    - Frequency of accidents by maximum temperature

## How to Use

1. **Prepare the Data:**
   - Ensure your accident data file is in CSV or JSON format.
   - Place the file in your working directory or provide the full file path.

2. **Run the ETL Processor:**
   - Execute the script:
   - The program will prompt you for:
     - Output file format (`json`, `csv`, or `sql`).
     - Desired output file name (or SQL table name if using SQL).

3. **View the Output:**
   - If you selected `json` or `csv`, the transformed data will be saved as a file in the current directory.
   - If you selected `sql`, the data will be loaded into a SQLite database table, and analysis summaries will be printed.

4. **Review Logs and Summaries:**
   - The script prints the columns in the accident data, summaries of raw accident data, raw weather data, and transformed data.
   - It also prints analysis summaries (e.g., accident frequency by weather conditions).

