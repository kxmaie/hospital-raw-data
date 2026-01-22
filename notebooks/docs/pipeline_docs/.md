
## Purpose
Ingest raw CSV files from GitHub to Lakehouse Bronze tables and load it in lakehouse and make atransformation to make a clean data for analysis.

## Steps
1. Lookup config JSON for source files
2. Filter activity to check for only active csv to ingest
3. ForEach activity iterates over entities
4. Copy Data activity to Lakehouse
5. notebook for bronze layer
6. notebook for silver layer
7. notebook for gold layer

## Output
- `bronze_patients`
- `bronze_vitals`
- `bronze_labs`
- `silver_patients`
- `silver_labs`
- `silver_vitals`
- `gold_doctors_data`
- `gold_nursing_data`
