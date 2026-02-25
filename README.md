# OnlineRetailEDA
## Project Overview
Exploratory Data Analysis of a publicly available dataset containing sales information for a UK based retailer. The goal of the analysis is to explore the weekly revenue behaviour and assess suitability for time series modeling. The focus is on understanding the trend, variability and dependence over time; no forecasting or model fitting is performed in this project.
## Dataset
- Name: Online Retail Dataset
- Source: UCI Machine Learning Repository
- Time Period: December 2010 until December 2011
- Link: https://archive.ics.uci.edu/dataset/352/online+retail
### Description:
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
- The raw series shows a clear upward trend, indicating non-stationary behavior.
- Variability increases with the level of the series, suggesting time-varying variance.
- Rolling statistics confirm that both mean and variance change over time prior to transformation.
- Log transformation has proven to reduce scale effects and to stabilise the variance. However, it did not remove the underlying trend.
- First Order Differencing effectively removes the long-term trend,  resulting in a more stable mean and variance.
- Autocorrelation analysis after transformation shows that long-range dependence has been removed, with only weak short-term effects remaining.
- Partial Autocorrelation indicates no significant direct autoregressive dependence after transformation.
## Stationarity Conclusion
As already established in the key findings the raw series has exhibited non-stationary behavior which is supported by the rolling statistics as there is a visible upward trend and the variance changes with time.
After applying log transformation and first order differencing, the rolling statistics indicate improved stability in both mean and variance. Autocorrelation and partial autocorrelation diagnostics further suggest that long-term effects have been removed, with only short-term effects remaining. Together, these findings indicate that the transformed series characteristics are consistent with approximate stationarity and thus is suitable for subsequent time-series modelling. 
## Limitations
- Analysis focuses on a single aggregation of the series without exploration of any other aggregation levels.
- No external variables have been incorporated into the analysis.
- The project is limited to exploratory analysis and does not include forecasting or model evaluation.
## Next Steps
Building on the stationarity diagnostics established in this analysis, future work will include fitting statistical forecasting models such as ARIMA and SARIMA. Subsequent projects will also explore machine learning-based approaches for time series prediction and compare their performance against traditional statistical baselines.
## Tools Used
- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
