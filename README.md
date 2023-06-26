# stock-price-prediction

## 🔖 Executive Summary
This project aims at creating a machine learning model that predicts the price of a stock for every 15 minute time intervals. Stock prices of Google, Apple, Meta, Netflix, Amazon, Ebay have been collected from Yahoo finance. Variables high, low, close, open and volume have been collected for every 15 minute intervals from December 14th and March 13th. This complete data has been used for training, hyper-tuning and validation. Finally, the selected model has been tested on the data from March 14th to March 23rd. Based on our analysis we found that different stocks move differently in the market. We also learned that each stock’s close depends on a different set of features. 
Some of the more volatile stocks depend on more lag values as well as volume information whereas the less volatile stocks depend mostly on the previous lag variables. The main observation was that we saw a strong linear correlation between lag values and close price and hence the final model we chose was a lasso linear regression model. Below are the statistics for this model.
<img width="378" align="center" alt="Screenshot 2023-06-25 at 10 36 57 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/c7cb13b5-b9e4-4873-b5e2-af245a794be3">

## 🛠️ Programming language and libraries
- Python
- sklearn
- statsmodel
- tensorflow 

## 📊 Models 
- Linear regression
- Lasso regression
- Random forest
- Neural network to build a stock price prediction model. 

## 🌃 Background
Stock market trading can be an exciting and potentially lucrative endeavour, but it can also be a challenging one for those who are new to it. Our project attempts to make this feat easier for people just starting their trading journey. Traditionally, stock trading analysis is seen as a time series forecasting model, but we are looking at it in a different light. We are using machine learning prediction techniques to identify the important features that need to be considered before trading stocks. 

## 🗺️ Exploratory Data Analysis (EDA):
The EDA was performed on the training dataset to identify anomalies or outliers, understanding the data and determine the relationships between the variables. Every stock’s close price is strongly and linearly related to the previous lag terms of the closing and opening prices as illustrated below:

<img width="700" alt="Screenshot 2023-06-25 at 10 39 54 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/6b2074fa-105d-41e0-af95-69d00a09452d">

The magnitude of difference in the closing price from one interval to another interval is slightly dependent on the volume of the stock which has been traded in the lag intervals. 

<img width="518" alt="Screenshot 2023-06-25 at 10 41 18 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/b80b3b1c-9c57-42bd-810e-eacbeacbe215">

Moreover, there is an existing pattern between the time of the day and the stock movement as well. In the early hours of the day, the volume and magnitude difference is higher than the rest of the day. Also, there is high correlation between the different lag terms.

<img width="642" alt="Screenshot 2023-06-25 at 10 47 24 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/a7e81fc4-5317-404d-a3e0-48fd014f3fd0">

If n-number of lag terms are used there will be multicollinearity hence, principal component analysis has been performed to visualise the data using only 3 lag terms. Principal component 1 was able to capture the trend of the google stock. The first two principal components capture 91% of the closing price variance.

<img width="715" alt="Screenshot 2023-06-25 at 10 48 17 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/1d9d8bc1-2e7d-43e9-9868-5b903642ed9e">

Apart from using only 15-min interval data, we incorporated the day based interval as well. We observed correlation between the previous day closing price and the trading day prices.
Model Development & Results:
<img width="1011" alt="Screenshot 2023-06-25 at 10 48 34 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/503aa879-22d3-4e15-ab97-dfa147bb723a">

Final Model Actual vs Prediction:

<img width="597" alt="Screenshot 2023-06-25 at 10 50 38 PM" src="https://github.com/Aish26/stock-price-prediction/assets/27972590/233c9440-684a-4909-a97b-9cbdbdaf4f17">


## 💰 Recommendations and Business Value
- To buy or not to buy? : Using our statistical models you will be able to predict the price of the stock in the next time window. This will tell you how you should trade in the next time period - if you should buy, sell or do nothing.
- What’s trending : If a stock is trending upwards during the day, it may indicate positive intraday market sentiment and investor confidence in the stock. Conversely, if a stock is trending downwards during the day, it may indicate negative intraday market sentiment and investor uncertainty.
- Uncalculated Risk, No Reward : If a stock has been trending downwards during the day and has established a resistance level, traders can use this level as a stop loss to limit their potential losses if the stock starts to rise. 
- Move to a different beat : Our analysis also proves that different stocks have different patterns and move differently in the market. Hence it is important to understand not one model works for all and each stock needs to be analysed differently.


The current model is unable to capture the extreme volatility in stock closing prices. This volatility could be due to external factors such as friction between countries, a major financial breakdown etc. The model could be fine tuned by feeding such information in the form of sentiments so the extremities could also be predicted up to an extent.

