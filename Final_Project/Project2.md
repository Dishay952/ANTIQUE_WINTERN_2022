# Project 2 - Calculating the Final Investment Value of a stock portfolio using MultiClass Classification
### By: [Dishay Mehta]()
### Date: 2022-12-24
### Tags: Stock Market, Technical Indicators, Machine Learning, Python, Pandas, Scikit-Learn, Matplotlib, Seaborn, Jupyter Notebook

## For Project_part2.ipynb,
### So I have done series of analysis on the stock price of Adani Transmission Ltd. (ATL)
I have added the following features:
1. Change in Close Price
2. Change in Volume
3. Close Price after 5 minutes
3. Close Price after 15 minutes
3. Close Price after 30 minutes

I have trimmed the data such that I can only use the data from 9:15 to 15:00 and has a holding period of 5, 15 and 30 minutes.

I have used the following technical indicators:
1. RSI
2. Bolinger Bands

These will help me predict the intraday price movement of the stock.

I have used the following models and saved the best models in the models folder:\
1. Linear Regression with explanatory variables as Close Price and dependent variable as Close Price after 5 minutes
The predicted model is:\
Close after 5 mins(y) = 0.99 * Close(x1) + 14.14 (constant)\
train loss 35.77579797137519\
test loss 41.14855018323389
2. Artificial Neural Network with explanatory variables as Close and Open Price and dependent variable as Close Price after 5 minutes 
Using adams optimizer and loss function as mean squared error, we get\
train loss 39.162254333496094\
test loss 39.424198150634766
3. Artificial Neural Network with explanatory variables as Close, Open and Volume and dependent variable as Close Price after 5 minutes
Using adams optimizer and loss function as mean squared error, we get\
train loss 48.11674118041992\
test loss 44.80111312866211
4. Artificial Neural Network with explanatory variables as Close and Change in Close Price and dependent variable as Close Price after 5 minutes
Using adams optimizer and loss function as mean squared error, we get\
train loss 0.0001169120441772975\
test loss 0.0007787988870404661
5. Artificial Neural Network with explanatory variables as Close, Open and Change in Close Price and dependent variable as Close Price after 5 minutes
Using adams optimizer and loss function as mean squared error, we get\
train loss 0.001128018251620233\
test loss 0.0015555963618680835
6. Artificial Neural Network with explanatory variables as Close, Change in Close Price, RSI and Bolinger Bands and dependent variable as Close Price after 5 minutes
Using adams optimizer and loss function as mean squared error, we get\
train loss 0.00025204342091456056\
test loss 0.00024410623882431537

The best model is the 4th model with the lowest test loss.\
The plot below also shows that the model is the best with optimum bias and variance.

### Now predicting the 30 mins price movement using the best model.
We make a new model 9 with the same features as 4 but with a holding period of 30 mins.\
We get the following results:\
train loss 172.10414123535156\
test loss 159.07473754882812

### Calculating the predicted returns and actual returns for the 30 mins holding period.
I have used the following formula to calculate the returns:\
Returns = (Close Price after 30 mins - Close Price) / Close Price

### Now comes the multi-class classification part.
The dataframe created from model 9 is then used to create a new columns for predicted label and actual label, where\
1 = Returns > 0.05%\
-1 = Returns < -0.05%\
0 = -0.05% < Returns < 0.05%

### The predicted label is calculated using the predicted returns and the actual label is calculated using the actual returns.
We define the profit returns as **actual returns * predicted returns**\
We then calculate the profit returns for each day and then calculate the cumulative profit returns\
Since the holding period is 30 minutes so we can only make 1 trade in the 30 minutes of trading time. Thus the data is trimmed accordingly\
We then esitmate the number of trades and the final investment value using the following formula:\
Final Investment Value = Initial Investment Value * (1 + Profit Returns)



