#### Prophet Challenge

Forecasting Net Prophet
You’re a growth analyst at MercadoLibre. With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. You've been tasked with analyzing the company's financial and user data in clever ways to make the company grow. So, you want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.

The instructions for this Challenge are divided into four steps, as follows:

Step 1: Find unusual patterns in hourly Google search traffic

Step 2: Mine the search traffic data for seasonality

Step 3: Relate the search traffic to stock price patterns

Step 4: Create a time series model with Prophet

The following subsections detail these steps.
!pip install prophet
# PART 1

### Install the required libraries
### Review the data types of the DataFrame using the info function
### Slice the DataFrame to just the month of May 2020
##
### Plot to visualize the data for May 2020
### Calculate the sum of the total search traffic for May 2020
### View the traffic_may_2020 value
### Calcluate the monhtly median search traffic across all months
### Group the DataFrame by index year and then index month, chain the sum and then the median functions
### View the median_monthly_traffic value
### Compare the seach traffic for the month of May 2020 to the overall monthly median value


# Part2
### Step 2: 
### Mine the Search Traffic Data for Seasonality
### Marketing realizes that they can use the hourly search data, too. If they can track and predict interest in the company and its platform for any time of day, they can focus their marketing efforts around the times that have the most traffic. This will get a greater return on investment (ROI) from their marketing budget.
### To that end, you want to mine the search traffic data for predictable seasonal patterns of interest in the company. To do so, complete the following steps:
### Group the hourly search data to plot the average traffic by the hour of day. Does the search traffic peak at a particular time of day or is it relatively consistent?
### Group the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday). Does the search traffic get busiest on any particular day of the week?
### Group the hourly search data to plot the average traffic by the week of the year. Does the search traffic tend to increase during the winter holiday period (weeks 40 through 52)?
### Group the hourly search data to plot the average traffic by the day of week, using `df.index.hour`
### Group the hourly search data to plot the average traffic by the day of week, using `df.index.isocalendar().day`.
### Group the hourly search data to plot the average traffic by the week of the year using `df.index.isocalendar().week`.


# Part 3
### Step 3: Relate the Search Traffic to Stock Price Patterns
### You mention your work on the search traffic data during a meeting with people in the finance group at the company. They want to know if any relationship between the search data and the company stock price exists, and they ask if you can investigate.
### To do so, complete the following steps:
### Read in and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.
### Market events emerged during the year of 2020 that many companies found difficult. But, after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. Slice the data to just the first half of 2020 (2020-01 to 2020-06 in the DataFrame), and then plot the data. Do both time series indicate a common trend that’s consistent with this narrative?
### Create a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:
### “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility
### “ Hourly Stock Return”, which holds the percent change of the company's stock price on an hourly basis
### Review the time series correlation, and then answer the following question: Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?
#### Visualize the closing price of the df_mercado_stock DataFrame
#### Concatenate the df_mercado_stock DataFrame with the df_mercado_trends DataFrame
#### Concatenate the DataFrame by columns (axis=1), and drop and rows with only one column of data
#### View the first and last five rows of the DataFrame
#### For the combined dataframe, slice to just the first half of 2020 (2020-01 through 2020-06)
#### View the first and last five rows of first_half_2020 DataFrame
#### Visualize the close and Search Trends data
#### Plot each column on a separate axes using the following syntax
#### `plot(subplots=True)`
#### Create a new column in the mercado_stock_trends_df DataFrame called Lagged Search Trends
#### This column should shift the Search Trends information by one hour
#### Create a new column in the mercado_stock_trends_df DataFrame called Stock Volatility
#### This column should calculate the standard deviation of the closing stock price return data over a 4 period rolling window
#### Visualize the stock volatility


# Part 4
### Step 4: Create a Time Series Model with Prophet
### Now, you need to produce a time series model that analyzes and forecasts patterns in the hourly search data. To do so, complete the following steps:
### Set up the Google search data for a Prophet forecasting model.
### After estimating the model, plot the forecast. How's the near-term forecast for the popularity of MercadoLibre?
### Plot the individual time series components of the model to answer the following questions:
### What time of day exhibits the greatest popularity?
### Which day of the week gets the most search traffic?
### What's the lowest point for search traffic in the calendar year?
#### Using the df_mercado_trends DataFrame, reset the index so the date information is no longer the index
#### Label the columns ds and y so that the syntax is recognized by Prophet
#### Drop an NaN values from the prophet_df DataFrame
#### View the first and last five rows of the mercado_prophet_df DataFrame
#### Make the predictions for the trend data using the future_mercado_trends DataFrame
#### Display the first five rows of the forecast_mercado_trends DataFrame
#### Plot the Prophet predictions for the Mercado trends data
#### Set the index in the forecast_mercado_trends DataFrame to the ds datetime column
#### View the only the yhat,yhat_lower and yhat_upper columns from the DataFrame
#### From the forecast_mercado_trends DataFrame, plot the data to visualize
####  the yhat, yhat_lower, and yhat_upper columns over the last 2000 hours
#### Reset the index in the forecast_mercado_trends DataFrame