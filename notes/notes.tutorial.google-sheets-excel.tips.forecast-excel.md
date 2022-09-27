---
id: kIBTZXaWHfCSnxg14W1Jb
title: Forecast in Excel
desc: ''
updated: 1653347529812
created: 1641944906767
---
# Create a forecast in Excel for Windows

ref: [Microsoft](https://support.microsoft.com/en-us/office/create-a-forecast-in-excel-for-windows-22c500da-6da7-45e5-bfdc-60a7062329fd), [Excel Easy](https://www.excel-easy.com/examples/forecast.html)

Starting from `Excel 2016`, we can easily create a forecast based on our historical time-based data

![forecast-sheet-button](https://support.content.office.net/en-us/media/729d4098-b4cb-4b0c-a5e1-d046a3093db9.png){max-width: 300px, display: block, margin: 0 auto}

This feature will create a new forecast worksheet that contains both a table of the historical and predicted values and a chart that expresses this data
![forecast-worksheet](https://support.content.office.net/en-us/media/1f8ebf53-95b1-43d3-a73d-c20b4d3a5aa8.png){max-width: 300px, display: block, margin: 0 auto}

We can also customize the forecast by configuring the parameters
- Forecast Start
    - Pick the date for the forecast to begin
- Seasonality
    - Seasonality indicates the length of the seasonal pattern (number of points)
    - The default value of `1` indicates seasonality is detected automatically 
    - For example, with the chart below, the length of the seasonal pattern is `4`.
    ![seasonal-pattern](https://www.excel-easy.com/examples/images/forecast/seasonal-pattern.png){max-width: 300px, display: block, margin: 0 auto}
- Confidence Interval
    - The confidence interval is the range surrounding each predicted value, in which 95% of future points are expected to fall, based on the forecast (with normal distribution). Confidence interval can help you figure out the accuracy of the prediction. 
    - A smaller interval implies more confidence in the prediction for the specific point
