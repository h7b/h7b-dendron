---
id: hxh6epiehlg41xuuhwuf1m8
title: Manage Stock Transactions with Sheet
desc: 'Manage Stock Transactions With Google Sheets'
updated: 1671849162306
created: 1671847041209
---
# Manage Stock Transactions With Google Sheets

ref: [allstacksdeveloper](https://www.allstacksdeveloper.com/2020/04/manage-stock-transactions-with-google-sheets.html)

Inspired by [this post](https://www.allstacksdeveloper.com/2020/04/manage-stock-transactions-with-google-sheets.html).

## Define the structure of a transaction

The transactions are registered in a sheet called `orderBook`.

Fields of record:
- Date: when a transaction is executed
- Ticker: stock symbol
- Type: 4 types of transaction
    - buy: buy shares
    - sell: sell shares
    - stock dividend: dividend distributed as stock
    - cash dividend: dividend distributed as cash
- Number of shares: represents the number of shares involved in a transaction
    - only applicable for transactions of type BUY, SELL, and STOCK DIVIDEND
    - The value here can be negative or positive:
        - Positive (+): Shares of a company are increased in the portfolio, i.e. buying
        - Negative (-): Shares of a company are decreased in the portfolio, i.e. selling.
- Price: unit price of 1 share per transaction
- Money value: equivalent cash value of a transaction
    - Positive (+): Money goes into the portfolio. They are for transactions of type: SELL, and STOCK/CASH DIVIDEND
    - Negative (-): Money goes out of the portfolio. They are for transactions of type: BUY
- Trading commission fee: paid for brokerage service
- Income tax on selling securities: tax responsibilities paid to Authority