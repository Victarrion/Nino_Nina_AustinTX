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
   
 ## How El Nino and La Nina affect the recharge of Edwards aquifers?
Considering the data available in data.austintexas.gov and waterdata.usgs.gov to get the datasets of the basin recharge and Water consumption according to the Customer Class​ we analized how El Nino/Nina effect impact the water recharge and Water consumption in Austin Metro. 


  -Study data files
  
aquifer_metadata_path = "datasets/archive/Edwards_Aquifer_annual_recharge_2000_2020.csv"
Residential_Water_data_path = "datasets/archive/Austin_Water_-_Residential_Water_Consumption.csv"

 -Read the water data and the study results in
 
aquifer_metadata = pd.read_csv(aquifer_metadata_path)
Residential_Water_data = pd.read_csv(Residential_Water_data_path)

 -Combine the data 
 
Residential_Water_data['Year'] = Residential_Water_data ['Year Month'].str.split ('/').str [0]
Residential_Water_data['Year'] = Residential_Water_data['Year'].astype(int)
Residential_Water_data['Year'] = pd.to_numeric(Residential_Water_data['Year'])
Residential_Water_data['Total Gallons'] = Residential_Water_data['Total Gallons'].astype(int)

 -Combine the data into a single DataFrame
 
water_complete_complete = (pd.merge(aquifer_metadata, Residential_Water_data, how="inner", on=["Year"]))
water_complete_complete = water_complete_complete.drop(['Year Month'], axis=1)

![image](https://github.com/Victarrion/Nino_Nina_AustinTX/assets/129136787/a3dc14da-3b9d-4981-9ab6-6bedbf205b22)

According to the results, the years with the most outstanding recharges in the aquifer are 2002, 2004, 2007, 2015, and 2016. When we are affected by the El Nino phenomenon or when the Nina phenomenon is weak. ​Also, The year with the highest recharge was 2004 with 2176.1 mm/y, Nino weak. The year with the lowest recharge was 2011 with 107.2 mm/y, Nina moderate. ​

## Water consumption according to the Customer Class

  -Generate a summary statistics  using the local government data table of mean, median, variance, standard deviation, and SEM of the Customer Class for each regimen
  - Use groupby and summary statistical methods to calculate the following : 
   - mean, median, variance, standard deviation, and SEM of the Total Gallons. 

summary_df2 = water_complete_complete.groupby('Customer Class')['Total Gallons'].agg(['mean', 'median', 'var', 'std','sem'])
summary_df2
	
   -Generate a bar plot showing the total number of rows (Year/Total Gallons) for each Customer Class using Pandas.
   
Custumer_class = water_complete_complete.groupby(['Year', 'Customer Class'])['Total Gallons'].sum()

   -Create a bar plot using the  series
   
color_palette = ['red', 'green', 'blue', 'orange']
Custumer_class.plot(kind='bar', figsize=(10,5), stacked=False, color=color_palette)

    -Set the title and axis labels
    
plt.xlabel('Customer Class')
plt.ylabel('Total Gallons')
plt.title('Consumption of Total Gallons per Customer Class')

    -Display the plot
    
plt.show()

![image](https://github.com/Victarrion/Nino_Nina_AustinTX/assets/129136787/b66df799-b2b6-4440-a712-e5ad3487af3b)

According to the data, the customer class with the highest water consumption is the Residencial with an average consumption of 27 million gallons per year, and a median of 20 million. The lowest water consumption is Irrigation-Residential with an average of 93 000 gallons per year. 
 The year with the lowest consumption in Residential, customer class was 2016. In Multi-Family the lowest consumption was in 2020.
 

   
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

