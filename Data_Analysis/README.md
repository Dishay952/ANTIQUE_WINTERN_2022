# Data Analysis of NIFTY and Adani Transmission Ltd. (ATL) stock
### By: [Dishay Mehta]()
### Date: 2022-12-19
### Tags: Stock Market, Technical Indicators, Machine Learning, Python, Pandas, Scikit-Learn, Matplotlib, Seaborn, Jupyter Notebook

## For NIFTY_EDA.ipynb,
### So I have done series of analysis on the stock price of NIFTY 50
I have calculated the rolling 5 day returns.
Seeing the distributions of the Volume, 1 day returns and 5 day returns, we can say that the data is not normally distributed.
### Time to test the normality of the data
I have used the following test to test the normality of the data:
1. QQ Plot 
The plot is far deviated from the straight line for both the 1 day returns and 5 day returns. So we can say that the data is not normally distributed but we still have to test it using the Kolmogorov-Smirnov test and Shapiro-Wilk test.
2. Kolmogorov-Smirnov Test
The p-value comes out to be less than 0.05 so we can reject the null hypothesis and say that the data is not normally distributed but we still have to test it using the Shapiro-Wilk test.
3. Shapiro-Wilk Test
The p-value comes out to be less than 0.05 so we can reject the null hypothesis and say that the data is not normally distributed.

Thus normality assumption is violated.

### Time to test if the distribtion is lognormal
I have scaled the returns to make sure that its positive, taken the log of data and then I have used the following test to test if the distribtion is lognormal:
1. QQ Plot
The plot is far deviated from the straight line for both the 1 day returns and 5 day returns. So we can say that the data is not lognormally distributed but we still have to test it using the Kolmogorov-Smirnov test and Shapiro-Wilk test.
2. Kolmogorov-Smirnov Test
The p-value comes out to be less than 0.05 so we can reject the null hypothesis and say that the data is not lognormally distributed but we still have to test it using the Shapiro-Wilk test.
3. Shapiro-Wilk Test
The p-value comes out to be less than 0.05 so we can reject the null hypothesis and say that the data is not lognormally distributed.

Thus lognormality assumption is violated.

### Lastly, comparing the mean for 2 years period to check if the property of variables have changed over years

## For TA.ipynb,
### So I have done series of analysis on the stock price of Adani Transmission Ltd. (ATL)
I have used the following technical indicators:
1. RSI
2. Bollinger Bands

### Strategy - a simple voting mechanism
> When two indicators think it is time to buy, then it issues buy order to enter.
> When both indicators think it is time to sell, then it issues sell order to exit.

Thus have plotted the buy and sell signals on the stock price.




