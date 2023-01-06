---
id: hxh6epiehlg41xuuhwuf1m8
title: Data structure
desc: 'How did I organize the data structure of transactions in spreadsheet'
updated: 1672998118397
created: 1671847041209
---
# How did I organize the data structure of transactions in spreadsheet?

Inspired by [this post](https://www.allstacksdeveloper.com/2020/04/manage-stock-transactions-with-google-sheets.html).

The spreadsheet consists of 5 sheets:
- orderBook
- pnl
- pnl_daily
- tmp_currentPrice
- helper

## orderBook - define the structure of a transaction

The transactions are registered in a sheet called `orderBook`.

Fields of record:
- **Date**: 
    - when a transaction is executed
- **Ticker**: 
    - stock symbol
- **Type**: 4 types of transaction
    - *buy*: buy shares
    - *sell*: sell shares
    - *stock dividend*: dividend distributed as stock
    - *cash dividend*: dividend distributed as cash
- **Number of shares**: 
    - represents the number of shares involved in a transaction
    - only applicable for transactions of type BUY, SELL, and STOCK DIVIDEND
    - The value here is always positive
    - The value is **0** for *cash dividend* type of transaction.
- **Price per share**: 
    - unit price of a share in a transaction
    - the value is **0** for *cash dividend* and *stock dividend* type of transaction.
- **Transaction value**: 
    - equivalent in cash value of a transaction
    - The value here is always positive.
- **Trading fee**: paid for brokerage service
- **Income tax on selling securities**: 
    - tax responsibilities paid to Authority
    - applicable only for *sell* transaction type

## pnl - recap gain and loss from trading

Sheet `pnl` holds the metrics which evaluate the current snapshot of the trading activity's performance.

## pnl_daily - historical values of pnl

Sheet `pnl_daily` captures the historical values of `pnl`. It serves the purpose of understanding the trading's historical performance. I'm curious to learn whether I missed the opportunity to sell a security at good price or not.  

## tmp_currentPrice - end-of-day price data

Sheet `tmp_currentPrice` is a temporary helping table. It holds the end-of-day price data of every stock which I have ever traded.

## helper - temporary helping table

Sheet `helper` is a temporary helping table that holds the extra parameters. They are being used in multiple calculation steps within the two main sheets `orderBook` and `pnl`.