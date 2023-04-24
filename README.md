# DS 4002 Project 3

## For our third project, we wanted to create a machine learning model using economic data to project how the U.S. economy will perform in the coming years. After downloading data from the Bureau of Economic Analysis (BEA), we honed in on a testable hypothesis: The U.S. will enter a recession in 2023. To navigate our repository, adhere to the following sections. The "SOURCE" section shows how we install, build, and use our code. The "DATA" folder will enable you to see our data dictionary, a link to the Kaggle source, and notes about how we use the data. The "FIGURES" folder contains all of the figures produced and summarizes the takeaways. The "REFERENCES" section acknowledges the sources for our analysis. 

## SRC
### Installing / Building Code
The primary reference code for preparing our Auto-ARIMA model can be found here: 
https://www.section.io/engineering-education/multivariate-time-series-using-auto-arima/

### Usage of Code
To determine the parameters for our Auto-ARIMA model, we used Auto Correlation Functions (ACF) and Partial Auto Correlation Functions (PACF). After deteriming them, we applied them to our Auto-ARIMA function in Python.

## DATA
### Data Dictionary
<img width="387" alt="Screen Shot 2023-04-20 at 8 40 46 AM" src="https://user-images.githubusercontent.com/104598450/233368849-eda966a0-f8b0-41d2-b0a5-1efee9025a3b.png">
### Links to Data
Percent Change From Preceding Period in Real Gross Domestic Product:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjEiXSxbIkZpcnN0X1llYXIiLCIxOTMwIl0sWyJMYXN0X1llYXIiLCIyMDIyIl0sWyJTY2FsZSIsIjAiXSxbIlNlcmllcyIsIkEiXV19

Percent Change From Preceding Period in Real Gross Domestic Product, Real Gross Domestic Income, and Other Major NIPA Aggregates:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjMxNiJdLFsiRmlyc3RfWWVhciIsIjE5MzAiXSxbIkxhc3RfWWVhciIsIjIwMjIiXSxbIlNjYWxlIiwiMCJdLFsiU2VyaWVzIiwiQSJdXX0=

Percent Change From Preceding Period in Real Personal Consumption Expenditures by Major Type of Product:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjYxIl0sWyJGaXJzdF9ZZWFyIiwiMTkzMCJdLFsiTGFzdF9ZZWFyIiwiMjAyMiJdLFsiU2NhbGUiLCIwIl0sWyJTZXJpZXMiLCJBIl1dfQ==

Percent Change From Preceding Period in Real Government Consumption Expenditures and Gross Investment:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjk0Il0sWyJGaXJzdF9ZZWFyIiwiMTkzMCJdLFsiTGFzdF9ZZWFyIiwiMjAyMiJdLFsiU2NhbGUiLCIwIl0sWyJTZXJpZXMiLCJBIl1dfQ==

Percent Change From Preceding Period in Real Exports and in Real Imports of Goods and Services by Type of Product:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjEyOSJdLFsiRmlyc3RfWWVhciIsIjE5NjgiXSxbIkxhc3RfWWVhciIsIjIwMjIiXSxbIlNjYWxlIiwiMCJdLFsiU2VyaWVzIiwiQSJdXX0=

Percent Change From Preceding Period in Real Private Fixed Investment by Type:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjE0MSJdLFsiRmlyc3RfWWVhciIsIjE5NDgiXSxbIkxhc3RfWWVhciIsIjIwMjIiXSxbIlNjYWxlIiwiMCJdLFsiU2VyaWVzIiwiQSJdXX0=

### Relevant notes about the use of data
While these datasets contained many variables, we narrowed our factors to predict a recession down to the following: 
1. Personal consumption Expenditures
2. Gross private domestic investment
3. Exports
4. Imports 
5. Government consumption expenditures and gross investment
6. Private fixed investment
7. GDP
8. GDI
9. Disposable personal income

## FIGURES
Our figures include a plot of the different variables over time. In addition, we have ACF and PACF plots illustrate how we determined our parameters

## REFERENCES
Bureau of Economic Analysis, “Percent Change From Preceding Period in Real Gross Domestic Product,” Updated March 30, 2023. [Online]. Available:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjEiXSxbIkZpcnN0X1llYXIiLCIxOTMwIl0sWyJMYXN0X1llYXIiLCIyMDIyIl0sWyJTY2FsZSIsIjAiXSxbIlNlcmllcyIsIkEiXV19

Bureau of Economic Analysis, “Percent Change From Preceding Period in Real Gross Domestic Product, Real Gross Domestic Income, and Other Major NIPA Aggregates” Updated March 30, 2023. [Online]. Available:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjMxNiJdLFsiRmlyc3RfWWVhciIsIjE5MzAiXSxbIkxhc3RfWWVhciIsIjIwMjIiXSxbIlNjYWxlIiwiMCJdLFsiU2VyaWVzIiwiQSJdXX0=

Bureau of Economic Analysis, “Percent Change From Preceding Period in Real Personal Consumption Expenditures by Major Type of Product” Updated March 30, 2023. [Online]. Available:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjYxIl0sWyJGaXJzdF9ZZWFyIiwiMTkzMCJdLFsiTGFzdF9ZZWFyIiwiMjAyMiJdLFsiU2NhbGUiLCIwIl0sWyJTZXJpZXMiLCJBIl1dfQ==

Bureau of Economic Analysis, “Percent Change From Preceding Period in Real Government Consumption Expenditures and Gross Investment” Updated March 30, 2023. [Online]. Available:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjk0Il0sWyJGaXJzdF9ZZWFyIiwiMTkzMCJdLFsiTGFzdF9ZZWFyIiwiMjAyMiJdLFsiU2NhbGUiLCIwIl0sWyJTZXJpZXMiLCJBIl1dfQ==

Bureau of Economic Analysis, “Percent Change From Preceding Period in Real Exports and in Real Imports of Goods and Services by Type of Product” Updated March 30, 2023. [Online]. Available:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjEyOSJdLFsiRmlyc3RfWWVhciIsIjE5NjgiXSxbIkxhc3RfWWVhciIsIjIwMjIiXSxbIlNjYWxlIiwiMCJdLFsiU2VyaWVzIiwiQSJdXX0=

Bureau of Economic Analysis, “Percent Change From Preceding Period in Real Private Fixed Investment by Type” Updated March 30, 2023. [Online]. Available:
https://apps.bea.gov/iTable/?reqid=19&step=2&isuri=1&categories=survey#eyJhcHBpZCI6MTksInN0ZXBzIjpbMSwyLDMsM10sImRhdGEiOltbImNhdGVnb3JpZXMiLCJTdXJ2ZXkiXSxbIk5JUEFfVGFibGVfTGlzdCIsIjE0MSJdLFsiRmlyc3RfWWVhciIsIjE5NDgiXSxbIkxhc3RfWWVhciIsIjIwMjIiXSxbIlNjYWxlIiwiMCJdLFsiU2VyaWVzIiwiQSJdXX0=

J. Omina, “Multivariate Time Series Using Auto ARIMA,” May 24, 2022. [Online]. Available: https://www.section.io/engineering-education/multivariate-time-series-using-auto-arima/
