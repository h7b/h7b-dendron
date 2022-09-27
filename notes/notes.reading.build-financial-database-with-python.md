---
id: 7GDitBrWh8EtejiUqqvJH
title: Build Financial Data Database with Python
desc: ''
updated: 1647563216038
created: 1642738488330
---
# Reading 2022-01-21

## Metadata

- Ref:: [PythonForFinance](https://pythonforfinance.net/2020/10/24/build-a-financial-data-database-with-python/) 
- Title:: Build a Financial Data Database with Python
- Author:: Stuart Jamieson
- Year of publication:: 2020
- Category:: Blog
- Topic::

## Notes from reading

data pipeline mindmap
  ![data-pipeline](https://pythonforfinance.net/wp-content/uploads/2020/10/DataPipeline-1170x638.jpg){max-width: 300px, display: block, margin: 0 auto}

Entity-Relation diagram
  ![er-diagram](https://pythonforfinance.net/wp-content/uploads/2020/10/db_tables.png){max-width: 300px, display: block, margin: 0 auto}

idea: 
  - create a simple local database using [SQLite](https://www.sqlite.org/index.html) 
  - use [pandas-datareader](https://pydata.github.io/pandas-datareader/index.html#) to scrape price historical data from [Yahoo Finance](https://finance.yahoo.com/) then, clean and write the collected data into the local database

thoughts:
  - the author agree that relational database is possibly not suitable for security prices. He accepts that time-series DBs have certain benefits over SQL DBs when it comes to large amounts of financial time-series data.
  - He explained his reason of choice. Sqlite comes pre-packaged with Python, it exists in a single .db file and is accessible without faffing around with setting up SQL servers
  - However, I am not aiming this blog at those who would have their own SQL servers and who are looking to build an enterprise grade financial DB here. This whole blog is aimed at individuals, many of whom are in the learning phase of their journey…so I stand by my choice of an SQL database for this article. Sqlite comes pre-packaged with Python, it exists in a single .db file and is accessible without faffing around with setting up SQL servers and the like. For the amounts of data they are likely to be scraping (end of day in my example) then, again an SQL DB is more than sufficient for that. I can assure you at many smaller funds and CTAs you will often find their data held in SQL DBs. It all comes down to use case