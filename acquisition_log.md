# Acquisition Log

## Source 1: Chicago Traffic Crashes - Crashes
- Source URL: https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if
- Source organization: City of Chicago Open Data Portal / Chicago Police Department
- Access method: CSV export from the Chicago Data Portal
- Export date: [fill exact date if known]
- Date range used: 2025-01-01 to 2025-06-30
- Filters applied: Crash records restricted to the January 1, 2025 to June 30, 2025 project window
- Raw file saved as: `Traffic_Crashes_-_Crashes.csv` / zipped snapshot in `data_raw/`
- Snapshot location: `data_raw/`
- Notes on licensing / disclaimer: Source documentation and city data disclaimer reviewed and cited in project materials
- Notes on source stability / versioning: A frozen local snapshot was retained for reproducibility because portal data may change over time

## Source 2: Open-Meteo Historical Weather API
- Source URL: https://open-meteo.com/en/docs/historical-weather-api
- API endpoint: `https://archive-api.open-meteo.com/v1/archive`
- Access method: API request from notebook
- Request date: [fill exact date if known]
- Latitude: 41.88
- Longitude: -87.63
- Timezone: America/Chicago
- Start date: 2025-01-01
- End date: 2025-06-30
- Daily variables requested:
  - `weather_code`
  - `temperature_2m_mean`
  - `temperature_2m_max`
  - `temperature_2m_min`
  - `precipitation_sum`
  - `rain_sum`
  - `snowfall_sum`
  - `precipitation_hours`
- Raw JSON saved as: `openmeteo_daily_raw.json`
- Snapshot location: `data_raw/`
- Notes on terms / licensing: Open-Meteo terms and provenance documentation reviewed and cited in project materials; progress report describes the source as documented provenance / CC BY 4.0
- Notes on source stability / versioning: Raw JSON snapshot retained for reproducibility
