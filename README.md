# IS537 Chicago Crash Weather Data Quality

This repository contains my IS537 course project on how data quality assessment, cleaning, and integration decisions affect conclusions about daily crash frequency and injury severity under different weather conditions in Chicago.

## Research Question

**How do data quality assessment, cleaning, and integration decisions affect conclusions about daily crash frequency and injury severity under different weather conditions in Chicago?**

## Data Sources

- **Chicago Traffic Crashes dataset** from the City of Chicago Open Data Portal
- **Open-Meteo Historical Weather API** for daily weather conditions in central Chicago

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
├── acquisition_log.md
├── cleaning_decisions.md
└── README.md
```
## Workflow

### 1. Crash Profiling
`notebooks/01_crash_profiling.ipynb`
- profiles missingness, uniqueness, date coverage, and category distributions
- creates `crash_day`
- aggregates crash records to daily level

### 2. Open-Meteo Pull and Profiling
`notebooks/02_openmeteo_pull.ipynb`
- pulls daily weather data for central Chicago
- creates `wet_day` and `snow_day`
- profiles coverage, missingness, and weather variability

### 3. Integration and Impact Assessment
`notebooks/03_daily_integration_and_checks.ipynb`
- merges crash and weather data by `crash_day`
- compares officer-reported and Open-Meteo-based wet/dry classification
- evaluates Scenario A, B, and C
- exports impact and quality-metric summaries
