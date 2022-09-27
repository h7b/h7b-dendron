---
id: ShURLFJ0dRtctFHpFXcR0
title: Reduce Data Model Size
desc: ''
updated: 1640396882714
created: 1640392344756
---
# Power Query: Reduce Data Model Size, Transformations to Columnar Database Size

ref: [ExcelIsFun](https://www.youtube.com/watch?v=fO_Vymn1e8U)

Grain or Granularity is Size or level of detai

The more granular, the smaller the size, like a grain of sand is small
The less granularity, the more aggregated the number is (the bigger the number is), like moving from adding total sales from daily sales to monthly sales to year sales and so on
![granularity](https://i.imgur.com/Rclc8Q7.jpg){max-width: 300px, display: block, margin: 0 auto}

Efficiency:
- Source data filesize: 707 MB
- After loading all rows and columns into Data Model filesize: 184 MB
- After loading only needed records for analysis: 3 MB

So the idea of a good Data Model:
- Contains only necessary data for end solution
- easy to use for Decision Maker
- allows fast queries
- easy to update structurally
- Make as many calculations at the data source (like SQL database) or in the `Data Modeling` phase in Power Query to avoid `DAX Calculated Columns`. `DAX Calculated Columns` are not stored as efficiently as raw data columns