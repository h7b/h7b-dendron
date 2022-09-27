---
id: yt58K4JQAuLohBdZIPKG7
title: Group Summarize Row
desc: ''
updated: 1640307480541
created: 1640306646209
---
# Grouping or summarizing rows

ref: [Microsoft](https://docs.microsoft.com/en-us/power-query/group-by), [ExcelIsFun](https://www.youtube.com/watch?v=hs21s0TWT14)

In Power Query, you can group values in various rows into a single value by grouping the rows according to the values in one or more columns
![group-by-concept](https://i.imgur.com/fTQjgwG.jpg){max-width: 300px, display: block, margin: 0 auto}

Use `Group by` feature.
![group-by-button](https://docs.microsoft.com/en-us/power-query/images/me-group-by-transform-icon.png){max-width: 300px, display: block, margin: 0 auto}

With a sample data
![](https://docs.microsoft.com/en-us/power-query/images/me-group-by-right-click-icon.png){max-width: 300px, display: block, margin: 0 auto}

Typical use case of `Group by`:
- summarize the total units sold at the country and sales channel level
  ![group-by-summarize](https://docs.microsoft.com/en-us/power-query/images/me-group-by-add-aggregated-column-final.png){max-width: 300px, display: block, margin: 0 auto}
- you want total units sold and—in addition—you want two other columns that give you the name and units sold for the top-performing product, summarized at the country and sales channel level
  ![group-by-row-operation](https://docs.microsoft.com/en-us/power-query/images/me-group-by-row-operation-final-table.png){max-width: 300px, display: block, margin: 0 auto}
- fuzzy grouping that uses an approximate match algorithm for text strings
  ![group-by-fuzzy](https://docs.microsoft.com/en-us/power-query/images/me-fuzzy-grouping-sample-source-table.png){max-width: 300px, display: block, margin: 0 auto}  
  ![](https://docs.microsoft.com/en-us/power-query/images/me-fuzzy-grouping-sample-final-table-no-transform-table.png){max-width: 300px, display: block, margin: 0 auto}