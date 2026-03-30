# IS537 Chicago Crash Weather Data Quality

This repository contains my IS537 course project on data quality assessment and integration of Chicago traffic crash records with historical weather data from Open-Meteo.

## Project Overview

This project examines how data quality assessment, cleaning, and integration decisions affect conclusions about daily crash frequency and injury severity under different weather conditions in Chicago.

The workflow combines two sources:

1. **Chicago Traffic Crashes dataset** from the City of Chicago Open Data Portal
2. **Open-Meteo Historical Weather API** for daily weather conditions in Chicago

The project focuses on fitness-for-use rather than causal inference. The goal is to understand how profiling, cleaning, uncertainty handling, and integration choices shape downstream descriptive analysis.

## Research Question

**How do data quality assessment, cleaning, and integration decisions affect conclusions about daily crash frequency and injury severity under different weather conditions in Chicago?**

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

## Repository Structure

```text
.
├── 01_crash_profiling.ipynb
├── 02_openmeteo_pull.ipynb
├── 03_daily_integration_and_checks.ipynb
├── data_raw/
├── data_processed/
├── figures/
├── references/
└── README.md
