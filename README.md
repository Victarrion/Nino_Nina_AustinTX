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
1. Temperature and Rainfall
   
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
   
4. Water Recharge Rate of the Edwards aquifer

   
6. Water levels in Lake Travis:
-Pulled historical water levels going back to 1940 from the Lower Colorado River Authority. This Data measure several daily time stamps. This was too granular for our needs so I Filtered out the data to only use the first measurement of each month.
-I grab the years from 2020 foward and plotted the results over our abstract Nino/Nina intensity timeline to reach our results.
-We saw a rapid water level rise around 9-12 months after the start of the nino. This desync could be because of out timestamps no being of the same granularity between out dataframes

8. Electrical cost in kWh:
-Obtained historical data regarding electrical cost per KWh of Austin power since 2020.
-Ajusted rates to inflation.
-Plotted rates per year over Nino/Nina Intensity chart hoping to observe a trendline. None were observed in the first decade but in the second decade a correlation appeared to form but no conclusion was reached.

#Results:
Results:
# Research Question #1(Alexander Bates)
Identify whether el nino / la nina have correlated impact on the greater austin metro weather.

jupyter notebook: AMBProject1.ipnyb

datasources: noaa

references: https://www.ncei.noaa.gov/access/past-weather/Austin%2C%20Texas


# Research Question #3(Leonardo Bolanos)
Did el Nino affect the significantly the water levels in lake travis?
-We did observe rapid water level increases in the lake during Nino years and concluded there is corelation.
Did el Nino affect the significantly affect electricity rate in Austin?
-We were unable to conclude a definitive conclusion. We suspect that outside factor not in the scope of our analysis had more weight on the costs of electricity than el Nino.

jupyter notebook: Main.ipnyb

