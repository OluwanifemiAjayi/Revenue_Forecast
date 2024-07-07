# Gadgets Store Revenue Forecast Using Microsoft Excel

## Project Outline
1. Introduction

2. Data Preparation and Cleaning

3. Data Exploration

4. Modeling

5. Model Validation

6. Scenario Analysis
   
7. Dashboard Creation
  
8. Conclusion

## 1. Introduction
This Project involved working with the financial data of a gadgets store for year 2023 to show how well the business would perform in the year 2024 by forecasting the monthly revenue. By building a forecast model with the aid of Microsoft Excel, I was able to predict the monthly revenue for the year 2024, making use of the metrics of the past year, and also provide a comprehensive visualization to support decision-making. All steps taken and formulas used can be observed in this [Excel Workbook](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/gadgets_store_data_2023.xlsx)

## 2. Data Preparation and Cleaning 
I imported the dataset consisting of 4 columns; Date, Product, Units_sold and Price_per_unit and 3536 rows of data into Excel spreadsheet then I made a duplicate of the workbook and loaded this duplicate into power query to clean and transform my data before any analysis or model building. I checked the profile, distribution and quality for all columns and as shown below, 

![Column quality and profile](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/Column%20profile%20and%20quality.png)

I observed few blank rows in the Units_sold and Price_per_unit columns, I took care of these missing rows by replacing the null values with the mean value of 22 for the Units_sold column and I also did the same for the Price_per_unit column with the mean value $509.48. Then I applied these changes and loaded the data to Microsoft Excel where I formatted my data correctly; to Datetime for the Date column, to text for the Product column, to number for Units_sold and to currency for the Price column.

I then went ahead to check for outliers using the interquartile-range method and I created two is_outlier columns, for Units_sold and Price columns since they were the numerical columns, using an IF() function to show 'Yes' if the value was an outlier and 'No' otherwise. 48 rows of only the Units_sold column were outliers so I replaced them with the column's Average value of 22.
Next, I created the columns Month and Revenue respectively to show the month of each date in text form and the revenue generated for each record by multiplying Units_sold and Price .

## 3. Data Exploration
Using descriptive statistics, I was able to obtain the mean, median, mode,range, variance, standard error, maximum, and minimum values of the dataset. After which I created Pivot tables to summarize and aggregate my dataset according to each Month and Product; showing the quantity of Units_sold, average Price and Total Revenue for both categories

![Pivot Tables](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/Pivot%20tables.png)

## 4. Modeling 
I proceeded to the main purpose of this project, that is to create the model needed for Revenue forecasting, but before doing so, I calculated the 3-months Moving Averages for the actual Revenue. Using the FORECAST.ETS() function, specifying the seasonality as 12 months, I was able to forecast the revenue for the 12 months of 2024 based on the historical data. Then I calculated the Moving Averages for the 2024 forecasted Revenue.

![Forecast Results](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/forecast.png)

## 5. Model Validation
To evaluate the performance of my model, I used the Error Metrics method to validate my model, by comparing the forecasted Revenue with the actual Revenue, I was able to derive the Mean Absolute Error, Mean Squared Error, Root Mean Squared Error and Mean Absolute Percentage Error

![Model Validation with Error Metrics](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/Model%20Validation.png)

Given the values for the Error Metrics displayed above, the Mean Absolute Percentage Error was below 10% and this showed that the model was performing well, then the Mean Absolute Error (MAE) and the Root Mean Squared Error (RMSE) were relatively compared to the scale of the data. Given that the revenues were in millions, an MAE of $149,518.44 and an RMSE of $181,154.72 was seen as acceptable due to the tolerance for forecasting errors.

## 6. Scenario Analysis
After validation of the forecast model, I decided to do an analysis of different scenarios I created to see potential future outcomes of the forecasted Revenue under different conditions. This approach is more relevant for planning and preparing for potential future events, helping companies make informed decisions.
 I created three scenarios;
- **Best Case:** Assuming a 10% increase in forecasted Revenue.
- **Worst Case:** Here, I assumed a 10% decrease in forecasted Revenue.
- **Normal Case:** I used the forecasted Revenue as it was.

![Scenario Analysis for Forecast data](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/Scenario%20Analysis.png)

## 7. Dashboard Creation 
Lastly, I created a dashboard for the financial data with the following components; Title and Summary Cards, charts showing monthly revenue, comparing revenue by product, comparing forecasted, best, and worst-case scenarios. Also, Line charts showing Time Series of actual and forecasted revenue and sales and price trends over the year. 

![Revenue Dashboard](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/Revenue%20Forecasting%20Dashboard.jpg)

## 8. Conclusion
The revenue forecasting project successfully utilized historical data to predict future revenues and visualized the results in an interactive dashboard providing valuable insights which will help in decision-making. 

- **Performance of Forecasting Model:**
The error metrics seem to show that the model is very accurate. These high values of MSE and RMSE, against the low MAPE of 4.92%, indicate the variability in the data while showing that the forecasted values are very close to these real values.

- **Scenario Analysis:**
As total Revenue rise to $39,246,849.88 in the Best Case and fall to $32,111,058.99 in the Worst Case. This chart only goes to prove the effect that external factors may have on revenues and makes scenario planning in the development of forecasting highly necessary.

- **Actual Revenue vs. Forecasted Revenue**:
Actual revenue is huge, worth $36,100,183, with the forecasted revenue a little short at $35,678,950.

- **Average Price**:
The average price per transaction is $509.48 showing a good pricing strategy is in use.

- **Monthly Revenue Trends**:
Monthly revenue is inexactly steady and experiences fluctuations for the Actual Revenue while the Forecasted Revenue is quite steady but falls from $3,001,237 to #2,945,090

- **Product Revenue Insights**:
Certain products contribute significantly to revenue growth.

- **Sales, quantity of Units_sold and Price Trend**:
Increasing trend for actual revenue and profit while Units_sold and Price are quite stable over the months.

## Recommendations:
The model should be updated frequently with new data to increase its accuracy.
Exogenous factors that might have an impact on revenues should be considered and built  into the model.
Seasonal trends should be monitored.
Resources should be allocated strategically to high-performing products.

## Relevant Links
- [Revenue Forecasting Dashboard](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/Revenue%20Forecasting%20Dashboard.jpg)
- [Excel Workbook](https://github.com/OluwanifemiAjayi/Revenue_Forecasting/blob/main/gadgets_store_data_2023.xlsx)
- [Gadgets Store Dataset](https://github.com/OluwanifemiAjayi/Revenue_Forecast/blob/main/gadgets_store_dataset.xlsx)
- [LinkedIn](https://www.linkedin.com/in/oluwanifemiii)
