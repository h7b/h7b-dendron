---
id: d3rad7oh4s4dr7y5uh47wnm
title: Blend Data
desc: Blend Data in Google Data Studio
updated: 1661950365661
created: 1661949992478
---
# Data blending in Data Studio

## Merge data tables in Data Studio

ref: 
- [Learn Google Spreadsheets | Google Data Studio - Blend Data, Join Tables Using Relationships - Part 2](https://www.youtube.com/watch?v=VJhtZ7x7nZk) 
- [Learn Google Spreadsheets | Google Data Studio - Blend Data, Left Outer Join in Depth - Part 3](https://www.youtube.com/watch?v=fkJIbfOUjf8)

Data Studio can blend data by joining two tables source based on the primary key column, then visualize the blended data.

This `blend data` feature is equivalent to a `Left Outer Join` in SQL and [[Power Query|notes.tutorial.google-sheets-excel.power-query.merge-query]] for Microsoft Power BI.

## Data blending improvements

ref: [Data Studio Help](https://support.google.com/datastudio/answer/11542817)

Update 2022-02-17: with improved data blending, you can now select from 5 different join operators. (Previously, you were limited to left outer join.)
- Inner join
    - Returns only matching rows from the left and right tables
- Left outer join
    - Returns matching rows from the right table, plus non-matching rows from the left tables
- Right outer join
    - Returns matching rows from the left tables, plus non-matching rows from the right table
- Full outer join
    - Returns all matching rows from the left tables or the right table
- Cross join
    - Returns every possible combination of rows from the left and right tables
