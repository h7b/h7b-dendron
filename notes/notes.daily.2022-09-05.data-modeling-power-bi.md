---
id: wz3wy7n6dmr8hnx1y9mpb28
title: Data Modeling in Power BI
desc: Data Modeling in Power BI
updated: 1663276780318
created: 1663185149641
tags:
  - topic.data
  - cat.tut
---
#  Data Modeling in Power BI

ref: [Pragmatic Works](https://www.youtube.com/watch?v=MrLnibFTtbA)

## Overview

A [tutorial video](https://www.youtube.com/watch?v=MrLnibFTtbA) by Pragmatic Works, related to data model in Power BI.

The `.pdf` presentation, `.pbix` file and data sample are accessible at [here](https://app.box.com/s/b826z6jwrbwcw9bc9e0f4mnhvwitgduj).

## Notes

[00:14:46](https://youtu.be/MrLnibFTtbA?t=886): 
star schema; fact table surrounded by dimension tables; fact table is on the Many side of the 1-to-many relationship with other dimension table.

![star-schema](https://ik.imagekit.io/casa/h7b-dendron/data_modeling_for_power_b_time_886_OUF2kaHyr.png?ik-sdk-version=javascript-1.4.3&updatedAt=1663204527473){max-width: 300px, display: block, margin: 0 auto}

[00:16:15](https://youtu.be/MrLnibFTtbA?t=975):
snowflake schema; similar to star schema with Fact table at the center, but dimension tables now have their own hierarchy/relation.

![snowflake-schema](https://ik.imagekit.io/casa/h7b-dendron/data_modeling_for_power_b_time_975_lyrnh2W1y.png?ik-sdk-version=javascript-1.4.3&updatedAt=1663204527586){max-width: 300px, display: block, margin: 0 auto}

[00:18:59](https://youtu.be/MrLnibFTtbA?t=1139): conceptual data model.

[00:20:57](https://youtu.be/MrLnibFTtbA?t=1257): dimensional data model: organizes data to be retrieved for reporting purposes; This model consists of Fact table and Dimension table; Fact is an event that include (or may not) measures; Dimension is a category of information, that provides the "who what where when why how" context surrounding a business process event; Dimension table contains descriptive Attributes (column in a Dim table) that define how a fact should roll up.

[01:30:30](https://youtu.be/MrLnibFTtbA?t=5430): create a surrogate key by inserting a new index column.

[01:42:24](https://youtu.be/MrLnibFTtbA?t=6144): in Data Model pane, we can create a layout that consist only the required data model; this makes the model diagram becoming neat.

![data-model-layout](https://ik.imagekit.io/casa/h7b-dendron/data_modeling_for_power_b_time_6199_mu3QIMU5v.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1663204527473){max-width: 300px, display: block, margin: 0 auto}

[01:52:18](https://youtu.be/MrLnibFTtbA?t=6738): ytd sales = TOTALYTD function.

[01:55:01](https://youtu.be/MrLnibFTtbA?t=6901): USERELATIONSHIP dax function does not create a new relationship,

[01:57:02](https://youtu.be/MrLnibFTtbA?t=7022): Use Tabular Editor tool (3rd party tool for Power BI) to create a Calculation Group which helps to reduce the number of Measures in a data model.

[02:11:10](https://youtu.be/MrLnibFTtbA?t=7870): create an aggregate fact table as a snapshot of a bigger fact table (imagine billions of rows); use Group By feature in Power Query.

![group-by-power-query](https://ik.imagekit.io/casa/h7b-dendron/data_modeling_for_power_b_time_7938_HYB-6GyvH.png?ik-sdk-version=javascript-1.4.3&updatedAt=1663204527792){max-width: 300px, display: block, margin: 0 auto}