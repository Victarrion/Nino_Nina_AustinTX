# Nino Nina AustinTX
Project-1 Of the UT Austin Data Analysis bootcamp. In this project we focus on analysing the effect that el Nino and La Nina have across the Austin metro area (Travis and Williamson county) and how it affects:
1. Temperature
2. Rainfall

   ## How El Nino and La Nina affect the recharge of Edwards aquifers?
Considering the data available in data.austintexas.gov and waterdata.usgs.gov to get the datasets of the basin recharge and Water consumption according to the Customer Class​ we analized how El Nino/Nina effect impact the water recharge and Water consumption in Austin Metro. 
  -Study data files
aquifer_metadata_path = "datasets/archive/Edwards_Aquifer_annual_recharge_2000_2020.csv"
Residential_Water_data_path = "datasets/archive/Austin_Water_-_Residential_Water_Consumption.csv"
 -Read the water data and the study results
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

4. Water Recharge Rate of the Edwards aquifer

5. Water levels in Lake Travis
6. Electrical cost in kWh

Results:
