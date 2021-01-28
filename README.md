# Time-Series-Analysis
## Objective: In this repository, we will create a trading strategy by using the ARIMA model on a Bank of America price time series and perform a backtest on the strategy. 

# Background
  A time series is a sequence of numerical data points in successive order. Time series data has a peculiar characteristic which is the persistence in successive observations. This means that previous values have some influence on the present values. We can use that characteristic to perform price forecasting which is necessary for developing our trading strategy. To perform the price forecasting on a time series, we can use a combination of autoregressive and moving average models. Autoregressive models are process where the current value is a linear combination of past/lagged observations.
AR(p) models attempt to explain the mean reversion and trending behaviours that we observe in asset prices. Moving Average models are process where the current value is a linear combination of past error terms. MA(q) models try to capture the idiosyncratic shocks that are observed in financial markets. A white noise process models these shocks quite well. We can think of events like terrorist attacks, earnings surprises, sudden political changes, etc. as the random shocks affecting the asset price movements. However, the ARMA model described above will only work or have good explanatory and predictive power only if the time series is stationary. Meaning that time series' statistical properties (mean, variance, covariance) are constant throughout time. We can perform an augmented fuller dicker test to check if the time series is stationary or not. In the case the time series is not stationary, we can convert it into stationary by differencing the time series. This is where ARIMA models come handy. ARIMA models perform an order of i in differencing the time series and then perform the ARMA model. Once we have a good model, we can forecast the price in the time series and generate trading signal. The strategy is simple.
If our current predicte price increased then we go long otherwise we go short. 

# Financial Data
We gathered stock data for Bank of America from Jan. 1 , 2010 to Dec. 31, 2020. We fetch the data from yahoo finance by using the yfinance module. The ticker used was BAC which is Bank of America. We also performed a sanity check on the data to see if there was no missing value on the data which is an important feature in time series analysis. Also, there is a csv file with the same data in the reporsitory.   

# Analysis Results
We first tested the model performance by calculating the error metrics and residual analysis. Once we had a good model performance, we developed the trading strategy. For the backtest analysis, we only calculated the Sharpe Ratio, Cumulative return and Drawdowns of the strategy. However, we did a quick backtest 
on the strategy returns by using the pyfolio module.   


