# Dynamic SIR Model 

### Code used to form a policy memo, "The New COVID-19 Variant Prediction with Dynamic Model", to the Government of Republic of Indonesia. July 25, 2021.

## Citation

Travel Cadence and Epidemic Spread, Lauren Streitmatter and Peter Zhang, Proceedings of Winter Simulation Conference 2021 (forthcoming).

[Draft available on arXiv.](https://arxiv.org/abs/2107.00203)

## Summary of Code

The code contains two part. 

### Part 1: Visualizing mobility trends and COVID case counts.

For all time series data, we used convolution to smooth out the trend. For example, the mobility level at day `t` is counted as the average of reported cases from day `t-6` to `t`. We set the smoothing window to be 7 days to reduce the impact of weekday vs weekend data.

### Part 2: Dynamic SIR Model

Building on a traditional SIR model, we created a dynamic SIR model where the simulation has three phases.

Phase 1: Spreading of disease with moderate travel and mobility restriction, reflecting the pre-Delta-variant situation in early 2021.\
Phase 2: Shutdown that reduces mobility significantly. \
Phase 3: Re-opening that eased mobility restriction.

Vaccination rates are also allowed to vary from Phase 1 to Phase 3.

## Data

Input data for the policy memo is not included for privacy reasons. To create your own input data, just create a csv file with the follow columns: 

`Date` \
`New_Case`	\
`Recovery`	\
`Death	Active_Case	Vac_1st_dose`	\
`Total_daily_test`	\
`Daily_Positivity_Rate` \
`Death rate`	\
`CFR`	\
`retail_and_recreation_percent_change_from_baseline`	\
`grocery_and_pharmacy_percent_change_from_baseline`	\
`parks_percent_change_from_baseline` \
`transit_stations_percent_change_from_baseline` \
`workplaces_percent_change_from_baseline`	\
`residential_percent_change_from_baseline` 

Useful sources to populate the data include:

Google Mobility \
Apple Mobility \
Our World in Data
