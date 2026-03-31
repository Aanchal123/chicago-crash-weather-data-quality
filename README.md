# IS537 Chicago Crash Weather Data Quality

This repository contains my IS537 course project on data quality assessment and integration of Chicago traffic crash records with historical weather data from Open-Meteo.

## Project Overview

This project examines how data quality assessment, cleaning, and integration decisions affect conclusions about daily crash frequency and injury severity under different weather conditions in Chicago.

The project combines two meaningfully distinct sources:

1. **Chicago Traffic Crashes dataset** from the City of Chicago Open Data Portal (https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if/about_data)
2. **Open-Meteo Historical Weather API** for daily weather conditions in central Chicago (https://open-meteo.com/en/docs/historical-weather-api) 

The project focuses on **fitness-for-use** rather than causal inference. The goal is to understand how profiling, uncertainty handling, cleaning choices, and source integration shape downstream descriptive analysis.

## Research Question

**How do data quality assessment, cleaning, and integration decisions affect conclusions about daily crash frequency and injury severity under different weather conditions in Chicago?**

## Current Project Status

### Completed
- Acquired and locally snapshotted both data sources
- Profiled the Chicago crash dataset
- Profiled the Open-Meteo daily weather dataset
- Aggregated crash records to the daily level
- Integrated crash and weather data by date
- Evaluated integration quality
- Produced preliminary scenario-based impact comparisons
- Generated processed outputs, issue-check files, and visualizations

### In Progress
- Final repair decisions for candidate inconsistencies
- Stronger before/after quality metric comparison
- Final fitness-for-use narrative
- Final report packaging and reflection

## Data Sources

### 1. Chicago Traffic Crashes
Primary dataset containing officer-reported crash records.

Key attributes used:
- `CRASH_RECORD_ID`
- `CRASH_DATE`
- `WEATHER_CONDITION`
- `ROADWAY_SURFACE_COND`
- `LIGHTING_CONDITION`
- `MOST_SEVERE_INJURY`
- injury count fields
- location fields

### 2. Open-Meteo Historical Weather API
Secondary dataset containing daily weather observations for central Chicago.

Variables used:
- `weather_code`
- `temperature_2m_mean`
- `temperature_2m_max`
- `temperature_2m_min`
- `precipitation_sum`
- `rain_sum`
- `snowfall_sum`
- `precipitation_hours`

## Project Scope

- **Geographic scope:** Chicago
- **Time window:** January 1, 2025 to June 30, 2025
- **Integration level:** Daily
- **Primary comparison:** Wet vs dry day crash summaries
- **Secondary comparison:** Officer-reported vs Open-Meteo-based weather classification

## Repository Structure

```text
.
├── notebooks/
│   ├── 01_crash_profiling.ipynb
│   ├── 02_openmeteo_pull.ipynb
│   └── 03_daily_integration_and_checks.ipynb
├── data_raw/
├── data_processed/
├── figures/
├── Traffic_Crashes_-_Crashes.csv.zip
└── README.md
