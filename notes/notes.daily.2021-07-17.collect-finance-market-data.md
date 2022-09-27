---
id: WXoYpLmbGZWi9gVX
title: How to Collect Market Data (stocks/crypto)
desc: How to Collect Market Data (stocks/crypto)
updated: 1661178007675
created: 1626513463054
tags:
  - topic.investment
  - cat.tut
---
# How do I get stocks/crypto trading data

Ref: [Towards Data Science](https://towardsdatascience.com/best-5-free-stock-market-apis-in-2019-ad91dddec984), [Algotrading101](https://algotrading101.com/learn/yfinance-guide/), [awesome-quant | Data Sources](https://github.com/wilsonfreitas/awesome-quant#data-sources)

## Paid data sources

![[notes.misc.side-business-idea#data-api-provider,1]]

## Free open source community package:

- manually download historical data from <https://www.investing.com/> or use [[notes.tutorial.python.packages.investpy]]
- [[notes.tutorial.python.packages.pandas-datareader]]
- [OpenBB](https://openbb.co/)
- [awesome-quant](https://github.com/wilsonfreitas/awesome-quant)
    - curated list of libraries, packages and resources for Quants
- [TradeKit](https://github.com/hackingthemarkets/tradekit)
    - a collection of open source server components and Python libraries for building your own financial applications, data analysis tools, and trading bots
- [[notes.tutorial.python.packages.quantstats]]
- [[notes.tutorial.python.packages.vnquant]] for Vietnam stock market

## Related Resources

### Tutorials

- [Investopedia | Basics of Algorithmic Trading: Concepts and Examples](https://www.investopedia.com/articles/active-trading/101014/basics-algorithmic-trading-concepts-and-examples.asp)
- [Algotrading101 | Yahoo Finance API Guide](https://algotrading101.com/learn/yahoo-finance-api-guide/)
- [Algotrading101 | Alpha Vantage API Guide](https://algotrading101.com/learn/alpha-vantage-guide/)
- [Algotrading101 | IEX API Guide](https://algotrading101.com/learn/iex-api-guide/)
- [IEX cloud blog | How to Get Market Data in Python](https://iexcloud.io/community/blog/how-to-get-market-data-in-python)
- [Analyzing Alpha | Get Historical Price Data from Polygon.io](https://analyzingalpha.com/get-historical-price-data-polygon)
- [Analyzing Alpha | Insert Crypto Price Data Using SQLAlchemy, Python & Pandas](https://analyzingalpha.com/insert-crypto-price-data-sqlalchemy)
- [Analyzing Alpha | Query Price Data Using SQLAlchemy, Python & Pandas](https://analyzingalpha.com/query-price-data-sqlalchemy)
- [Analyzing Alpha | How to Create an Equities Database](https://analyzingalpha.com/create-an-equities-database)
- [Analyzing Alpha | How to Create a Financial Statement Database](https://analyzingalpha.com/financial-statement-database)
- [Thecleverprogrammer | Pandas Datareader using Python](https://thecleverprogrammer.com/2021/03/22/pandas-datareader-using-python-tutorial/)
- [Algovibes | Pandas Dataframes and SQL - How to write dataframes into a sql database/get sql table to dataframe](https://www.youtube.com/watch?v=OjMDXTlVOYU)
- [Algovibes | How to connect Python with a SQL database SQLITE](https://www.youtube.com/watch?v=pU53JUhSnkY)
- [[Analyze cryptoassets using PostgreSQL and TimescaleDB|notes.reading.timescaledb-analyze-cryptoassets]]
- [Part Time Larry | Create Tables with PostgreSQL and TimescaleDB](https://www.youtube.com/watch?v=P-flYBbmCws&list=PLvzuUVysUFOsrxL7UxmMrVqS8X2X0b8jd&index=4)
- [Part Time Larry | Alpaca API, PostgreSQL, and TimescaleDB](https://www.youtube.com/watch?v=RAIqlK5K7-s)
    - the author demonstrate how he initialized TimescaleDB using docker, get stock data from Alpaca API and populate them into the database 
- [TimescaleDocs | Analyze historical intraday stock data](https://docs.timescale.com/timescaledb/latest/tutorials/analyze-intraday-stocks/)
- [Erol Aspromatis | Get Stock Pricing Data From The Polygon.io API For Algo-Trading Using Python](https://www.youtube.com/watch?v=sTlBQ3nVuJE)
- [[PythonForFinance - Build Financial Data Database with Python|notes.reading.build-financial-database-with-python]]
- [Part Time Larry | QuantStats: Portfolio Analytics with Python Tutorial](https://www.youtube.com/watch?v=Dm8GaSYZPF8)
- [Part Time Larry | IEX Cloud API - Stock Fundamentals Dashboard](https://www.youtube.com/watch?v=bPPJTc3JoMI)
- [Part Time Larry | TradeWell Backtesting App](https://www.youtube.com/watch?v=zxI97CmYGh0)

## Getting started

Initially I intended to use Sqlite or PostgreSQL as the database engine. After reading about [[BigQuery|notes.tutorial.google-bigquery]], I incline to this solution, since its free tier offers 10GB storage and I don't need to manually manage the database. BigQuery is also integrated directly into [Deepnote](https://deepnote.com/) or Jupyter notebook.

1. Create a new Google account for BigQuery
