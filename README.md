# Electric Load Forecasting

## Problem Statement
<p>
    Electrical energy is central to our quality of life and a lot of our daily tasks virtually depend on it.
Energy providers are under constant pressure to provide high quality services, without delay or failure, 24/7 and all for an affordable price.<br>
So, how does an energy provider determine supply based on demand?
How do they handle the challenge of everyone suddenly working from home using up more electric energy than was originally predicted?<br>
How do they meet the demand caused during extreme weather conditions without running out of supply or catastrophic failure?<br>
Keeping in mind all the fixed price contracts that need to be honored with customers, energy management today has a crucial need for innovative, dynamic, smart and artificially intelligent load management to keep things running smoothly.</p>
<p>
    Load forecasting is a technique used by energy providers to predict the energy needed to meet the demand and supply equilibrium. It is important because it is used to develop effective long and short term strategies, control energy usage, develop building electrical guidelines, fault detection, and developing reliable budget forecasts when dealing with a growing population and the global climate change crisis.</p>
<p>
    We will use machine learning regression models to perform load forecasting of each commercial building type and determine the electrical patterns for each building type. This can assist in identifying irregular electrical patterns and create building type energy profiles. This information can be usefule in determining grid areas that may need maintenance or inspection, and can provide building type energy usage guidelines.</p>

## Data Acquisition
We obtained this dataset from the <a target="blank" href="https://data.openei.org/about">Open Energy Data Initiative (OEDI) Data Lake</a> which is a centralized repository of datasets aggregated from the U.S. Department of Energy’s programs, offices and national labs.<br>
Our dataset is focused on commercial building energy data for Atlanta, GA and Chicago, IL which are two of the largest commercial energy data locations from the OEDI data lake datasets. The dataset contains 16 different commercial building types.<br>

## Data Dictionary
We combined 32 different datasets, 1 for each building type in each city to yield a combined structured dataset with a total of 280,320 records.<br>
We will combine the total electricity and gas usage columns to define our target, and use the building type, location and date/time columns as our features.<br>
<p>Here is a snapshot of our data dictionary:</p>

|                        Original Column Name 	| New Column Name                         	| Data Type   	| Description                                       	|
|--------------------------------------------:	|-----------------------------------------	|-------------	|---------------------------------------------------	|
| Date/Time                                   	| date_time                               	| Datetime    	| Date/time electricity and gas usage, was recorded 	|
| Electricity:Facility \[kW](Hourly)          	| electricity_facility_kw_hourly          	| Float       	| Total electricity usage in kilowatt-hours         	|
| Fans:Electricity \[kW](Hourly)              	| fans_electricity_kw_hourly              	| Float       	| Fan electricity usage                             	|
| Cooling:Electricity \[kW](Hourly)           	| cooling_electricity_kw_hourly           	| Float       	| Cooling electricity usage                         	|
| Heating:Electricity \[kW](Hourly)           	| heating_electricity_kw_hourly           	| Float       	| Heating electricity usage                         	|
| InteriorLights:Electricity \[kW](Hourly)    	| interiorlights_electricity_kw_hourly    	| Float       	| Interior lights electricity usage                 	|
| InteriorEquipment:Electricity \[kW](Hourly) 	| interiorequipment_electricity_kw_hourly 	| Float       	| Interior equipment electricity usage              	|
| Gas:Facility \[kW](Hourly)                  	| gas_facility_kw_hourly                  	| Float       	| Total gas usage in kilowatt-hours                 	|
| Heating:Gas \[kW](Hourly)                   	| heating_gas_kw_hourly                   	| Float       	| Heating gas usage                                 	|
| InteriorEquipment:Gas \[kW](Hourly)         	| interiorequipment_gas_kw_hourly         	| Float       	| Interior equipment gas usage                      	|
| Water Heater:WaterSystems:Gas \[kW](Hourly) 	| water_heater_watersystems_gas_kw_hourly 	| Float       	| Water heater gas usage                            	|
| building_type                               	| building_type                           	| Categorical 	| Building type                                     	|
| location                                    	| location                                	| Categorical 	| Location (City, state)                            	|
| Electricity:Facility \[kW](Monthly)         	| electricity_facility_kw_monthly         	| Float       	| Total monthly electricity usage (kilowatt-hours)  	|
| Gas:Facility \[kW](Monthly)                 	| gas_facility_kw_monthly                 	| Float       	| Total monthly gas usage (kilowatt-hours)          	|
