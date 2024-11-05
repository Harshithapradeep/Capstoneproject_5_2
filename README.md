|Project Title|Dominos - Predictive Purchase Order System
| :--- | :--- |
|**Skills take away From This Project**| ●	Data cleaning and preprocessing ●	Exploratory data analysis (EDA) ●	Time series forecasting ●	Predictive modeling ●	Business decision making ●	Real-world application of data science
|**Domain**|Food Service Industry|

<ins>***Project Description:***</ins>

This project aims to enhance the efficiency of future sales prediction and optimizing the purchase order of ingredients to minimize waste and stockouts based on given historical pizza sales
and ingredients dataset to forecast sales by developing a prediction model to generate ingredients purchase order for the week to achieve the following 
- Inventory Management: Ensuring optimal stock levels without overstocking.
- Cost Reduction: Minimizing waste and reducing costs associated with expired or excess inventory.
- Sales Forecasting: Predicting Seasonal sales trends to inform business strategies and promotions.
- Supply Chain Optimization: Streamlining the ordering process of ingredients for the predicted sales for the coming week.
  
<ins>***Data Preprocessing steps:***</ins>
- Understand the sales dataset to handle missing values based on the correlation between columns of the dataset 
- Data cleaning –Filling the total price based on unit price and quantity, pizza categories based on pizza name id, missing pizza ingredients based on pizza name, pizza name id based on pizza name.
- Analyze the ingredients dataset and filling the missing items quantity values using the Mean imputation.
- Create a master dataframe by merging both pizza sales and ingredients dataset for further cleaning.
- Drop the common columns and duplicate rows.

<ins>***Feature selection and engineering steps:***</ins>
- Formatting the desired date formats and extract day of the week, week, month and year from order date from the given dataset.
- Adding holiday indicator to check order dates was a holiday or not and weekend flag to analyze seasonal sale trends based on normal weekdays and weekend and month wise, week wise sales.

<ins>***Exploratory data analysis:***</ins>
- Data visualization of total sales ,top selling pizza category wise and size wise through bar plots and correlation heatmaps of sales data
- Sales during weekends and holidays 

 ![image](https://github.com/user-attachments/assets/02c8bc0a-25b4-430e-bc20-b8c4ed3682b1)

 ![image](https://github.com/user-attachments/assets/2b0a3d57-cf0a-46e7-a781-245090d15fb4)

 ![image](https://github.com/user-attachments/assets/03e9d9ba-690e-43d0-9269-aeb25b0fe1e2)

 ![image](https://github.com/user-attachments/assets/50e9f56a-2585-400c-99be-987f7fcbc16a)

 ![image](https://github.com/user-attachments/assets/99ab5195-963b-4913-ad07-7363acab9563)

 ![image](https://github.com/user-attachments/assets/bf160e8d-f1c0-4377-9ab1-0fa68d2142f8)

 ![image](https://github.com/user-attachments/assets/daea1698-17b1-4be3-9955-6fc1b275f450)

 ![image](https://github.com/user-attachments/assets/bd573c0d-1ab5-42fd-b914-7efe05ba9833)

<ins>***Model Selection and training:***</ins>
- Splitting the merged dataset to 80:20 test and train data ratio.
- ARIMA Model and SARIMA model for seasonal sales trend analysis 
1) p(Autoregressive-term):The number of past observations(lags) used to predict future values.
2) d(Differencing term):The number of times the data is differenced to make it stationary.
3) q(moving Average term): The number of past forecast errors used to improve future predictions.
- Model evaluation metric used -Mean absolute percentage error of actual and predicted sales by week.

 ![image](https://github.com/user-attachments/assets/bfcc9833-55b2-47e8-a83d-1e21107f327a)

- SARIMA Model(Seasonal ARIMA)
1)	P (Seasonal Auto Regressive term): The number of past seasonal values used for prediction.
2)	D (Seasonal Differencing term): The number of seasonal differencing applied to make data stationary.
3)	Q (Seasonal Moving Average term): The number of past seasonal forecast errors used for prediction.
4)	S (Seasonal Period): The length of the seasonal cycle (e.g., 12 for yearly seasonality in monthly data).

![image](https://github.com/user-attachments/assets/c104ff63-777f-45a0-8d8e-62f7d7aa3035)

- Prophet (Developed by Facebook)
Prophet is a popular model for handling time series data with seasonal and holiday effects.The Facebook Prophet model is a tool developed by Facebook for forecasting time series data.
It’s especially useful when you want to predict future values based on historical data, such as sales, temperatures, or website traffic.
1) Growth: Defines the trend type (linear or logistic).
2) Changepoints: Points where the trend changes.
3) Seasonality: Models seasonal patterns (weekly, yearly, etc.).
4) Holidays: Incorporates custom holidays or events affecting the forecast.
5) Seasonality Mode: Can be additive or multiplicative.

![image](https://github.com/user-attachments/assets/2dd9a9cc-9ae4-482c-bedc-d9c4ea8bd7c3)

- Regression Model
  
![image](https://github.com/user-attachments/assets/ec4ffaab-b1fc-4207-8c00-6ead2d3d4a02)

- Long short-term memory (LSTM) model with tensor flow
LSTMs address the vanishing gradient problem of traditional RNNs, making them better suited for tasks that require learning long-term dependencies.

![image](https://github.com/user-attachments/assets/957d676e-5230-4414-b303-1130a54e9bf2)

- Model evaluation based on MAPE values for all the models and saving the model in pickle file
  
<ins>***Purchase Order creation and sales forecasting for one week:***</ins>
- Ingredient calculation : Total quantity in KG calculated for each pizza ingredients for the week 04-01-2016 to 10-01-2016.
- Saving the purchase order data in a csv file.
- Predicted weekly sales using the trained SARIMA model to be 3372 units pizza sold.

  ![image](https://github.com/user-attachments/assets/dd3cc24b-ff4d-47fe-8bd8-e2518dffa087)





















 
