# Project 1 - Prediction of Intraday Stock Price using Linear Regression
### By: [Dishay Mehta]()
### Date: 2022-12-24
### Tags: Ridge Regression, Lasso Regression, OLS Regression, Stock Market, Machine Learning, Python, Pandas, Scikit-Learn, Matplotlib, Jupyter Notebook

## For Project_part1.ipynb,
### So I have done series of analysis on the stock price of Adani Transmission Ltd. (ATL)
I have added the following features:
1. Change in Close Price
2. Change in Volume
3. Close Price after 30 minutes

I have trimmed the data such that I can only use the data from 9:15 to 15:00 and has a holding period of 30 minutes.\
I have used the following models:
1. Linear Regression with explanatory variables as Close Price and Volume and dependent variable as Close Price after 30 minutes
The predicted model is:\
Close_after_30(y) = 1.00 * Price(x1) - 0.00 * Volume(x2) + 9.66 (constant)\
The root mean squared error is 14.122\
We see that its not dependent on the volume and the constant is not zero so we can say that the model is not good.
2. Linear Regression with explanatory variables as Close Price, Volume, Change in Close Price and Change in Volume and dependent variable as Close Price after 30 minutes
The predicted model is:\
Close_after_30(y) = 1.00 * Price(x1) - 0.00 * Volume(x2) - 0.00 * Change_in_Vol(x3) - 0.90 * Change_in_Price(x4) + 8.63 (constant)\
The root mean squared error is 13.424\
We see that its not dependent on the volume and change in volume and the constant is not zero so we can say that the model is not good.
3. OLS Regression with same variables as 2. The summary of the model can be seen in the notebook.
Close_after_30(y) = 0.9962 * Price(x1) - 1.917e-05 * Volume(x2) - 9.887e-05 * Change_in_Vol(x3) - 0.9006 * Change_in_Price(x4) + 8.6304 (constant)\
The root mean squared error is 13.424
4. Ridge Regression with same variables as 2. The summary of the model can be seen in the notebook.
The root mean squared error is 13.422
5. Lasso Regression with same variables as 2. The summary of the model can be seen in the notebook.
The root mean squared error is 13.422

