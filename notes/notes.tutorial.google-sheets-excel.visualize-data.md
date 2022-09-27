---
id: 4hL9V93O6LLwFbuHQvC8H
title: Visualize Data
desc: ''
updated: 1644283795190
created: 1640230718139
---
# Tips to visualize data in Microsoft 365 and Google Sheets

ref: [ExcelIsFun](https://www.youtube.com/watch?v=UVZcamKLJgU)

Why visualize instead of presenting in table?  
One of the best reason: help us see patterns and trends
![table-vs-chart](https://i.imgur.com/aNNypjK.jpg){max-width: 300px, display: block, margin: 0 auto}

## Table design principles:
- Horizontal lines are generally necessary only for separating column titles from data values or when
indicating that a calculation has taken place.
![horizontal-line](https://i.imgur.com/1n3A01N.jpg){max-width: 300px, display: block, margin: 0 auto}
- In large tables, light shading can be used to differentiate columns
![alternate-color](https://i.imgur.com/gW8elAU.jpg){max-width: 300px, display: block, margin: 0 auto}

## Edit range of series in chart 
Use `Select Data Source` to edit the ranges that the chart is pointing to
![select-data](https://i.imgur.com/pYPRyWm.jpg){max-width: 300px, display: block, margin: 0 auto}

## Line chart with emphasize
ref: [ExcelIsFun](https://youtu.be/UVZcamKLJgU?t=2062)

Create a helper column in data source to create line chart that shows revenue and emphasizes promotions for company
![line-emphasize-1](https://i.imgur.com/WheknBf.jpg){max-width: 300px, display: block, margin: 0 auto}
![line-emphasize-2](https://i.imgur.com/IbNKVmn.jpg){max-width: 300px, display: block, margin: 0 auto}

## Combo chart with a line of average - Google Sheets
ref: [Learn Google Spreadsheets](https://youtu.be/6vbferZJNJY?t=917)

![example-combo-chart](https://i.imgur.com/qS4fI21.jpg){max-width: 300px, display: block, margin: 0 auto}

Prepare the pivot table from `sales` data table. 
- Insert a new calculated field, 
    - named `Average` 
    - with the `Summarize by` option set as `Custom`
    - with `Formula`: `SUM/COUNT`
![custom-pivot-table](https://i.imgur.com/lv4ajPt.jpg){max-width: 300px, display: block, margin: 0 auto}

Then insert a `combo chart` with the recently created pivot table as `data range`

## Combo chart with a dynamic reference line - Power BI

ref: [How to Power BI](https://www.youtube.com/watch?v=9TyKMEoUMy0), [Havens Consulting](https://youtu.be/iYC3rPLn8GQ)

![dynamic-ref-line](https://i.imgur.com/WSw6P3L.jpg){max-width: 300px, display: block, margin: 0 auto}

Idea: 
- create a `what-if` parameter with name `Prices` to simulate.
- create a `DAX measure` to define the color conditions of bar chart, based on `what-if` variable.
  ```dax
  AboveAvgPrice? =
  IF(
      [Avg Price per Person] >= [Prices Value],
      1,
      0
  )
  ```
- apply conditional formatting to that `measure`

## Dynamic Quadrant Analysis - Power BI

ref: [How to Power BI](https://www.youtube.com/watch?v=W_aAWZRgA8s)

![dynamic-quadrant-1](https://i.imgur.com/WY8zchw.jpg){max-width: 300px, display: block, margin: 0 auto}
![dynamic-quadrant-2](https://i.imgur.com/19Jeutz.jpg){max-width: 300px, display: block, margin: 0 auto}
Idea: 
- Create 2 custom reference line to draw a quadrant,
- create a `what-if` parameter to simulate, 
- create a `measure` to define color conditions of data point
  ```dax
  CF Quadrants = 
  VAR TargetPrice = [Avg Price per Person] <= [MaxAvgPricePerPerson]
  VAR TargetReviews = [# Reviews] >= [MinNumberOfReviews]
  VAR Result =
  SWITCH(
      TRUE(),
      TargetPrice && TargetReviews = FALSE(), 1,
      TargetPrice && TargetReviews, 2,
      TargetPrice = FALSE() && TargetReviews = FALSE(), 3,
      TargetPrice = FALSE() && TargetReviews,4
  )
  RETURN
      Results
  ```
- Then apply conditional formatting to the newly created `Measure` 

## Highlight datapoint in chart
ref: [How to Power Bi](https://www.youtube.com/watch?v=hmk6PxDtbNs)

![highlight-datapoint](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-04_221207_up2R4dkrg.jpg?updatedAt=1641331341158){max-width: 300px, display: block, margin: 0 auto}

Idea: create a new `measure` to catch the criteria (in this example is the average of sales), then apply conditional format with color.

![measure-average](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-04_223212_w1A67u7EQ.jpg?updatedAt=1641331947847){max-width: 300px, display: block, margin: 0 auto}

## Small Multiples in Power BI
ref: [Microsoft](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-small-multiples), [How to Power BI](https://www.youtube.com/watch?v=fYogZa7xOa8)

`Small Multiples`, or `trellising`, splits a visual into multiple versions of itself. The versions are presented side by side, with data divided across these versions by a chosen dimension. For example, a small multiple could split a `sales by product` column chart across countries or customer segments
![small-multiples-1](https://docs.microsoft.com/en-us/power-bi/visuals/media/power-bi-visualization-small-multiples/small-mulitple-sales-category-region.png){max-width: 300px, display: block, margin: 0 auto}
![small-multiples-2](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_224205_hhUV6OCqY8w.jpg?updatedAt=1641418975589){max-width: 300px, display: block, margin: 0 auto}

## Highlight a Date Range
ref: [How to Power BI](https://www.youtube.com/watch?v=gxYguoBQF4U)

![highlight-date-range](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_231346_2hYR54Jbn.jpg?updatedAt=1641420840649){max-width: 300px, display: block, margin: 0 auto}
Idea:
- connect `X-axis constant lines` to a date range slicer
- then use `Shade region` to blur the area outside of selected date range
- create a `DAX measure` to show the summary aggregation of selected period

## Custom period Slicer
ref: [How to Power BI](https://www.youtube.com/watch?v=Aom_81rvCVw)

Create a `Slicer` with custom date period 
![custom-slicer](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_234316_oyx2ntfqO.jpg?updatedAt=1641422609706){max-width: 300px, display: block, margin: 0 auto}

Idea:
- using [SELECTCOLUMN](https://docs.microsoft.com/en-us/dax/selectcolumns-function-dax) function, create a helper table with all the dates within the custom date period, then put it in a filter
![](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_235006_aGmeTB2nH.jpg?updatedAt=1641423016614){max-width: 300px, display: block, margin: 0 auto}
- then connect this helper table to the `dimDate` dimension table

## Combine Actual and Forecast in one line chart
ref: [How to Power BI](https://www.youtube.com/watch?v=_TAGpAJ9rTQ)

![actual-forecast](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_000746_u-GLoNZvZ.jpg?updatedAt=1641424081902){max-width: 300px, display: block, margin: 0 auto}

Idea:
- create a `DAX measure` called `actual & forecast` to combine data points from both `actual` sales number and `forecast`
![example-combined-sales](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_001451_iv7yPBXttGI.jpg?updatedAt=1641424501508){max-width: 300px, display: block, margin: 0 auto}
![dax-measure-combined-sales](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_001832_ZG-e280Uu.jpg?updatedAt=1641424730321){max-width: 300px, display: block, margin: 0 auto}
- then draw a line chart with 2 series `actual` and `actual & forecast`, and apply color formatting for each serie.

## Dynamic benchmark range
ref: [How to Power BI](https://www.youtube.com/watch?v=PlMvvKEPgfA)

Situation: I need a shaded area which illustrate the varying range of forecast value (upper limit forecast vs lower limit forecast), then a line to show how the actual value is, vs the forecast.

![dynamic-benchmark-range](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_125059_i-W4tI8Zl.jpg?updatedAt=1641469912975){max-width: 300px, display: block, margin: 0 auto}

Idea:
- create 2 `DAX measure` to catch the `forecast - upper limit` and `forecast - lower limit`, with a `what-if parameter` to simulate the variance of the 2 forecast upper and lower limit.
- apply color formatting as `white` for the `forecast -lower limit` serie, in order to visualize a range of forecast value
![color-formatting](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_125952_W0CNpRRRag.jpg?updatedAt=1641470403873){max-width: 300px, display: block, margin: 0 auto}

## Show multiple forecast in one chart
ref: [How to Power BI](https://www.youtube.com/watch?v=dWyieDU4zWY)

Situation: I need to show forecast of sales data from multiple department, and how accurate the forecast vs actual data.

![multiple-forecast](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_141618_BN-7rDV-et.jpg?updatedAt=1641475002328){max-width: 300px, display: block, margin: 0 auto}

Idea: create `DAX measure` to show or hide data series depending on chosen slicer, then apply conditional formatting for color of each series.

## Add annotations into a chart - Power BI
ref: [Curbal](https://www.youtube.com/watch?v=3rr-XbbGT9o)

use case: 
- Annotations on charts are helpful for showing when key events occurred, especially when they have a noticeable impact on the data  or to give insights on the numbers in text form to help the reader understand the chart
- we can filter or highlight from types of events so positive and negative events can be highlighted

![annotated-chart](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-29_012559_rODs3rdRc.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643416082316){max-width: 300px, display: block, margin: 0 auto}

Idea: 
- in current active data model, create a event data table, and connect it into the calendar table
![event-data-table](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-29_013402_R1fRVcfLU.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643416456693){max-width: 300px, display: block, margin: 0 auto}
- then create custom visual for chart using [charticulator](https://charticulator.com/)

## Create dumbbell chart - Power BI
ref: [pluralsight](https://www.pluralsight.com/guides/tableau-playbook-dumbbell-chart), [PlayfairData](https://playfairdata.com/tableau-201-how-to-make-dumbbell-charts/)

dumbbell charts, aka DNA charts (or other aliases like gap chart, barbell chart, and connected dot plot). This slang name came from their appearance, which look similar to weights, and sometimes strands of DNA, when they are in a horizontal orientation. 

use case:
- illustrating the change between two data points
- the example below compares the market sales of two pizza companies from 2007 to 2016. We can observe each sales trend separately by points. In the meantime, we can also use line to see the gap between Pizza Hut and Domino's
![dumbbell-chart](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-29_080426_8WnTvoOJa.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643439904893){max-width: 300px, display: block, margin: 0 auto}

How to create:
- in Power BI, create custom visual for chart using [charticulator](https://charticulator.com/). Details in [tutorial from Curbal Data Labs](https://www.youtube.com/watch?v=gz6v8EDbjsw)
- another modified dumbbell charts to compare two variables. Details in [tutorial from Curbal Data Labs](https://www.youtube.com/watch?v=L0plebKtKXo)
  ![modified-dumbbell-chart](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-02-03_062820_MFj5xK2p-.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643866134659){max-width: 300px, display: block, margin: 0 auto}

## Evaluate performance with bullet chart
ref: [The Data Visualisation Catalogue](https://datavizcatalogue.com/methods/bullet_graph.html)

Bullet chart is an alternative to dashboard gauges and meters.

![bullet-chart-example](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-29_090037_Kw_lCcrEM.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643443264437){max-width: 300px, display: block, margin: 0 auto}

Explain the chart: 
- the main bar in the middle of the chart, known as the *Feature Measure*. 
- If the main bar has passed the position of *Comparative Measure*, you know you’ve hit your goal. 
- The segmented coloured bars behind the *Feature Measure* are used to display qualitative range scores. Each colour  are used to assign a performance range rating. So for example, poor, average and great

![bullet-chart-explain](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-29_091024_GBC2fMDBi.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643443839005){max-width: 300px, display: block, margin: 0 auto}

How to create:
- in Power BI, create custom visual for chart using [charticulator](https://charticulator.com/). Details in [tutorial from Curbal Data Labs](https://www.youtube.com/watch?v=1wBD7vD8do8)

## Show seasonality with cycle plots
ref: [Naomi Robbins](https://www.perceptualedge.com/articles/guests/intro_to_cycle_plots.pdf), [Daydreaming Numbers](http://daydreamingnumbers.com/blog/cycle-plots/)

A cycle plot (Cleveland, Dunn, and Terpenning, 1978) shows both the cycle or trend and the
day-of-the-week or the month-of-the-year effect

![cycle-plot-example-0](https://exceluser.com/wp-content/uploads/2020/02/chart-3-one-line-per-month.jpg){max-width: 300px, display: block, margin: 0 auto}
![cycle-plot-example-1](https://mkt.tableau.com/files/cycleplot.png){max-width: 300px, display: block, margin: 0 auto}

As an explanation, take a look at next chart. An analyst might want to know, for example, if sales differ by the day-of-the-week or by the month-of-the-year. The cycle plot below is created as an example of the sales of a hypothetical company over an eight week period. The horizontal line showing the mean for each day (Monday to Sunday).

![cycle-plot-example-2](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-02-03_060911_DqcsljFQa.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1643864968469){max-width: 300px, display: block, margin: 0 auto}

We see that sales for Mondays and Wednesdays have increased during the eight week period while sales for Tuesdays have decreased. Sales for the other four days were less variable and fluctuated around their means. 

How to create:
- in Power BI, create custom visual for chart using [charticulator](https://charticulator.com/). Details in [tutorial from Curbal Data Labs](https://www.youtube.com/watch?v=oe9M1o_e0WA)

## Conditional formatting a chart in Google Sheets
ref: [stackoverflow](https://stackoverflow.com/questions/68736950/how-to-set-the-color-of-bars-in-bar-chart-based-on-certain-condition-in-google-s), [Google Docs Editor Help](https://support.google.com/docs/thread/24168999/can-you-use-conditional-formatting-in-a-chart?hl=en)

![conditional-formatting-chart](https://ik.imagekit.io/casa/h7b-dendron/20220207_googleusercontents_eDGYo6TGX.png?ik-sdk-version=javascript-1.4.3&updatedAt=1644215749032){max-width: 300px, display: block, margin: 0 auto}

How to create:
- in Google Sheets, duplicate the data source to a helper table with multiple data series based on your conditions

## Stacked Bar Chart

ref: [Chartio](https://chartio.com/learn/charts/stacked-bar-chart-complete-guide/), [The Data Visualisation Catalogue](https://datavizcatalogue.com/methods/stacked_bar_graph.html)

Stacked Bar Graphs are used to show how a larger category is divided into smaller categories and what the relationship of each part has on the total amount.

100% Stack Bar Graphs show the percentage-of-the-whole of each group and are plotted by the percentage of each value to the total amount in each group. This makes it easier to see the relative differences between quantities in each group. 

![simple-vs-100%](https://datavizcatalogue.com/methods/images/anatomy/stacked_bar_graph.png){max-width: 300px, display: block, margin: 0 auto}

![example-stacked-bar-chart](https://chartio.com/assets/50552a/tutorials/charts/stacked-bar-charts/073137bf11f1c2226f68c3188128e28d66115622dcdecc9bc208a6d4117f53e8/stacked-bar-example-1.png){max-width: 300px, display: block, margin: 0 auto}

![example of data structure](https://i.imgur.com/jVnKhbn.jpg){max-width: 300px, display: block, margin: 0 auto}

## Helpful resources:

![[notes.tutorial.power-bi#add-on-for-dashboard-reporting,1]]