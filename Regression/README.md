# Linear Regression for NIFTY Stock Prediction
### By: [Dishay Mehta]()
### Date: 2022-12-12
### Tags: Regression, Stock Market, Machine Learning, Python, Pandas, Scikit-Learn, Matplotlib, Seaborn, Jupyter Notebook

## For Regression_5D_returns.ipynb,
### I have calculated the 2,3,4 and 5 day returns of the NIFTY stock price and then used the returns to predict the stock price.
I have used the following models to predict the stock price:
1. Linear Regression with explanatory variables as 4 day returns and dependent variable as 5 day returns\
The predicted linear regression model is:\
Returns_5D(y) = 1.00 * Returns_4D(x1) + 0.04 (constant)\
The root mean squared error of the model is 0.7123 \
2. Linear Regression with explanatory variables as 3 day returns and 4 day returns and dependent variable as 5 day returns
The predicted linear regression model is:\
Returns_5D(y) = -0.09 * Returns_3D(x1) + 1.07 * Returns_4D(x2)) + 0.04 (constant)\
The root mean square error of the model is 0.7126 \
3. Linear Regression with explanatory variables as 3 day returns and 4 day returns and an interactive term for non-linearity and dependent variable as 5 day returns
The predicted linear regression model is:
Returns_5D(y) = -0.09 * Returns_3D(x1) + 1.07 * Returns_4D(x2)) + -0.02 * Interactive_term(x1*x2)) + 0.09 (constant)
The root mean square error of the model is 0.7123
After this is done,
I have check the seasonality of the stock price and then decomposed the stock price into trend, seasonality and residuals. STL decomposition is found to be the best method for decomposing the stock price.
I have also plotted the autocorrelation and partial autocorrelation plots for the residuals to check for the presence of autocorrelation in the residuals.

## For Regression_Open_Close.ipynb,
### I have used 3 days MA and 9 days MA of the Open and Close price of NIFTY to predict the next Open and Close price respectively.
Linear Regression model for Close price
NIFTY Close Price (y) = 1.18 * 3 Days Moving Average (x1) + -0.18 * 9 Days Moving Average (x2) + 3.94 (constant)
Linear Regression model for Open price
NIFTY Open Price (y) = 1.19 * 3 Days Moving Average (x1) + -0.19 * 9 Days Moving Average (x2) + 3.73 (constant)