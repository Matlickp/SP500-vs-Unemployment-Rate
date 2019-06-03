# SP500-vs-Unemployment-Rate

Market Data vs Unemployment Rate:

For this project we wanted to look at two relationships that relate to market data and the unemployment  
rate in the United States over time. The first is the correlation between the S&P500 (SPY) and the
Volatility Index(^VIX). The second is the relationship between the overall movement of the market, using SPY and ^VIX,
compared to the overall unemployment rate. For this analysis we used the past 19 years from 1/1/2000 to 
12/31/2018 in order to take advantage of 2 large market downturns and their recoveries. Being able to see how the 
Volatility Index affects the S&P500 and how that in turn affects the unemloyment rate, could help predict any future spikes
in unemployment and allow government and private organizations to be proactive in preparing for the needs that will come.

## Data Gathering and Cleaning:

Using Pandas DataReader, historical data for the SPY and ^VIX is gathered.
This data can then be used to calculate a 100 day moving average for both indices.
Then only relevant columns are kept and renamed.
The tables are then joined and saved into a Mongo Database.

The Bureau of Labor Statistics then provides a csv for historical unemployment rate.
This data is also saved into the Mongo Database

![Market and Employment Data](Images/database tables.png?raw=true "Data"

## Visualizing the Data

The first thing to check is the inverse relationship between the SPY and the ^VIX which we can see here. As the SPY goes up the ^VIX goes down and vice versa.

![SPY and VIX](Images/SPYvsVIX.png?raw=true "Market Comparison"

Next, after mulitplying the unemployment rate by 10 to better visualize, the rate is plotted and the relationship can be analyzed. 

![Market and Unemployment](Images/Unemployment vs Market.png?raw=true "Market vs Unemployment")

As you can see, the better the SPY is doing, being used as a proxy for the overall market, the lower the unmployment rate. However, the market can recover a lot quicker than unemployment can.

Files in Repository:

1. Data Folder
	- spy.csv
	- vix.csv
	- unemploment rate.csv
	
2. Images Folder
	- SPY-vs_VIX.png
	- Unemployment_vs_Market.png
	
3. SPY vs VIX.ipynb 

4. ETL_Presenation.pptx
		
		




		
	
	 


