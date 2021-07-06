# Data cleaning project - NYC Trees
![](new-york-traffic.jpeg)

## Mission objectives

Clean properly a dataset for the Machine Learning process.

## Tools used

- Pandas
- Plotly for data visualization

## Database

For this data cleaning project, we are working with a sample of the database ['2015 Street Tree Census - Tree Data'](https://data.cityofnewyork.us/Environment/2015-Street-Tree-Census-Tree-Data/uvpi-gqnh) provided by the Department of Parks and Recreation (DPR). The original database has information about 684k trees. In our sample, we have 100k trees (14,62%).

We find 28 columns (already combining the date and hour together when loading the database). All are not useful for machine learning, so we'll do some cleaning and only keep the relevant ones. Some information is also redundant, so we'll get rid of them.

## Data visualization
We create a map in Plotly to see where crashes are happening in NYC.

![](nyc_crash_map_1.png)
![](nyc_crash_map_2.png)
![](nyc_crash_map_3.png)
![](nyc_crash_map_4.png)

## Cleaning
### Removing rows
- if 'location', 'latitude' and 'longitude' are all empty
- if 'latitude' or 'longitude' are out of NYC

### Removing columns that are redundant or not useful for ML
- 'location' 
- 'borough'
- 'on_street_name'
- 'off_street_name'
- 'cross_street_name'
- 'collision_id'

### To keep it simple, we remove information related to the vehicle type

## New columns
Based on 'date_time', I create new useful information easier to process for the ML:
- 'hour'
- 'day_of_week' (Monday, ...)
- 'day'
- 'month'
- 'year'

## We One-Hot Code the columns related to the 'Contributing factors'