---
id: 75dd1mcxayd7teu781pjfne
title: Manage Stock Trading With Google Sheets
desc: Manage Stock Trading With Google Sheets
updated: 1672715639615
created: 1669812452443
tags:
  - cat.tut
  - topic.investment
---
# Manage Stock Trading With Google Sheets

I want to create a spreadsheet to monitor the performance of trading stocks in Vietnam market.

## Project status

DONE
- Input manually each trade into `orderBook` sheet
- View recap of the portfolio with the automated sheet `pnl`, with the current value of the portfolio, realized/unrealized P/L 
- View list of executed trades, sorted by ticker in the automated sheet `orderBook_sortedByTicker`
- Compute cost basis of stocks with FIFO method

## Thoughts

From the article of [[notes.daily.2022-10-24.vn-stock-market-research]], I learned that there is no free API data feed for hobbyist to play with the end-of-day historical price data of Vietnam' securities. So I intend to crawl data from [investing.com](https://www.investing.com/) then import into Google Sheets.

- Use [investiny](https://github.com/alvarobartt/investiny) python package to crawl data
- Read tutorials
    - [Youtube | How to Use Google Sheets With Python](https://www.youtube.com/watch?v=bu5wXjz2KvU)
    - [Youtube | Google Sheets and Python - Tutorial](https://www.youtube.com/watch?v=T1vqS1NL89E)
    - [coupler | How to Connect Python to Google Sheets](https://blog.coupler.io/python-to-google-sheets/)
    - [Lucas Nunes Fernandes | How to locally run Python on Google Sheets](https://betterprogramming.pub/how-to-enable-pythons-access-to-google-sheets-e4264cdb545b)
    - [Youtube | Google Sheets Database with Python Web Scraping](https://www.youtube.com/watch?v=ct0xvw_Z0tU)
    - [Youtube | Google Sheets - Python API, Read & Write Data](https://www.youtube.com/watch?v=4ssigWmExak)
    - [Youtube | Google Colab Tutorial - Google Sheets, Read & Write Data](https://www.youtube.com/watch?v=cN7W2EPM-dw)
    - [Youtube | Google Colab Tutorial - Fuzzy Match Lookup with Google Sheets Data Using Python Fuzzy Pandas](https://www.youtube.com/watch?v=M3JYGiM_Xm8)

[Click here](https://docs.google.com/spreadsheets/d/1CMeBjHsBpL8_txMd6hhwQkfvEhAknmi-rNLycZaXszc/edit?usp=sharing) to access my spreadsheet, with sample data and user-defined functions included.

2022-12-09 update: TIL
- I can simply use the [[notes.tutorial.google-sheets-excel.function.importxml]] formula to import the historical data from [investing.com](https://www.investing.com/) into Google Sheets. [Click here](https://blog.coupler.io/googlefinance-function-advanced-tutorial/) to read the tutorial written by `coupler.io`. For this reason, the plan to practice python for web scraping is procrastinated again
- `IMPORTXML` refreshed automatically only if the document is opened, which is good enough for current usage [^1]
- Apply [[notes.tutorial.google-sheets-excel.tips.custom-formatting-numbers]] to indicate the `millions` by `M`, the `thousands` with a `k`.

[^1]: https://support.google.com/docs/answer/12188454?hl=en

2022-12-23 update: TIL
- need to refactor formula in `pnl` sheet since `orderBook` now has 3 types of transaction (buy, sell, stock dividend)
- add a new column for `income tax on selling securities`. Learn the calculation at [[notes.reading.tax-investors-vn]]
- Calculate the column `rate of return (unrealized) (weighted by cost of purchasing)`
    - use [[notes.tutorial.google-sheets-excel.function.sumproduct]] combined with [ABS](https://support.google.com/docs/answer/3093459?hl=en) formula to get the sum of absolute value of a mixture of positive and negative numbers
    - `SUMPRODUCT(ABS($E$2:$E))`
    - in [[notes.tutorial.google-sheets-excel.function.sumproduct]] formula, when `array2` is omitted as above, the formula will calculate the sum of the products of the 2 arrays: `array1` and `{1,1,1,...}` with same length as `array1`.
    - Read more about [How To Get Absolute Value In Google Sheets](https://www.alphr.com/absolute-value-google-sheets/)

2022-12-24 update:
- refactor the formula to calculate `Realized Gain/Loss`, applying the accounting FIFO (first in, first out). It means that the shares I bought earliest will be the shares I sell first. Read more at [[here|notes.daily.2022-11-16.stock-trading-spreadsheet.fifo-cost-basis]]
- add a [[dedicated note|notes.daily.2022-11-16.stock-trading-spreadsheet.data-structure]] explaining how did I record transaction into `orderBook`.

2023-01-03 update: 
- Add [[custom script|notes.daily.2022-11-16.stock-trading-spreadsheet.track-daily-history]] 
    - to automatically record a daily history of values in `pnl` sheet
    - to force refreshing `IMPORTXML` function in `tmp_currentPrice` sheet, while the document is not opened
- Reason: watch the daily performance of my portfolio, to learn when I missed the chance to realize the profit.