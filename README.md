# Nino Nina AustinTX


# Question: How does el Nino and Nina affect average temperature, rainfall, the edwards aquifer recharge rate, Lake Travis water level, and electricity cost.

Project-1 Of the UT Austin Data Analysis bootcamp. In this project we focus on analysing the effect that el Nino and La Nina have across the Austin metro area (Travis and Williamson county) and how it affects:
1. Temperature
2. Rainfall
3. Water Recharge Rate of the Edwards aquifer
5. Water levels in Lake Travis
6. Electrical cost in KWh


#Our Methodology 

For this data we did the following:
1. Temperature
   
3. Rainfall
   
4. Water Recharge Rate of the Edwards aquifer

   
6. Water levels in Lake Travis:
Pulled historical water levels going back to 1940 from the Lower Colorado River Authority. This Data measure several daily time stamps. This was too granular for our needs so I Filtered out the data to only use the first measurement of each month. Once this was filtered. I grab the years from 

8. Electrical cost in kWh:

#Results:
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
