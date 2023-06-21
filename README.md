# Nino Nina AustinTX
Project-1 Of the UT Austin Data Analysis bootcamp. In this project we focus on analysing the effect that el Nino and La Nina have across the Austin metro area (Travis and Williamson county) and how it affects:
1. Temperature
2. Rainfall

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

  -Generate a summary statistics  using the local government data table of mean, median, variance, standard deviation, and SEM of the tumor volume for each regimen
  - Use groupby and summary statistical methods to calculate the following : 
   - mean, median, variance, standard deviation, and SEM of the tumor volume. 

summary_df2 = water_complete_complete.groupby('Customer Class')['Total Gallons'].agg(['mean', 'median', 'var', 'std','sem'])
summary_df2
	
Customer Class					     mean	    median	         var	         std	      sem
Irrigation - Multi-Family	1.853053e+06	997750.0	    5.264581e+12	2.294467e+06	36415.531466
Irrigation - Residential	9.377354e+04	22950.0	    5.869516e+10	2.422708e+05	3960.493009
Multi-Family	            1.694487e+07	13057200.0	 2.870086e+14	1.694133e+07	255168.252711
Residential	               2.735767e+07	20781150.0	 5.720986e+14	2.391858e+07	348888.380039

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
 
5. Water levels in Lake Travis
6. Electrical cost in kWh

Results:
