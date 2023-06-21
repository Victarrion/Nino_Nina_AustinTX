# Nino Nina AustinTX
Project-1 Of the UT Austin Data Analysis bootcamp. In this project we focus on analysing the effect that el Nino and La Nina have across the Austin metro area (Travis and Williamson county) and how it affects:
1. Temperature
2. Rainfall
3. Water Recharge Rate of the Edwards aquifer
4. Water quality
5. Water levels in Lake Travis
6. Electrical cost in kWh

Results:
# Research Question #1(Alexander Bates)
Identify whether el nino / la nina have correlated impact on the greater austin metro weather.

jupyter notebook: AMBProject1.ipnyb

datasources: noaa

references: https://www.ncei.noaa.gov/access/past-weather/Austin%2C%20Texas

step 1: 
-processing and reading in the granger datak
-filtering granger data to produce a chopped down dataframe 
-selecting statistical tools to process the data

step 2:
-processed the rest of the datasets based on the first dataset processing due to coming from the same source.
-proceed to aggregate the filtered datasets into a large dataset
-filtering the large complete set to statistical means to find an average of the set

step 3:
-producing line charts to visualize set averages
-visualizing el nino/la nina within the larger datasets
-check for individual correlation with the el nino/la nina temp and precipitation.

there was a slight correlation with el nino/la nina in the average temp but stronger with precipitation data in the tests done
