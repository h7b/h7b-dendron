---
id: 4DHLvhZXNpbtd7Pv0wIsu
title: Google Bigquery
desc: ''
updated: 1643020868449
created: 1642977450032
---
# Google Bigquery
ref:
- [Andrzej Ludwikowski | BigQuery — lessons learned](https://blog.softwaremill.com/bigquery-lessons-learned-63b8a830e628)
- [Rajesh Thallam | BigQuery Explained: Storage Overview](https://medium.com/google-cloud/bigquery-explained-storage-overview-70cac32251fa)

Overview:
- BigQuery is distributed DB
- different ways to [load data](https://cloud.google.com/bigquery/docs/loading-data) into BigQuery
- [partitioning](https://cloud.google.com/bigquery/docs/partitioned-tables) the database help to optimize queries performance and reduce query cost. Reason: The BigQuery pricing model depends heavily (among other aspects) on the amount of data that BigQuery needs to process while handling a query
![partitioned-table](https://miro.medium.com/max/875/0*67n9CCfTc4Xy4zdB){max-width: 300px, display: block, margin: 0 auto}
- [clustering](https://cloud.google.com/bigquery/docs/clustered-tables) helps to organize the data based on the contents of one or more columns in the table' schema
![clustered-table](https://miro.medium.com/max/875/0*q2fK1S1fN9YCLihb){max-width: 300px, display: block, margin: 0 auto}
- how to [remove duplicates manually](https://cloud.google.com/bigquery/streaming-data-into-bigquery#manually_removing_duplicates) in BigQuery
- the data model/schema in BigQuery is usually denormalized. Because BigQuery uses columnar storage, where each column is stored in a separate file block. This makes BigQuery an ideal solution for OLAP (Online Analytical Processing) use cases
![bigquery-storage](https://miro.medium.com/max/875/0*soejo49qke3RpTps){max-width: 300px, display: block, margin: 0 auto}
- BigQuery when used in a proper context such as append-only data, time-series data, with the ability to run very complex queries, will definitely shine

The free tier of BigQuery require credit card. From 2019, Google introduce [BigQuery sandbox](https://cloud.google.com/blog/products/data-analytics/query-without-a-credit-card-introducing-bigquery-sandbox), a credit-card free path to enable new users to experiment with BigQuery at no cost—without having to enter credit card information. BigQuery sandbox provides you with up to 1 terabyte per month of query capacity and 10GB of free storage. All tables and partitions have a 60-day retention policy. Some features of BigQuery are not included in the sandbox (DML, Streaming, Data Transfer Service).

2022-01-24, the `Try BigQuery Free` button mentioned in the [blog article]((https://cloud.google.com/blog/products/data-analytics/query-without-a-credit-card-introducing-bigquery-sandbox)) always lead to the [Free trial](https://console.cloud.google.com/freetrial) instead of BigQuery sandbox as advertised. Hence I follow this [guide](https://www.optimizesmart.com/google-bigquery-sandbox/) to access BigQuery sandbox.

## Helpful resources:

[BigQquery Pricing](https://cloud.google.com/bigquery/pricing)
- storage: The first 10 GB per month is free
- queries (analysis): The first 1 TB of query data processed per month is free

[bobby_dreamer | Loading data into BigQuery using Python](https://bobbydreamer.com/134-load-bigquery)

[Patrick Dunn | Time series analytics with BigQuery](https://medium.com/google-cloud/time-series-analytics-with-bigquery-f65867c1ce74)

[Bence Komarniczky | Loading files into BigQuery](https://towardsdatascience.com/loading-files-into-bigquery-6de1ff63df35)

[Zakhar Yung | BigQuery Tutorial – How to Add Agility to Your Business](https://blog.coupler.io/bigquery-tutorial/)