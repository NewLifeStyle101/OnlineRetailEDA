# OnlineRetailEDA
## Project Overview
Exploratory Data Analysis of a publicly available dataset containing sales information for a UK based retailer. The goal of the analysis is to explore the weekly revenue behaviour and assess suitability for time series modeling and forecasting.
## Dataset
Name: Online Retail Dataset
Source: UCI Machine Learning Repository
Time Period: December 2010 until December 2011
Link: https://archive.ics.uci.edu/dataset/352/online+retail
Description: The dataset consists of 6 features 
- InvoiceNo which is a 6 digit number assigned to each transaction if it starts with a c it represents a cancellation
- StockCode a 5 digit number unique to each distinct product
- Description which is the product name
- Quantity represents the quantity sold per invoice
- InvoiceDate is the day and time when each transaction has been generated
- UnitPrice is the price of the product per unit
- CustomerID is a 5 number unique identifier assigned to each customer
- Country is the name of the country the customer resides
## Target Variable 
The analysis focuses on weekly revenue which is the sum of the quantity of each product sold in a week multiplied by its unit price.

The data is originally given in a daily format however, there is too much noise so to visualise the trend and to preserve seasonality weekly aggregation has been chosen.

Invoices that were cancellations, broken items or debt adjustment have been omitted from the analysis as they reflect post sale adjustments rather than new demand.
## Methodology
- Weekly aggregation for visualisation of the trend and seasonality
- Rolling statistics to gain a deeper insight of the movement of the data
- Log-Transformation for variance stabilisation
- First Order Differencing to remove trend effects from the series
- Autocorrelation
- Partial Autocorrelation

## Key Findings
## Stationarity Conclusion
## Limitations
Only a single aggregation has been done on the series without exploration of monthly movements.
Since the goal of the project is analysis no forecasting or model evaluation has been done.
## Next Steps
This project has been meant to build on statistical foundations of time series analysis to eventually lead to ARIMA modeling. 
## Tools Used
- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
