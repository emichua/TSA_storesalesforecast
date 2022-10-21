# Store Sales - Time Series Forecasting

### Contents:
* [01_EDA](#01_EDA)
- [Background story](#Background-story)
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Import Libraries & Data](#Import-libraries-&-Data)
- [Extract Transform & Load](#Extract-Transform-&-Load)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Export data](#Export-data)
* [02_Preprocessing_Model](#02_Preprocessing_Model)
- [Import libraries & Data](#Import-libraries-&-Data)
- [Hyperparameter Tuning](#Hyperparameter-Tuning)
- [Model Fitting](#Model-Fitting)
- [Conclusion&Recommendation](#Conclusion-&-Recommendation)

### Background story
Businesses forecast product demand is a common task of professional data scientists. Forecasts are especially relevant to brick-and-mortar grocery stores, which must dance delicately with how much inventory to buy. Predict a little over, and grocers are stuck with overstocked, perishable goods. Guess a little under, and popular items quickly sell out, leading to lost revenue and upset customers. More accurate forecasting, thanks to machine learning, could help ensure retailers please customers by having just enough of the right products at the right time.

For grocery stores, more accurate forecasting can decrease food waste related to overstocking and improve customer satisfaction. The results of this ongoing competition, over time, might even ensure your local store has exactly what you need the next time you shop.

### Problem Statement

- To build a time-series model that can accurately predicts the unit sales for items with highest sales and sold at one of the stores with highest sales.

### Executive Summary

I started by loading necessary libraries and data. Under extract,transform and load, I find out about the basic info for my train data. From train data, I found out about highest sales for the family & store. Store 44 & Grocery I has the highest sales. So I started by doing time series forecasting on this two features. I found out that there is no strong correlation between oil price & promotion and sales. Thus, I decided to drop the feature and proceed with simple time series model. Under hyperparameter tuning, I did parameter differencing for my data to achieve stationary. I also did Augmented Dicky-Fuller Test to find out the T-statistic and p-value. The original data (without differencing ) is good enough to show stationary as the p value is less that 0.05. We proceed with Manual GridSearch to look for the p,q for ARIMA model. ARIMA (4,0,4) is found. The model is fit and the result can be better.I proceed with PACF and ACF to find out the seasonal,Q feature. Another round of Manual GridSearch was done and SARIMA (4,0,4),(0,0,0,7) is fit. The model is not performing as well as ARIMA. In conclusion, the model can be fine tune, by doing SARIMAX or auto-arima in future.  

### Conclusion & Recommendation

#### Recommendation

**1. Using qty instead of $**
- Instead of sales figure, sales qty can be included as promotional item can be in bundle/or cheaper price

**2. Salesforce effectiveness**
- Besides having promotion, promoter in supermarket will also increase sales for certain items by having food tasting, freebies

**3. Include population/household income** 
- In order to forecast more accurately, population & household income can be one of the few factors

#### Conclusion
The time series models I have used ie ARIMA and SARIMA can help to predict the store sales. However, more related feature should be included for higher accuracy.

### Datasets
* Train (https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data)
* Oil (https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data)

