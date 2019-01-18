# market-to-unemployment
Market Data vs Unemployment Rate:

For this project we wanted to look at two relationships that relate to market data and the unemployment  
rate in the United States over time. The first is the correlation between the S&P500 (SPY) and the
Volatility Index(^VIX). The second is the relationship between the overall movement of the market, using SPY and ^VIX,
compared to the overall unemployment rate. For this analysis we used the past 19 years from 1/1/2000 to 
12/31/2018 in order to take advantage of 2 large market downturns and their recoveries. Being able to see how the 
Volatility Index affects the S&P500 and how that in turn affects the unemloyment rate, could help predict any future spikes
in unemployment and allow government and private organizations to be proactive in preparing for the needs that will come.

Process:

1. Collect S&P500 Data
	-Using pandas datareader 
	-Ticker (SPY)
	-Source: Yahoo
	- Dates
		- Start 2000/1/1
		- End 2018/12/31
		
	- Save S&P500 to CSV
	- Remove Open, High, Low, Close columns
	- Add column (100MA) 
		- This column is a rolling window that calculates the moving average (MA) over 100 days
		- You have to set the minimum to 0 in order to get an average of the days before you reach 100

2. Collect Volatility Index Data
	-Using pandas datareader 
	-Ticker (^VIX)
	-Source: Yahoo
	- Dates
		- Start 2000/1/1
		- End 2018/12/31
		
	- Save ^VIX to CSV
	- Remove Open, High, Low, Close columns
	- Add column (100MA) 
		- This column is a rolling window that calculates the moving average (MA) over 100 days
		- You have to set the minimum to 0 in order to get an average of the days before you reach 100

3. Join the SPY and VIX 
	- How = outer
	- On = Date

4. Download Unemployment Rate from Bureau of Labor Statistics
	- Save as CSV
	- Reformat CSV to have date column in yyyy/mm/dd format
	- Read CSV with pandas

5. Save Data to MongoDB
	- Execute "mongod" in gitbash
	- Connect to client in ipynb
	- Create DB for market data
		- Create Collection for the SPY/VIX dataframe
		- Insert
	- Create DB for Unemployment
		- Create Collection for Unemployment dataframe
		- Insert
		
6. Pull Data fromn MongoDB
	- Use .find for each of the databases that were created
	- Create Loop through .find results
	- Append Market Data list with loop
	- Append Unemployment Rate with loop
	- Convert lists to dataframes

7. Set "Date" as index for both dataframes
	- pd.to_datetime to keep them consistent

8. SPY vs Vix Plot
	- Create Subplot1 and Subplot2
	- Subplot1
		- plt.Line 
		- Plot the ADJ Close of the SPY
		- Plot the Moving Average of SPY
		- Plot the ADJ Close of the VIX
		- Plot the Moving Average of VIX
	- Subplot2
		- plt.bar
		- Plot the Volume of the SPY

9. Market vs Unemployment
	- Add to Subplot1 from first chart
		- plt.line
		- Plot Unemployment Rate
		
		




		
	
	 
Files in the Repository:

1) Data Folder:
(a) Web-Scraping Folder: CSV files from web-scraping
    * spy.csv
    * vix.csv
(b) unemployment rate.csv: Downloaded from BLS.gov

2) Images Folder:
(a) SPY_vs_VIX.png
(b) Unemployment_vs_SPY_VIX.png

3) SPY vs VIX.ipynb: Jupiter notebook with the code

4) ETL_Presentation.ppt: Presentation

