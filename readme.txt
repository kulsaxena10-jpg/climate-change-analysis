# 20-Year Climate Tracker (Ghaziabad / NCR)

A Python-based climate analysis and historical weather lookup tool that fetches, analyzes, and visualizes 20 years (2006–2025) of daily weather data using the [Open-Meteo Historical Weather API](https://open-meteo.com).

## Features

- **20-Year Historical Data Retrieval:** Fetches daily maximum, minimum, and mean temperatures (°C) along with precipitation totals (mm) from 2006 to 2025.
- **Offline Fallback Support:** Automatically generates a realistic 20-year synthetic dataset if the API is unreachable or blocked.
- **Local Caching:** Saves fetched data to `climate_20_years.csv` to avoid redundant API calls on subsequent runs.
- **Climate Trend Visualization:** Computes the warmest/coolest years on record, overall 20-year mean temperature, and saves a line chart (`20_year_trend.png`) of annual mean temperatures.
- **Interactive Date Inspector:** Allows querying any date between `2006-01-01` and `2025-12-31` to view daily weather metrics alongside the 20-year historical average and temperature anomaly for that specific calendar day.

## Prerequisites

Ensure you have Python 3.8+ installed along with the required libraries:

```bash
pip install requests numpy pandas matplotlib
```

## Configuration

You can customize the target location and date range at the top of the Python script:

```python
LATITUDE = 28.6692
LONGITUDE = 77.4538
CITY_NAME = "Ghaziabad / NCR"
START_DATE = "2006-01-01"
END_DATE = "2025-12-31"
CSV_FILE = "climate_20_years.csv"
```

## Usage

1. Save the script (e.g., `climate_tracker.py`) and ensure the API URL in `fetch_and_save_climate_data()` points to `https://open-meteo.com`.
2. Run the script from your terminal:

```bash
python climate_tracker.py
```

3. **View Outputs:**
   - The terminal will print the 20-year climate summary.
   - A plot of the annual temperature trend will display on screen and save as `20_year_trend.png`.
   - Use the interactive prompt to inspect specific dates:

```text
Enter a date to inspect (YYYY-MM-DD) or 'q' to quit: 2018-06-15

=== Weather Report for 2018-06-15 (Ghaziabad / NCR) ===
  Max Temperature : 41.2 °C
  Min Temperature : 29.8 °C
  Mean Temperature: 35.1 °C
  Precipitation   : 0.0 mm
  20-Yr Avg for 06-15: 34.45 °C (+0.65 °C anomaly)
=================================================
```

## Data Attribution

Historical weather data is provided by [Open-Meteo.com](https://open-meteo.com) under the [CC BY 4.0](https://creativecommons.org) license.
