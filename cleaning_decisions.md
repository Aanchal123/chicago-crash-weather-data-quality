# Cleaning and Repair Decisions

| Issue | Detection Method | Action Taken | Justification | Status |
|---|---|---|---|---|
| Crash date parsing | Date parsing check during crash profiling | Parsed `CRASH_DATE` and created `crash_day` for daily analysis | Daily aggregation and integration required a consistent date key | Repaired / Normalized |
| Weather and surface text variation | Categorical profiling and string matching prep | Stripped whitespace and uppercased values before grouping and checks | Needed consistent category matching across profiling and semantic checks | Repaired / Normalized |
| `WEATHER_CONDITION = UNKNOWN/OTHER` | Category counts and uncertainty profiling | Retained values and created `weather_unknown_flag` | Removing them would hide uncertainty; imputing weather categories was not justified for this use case | Retained / Flagged |
| `ROADWAY_SURFACE_COND = UNKNOWN/OTHER` | Category counts and uncertainty profiling | Retained values and created `surface_unknown_flag` | Same reasoning as above; useful for uncertainty-aware summaries | Retained / Flagged |
| Missing injury values | Missingness profiling | Left as missing; no imputation applied | Imputing injury counts without evidence could distort severity comparisons | Retained |
| Check A: `CLEAR` weather with wet/snow/ice surface | Cross-field semantic check | Retained for interpretation; not auto-repaired | IDOT manual defines both weather and roadway surface as conditions at the time of the crash, so clear weather with a wet or icy surface can be plausible | Flagged |
| Check B: snow/freezing weather with dry surface | Cross-field semantic check | Retained for interpretation; not auto-repaired | More suspicious than Check A, but still not repaired without stronger evidence from documentation or case context | Flagged |
| Check C: `UNKNOWN/OTHER` weather with known surface | Cross-field uncertainty check | Retained and used in uncertainty/sensitivity analysis | Useful indicator of uncertainty in officer-reported weather fields | Flagged |
| Daily aggregation of crash records | Structural transformation | Aggregated crash records to one row per day | Required to align crash data with daily Open-Meteo weather observations | Repaired / Normalized |
| Officer-reported vs external weather classification | Scenario-based impact assessment | Compared Scenario A, Scenario B, and Scenario C | Needed to assess how source choice and uncertainty handling affect downstream conclusions | Assessed |
| Scenario C threshold | Sensitivity analysis | Used a 10% `UNKNOWN/OTHER` weather-share threshold for low-uncertainty days | A 20% threshold excluded 0 days; 10% produced a meaningful robustness check by excluding 44 days and retaining 137 | Assessed |
