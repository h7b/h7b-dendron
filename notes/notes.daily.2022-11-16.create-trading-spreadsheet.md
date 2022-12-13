---
id: 75dd1mcxayd7teu781pjfne
title: Create Trading Spreadsheet
desc: 'Create a Trading Spreadsheet'
updated: 1670953395129
created: 1669812452443
tags:
- cat.tut
- topic.investment
---
# Create a Trading Spreadsheet

I want to create a spreadsheet to monitor the performance of trading stocks in Vietnam market.

## Project status

DONE
- Input manually each trade into `order_book` sheet
- View recap of the portfolio with the automated sheet `recap_sum-by-ticker`
- View list of executed trades, sorted by ticker in the automated sheet `recap_sorted-by-ticker`
- Create an automated sheet to calculate the current value of the portfolio, with P/L

## Thinking

I have written about [[notes.daily.2022-10-24.vn-stock-market-research]]. From that research, I learned that there is no free API data feed for hobbyist to play with the historical data of Vietnam stock market. So I intend to crawl historical data from [investing.com](https://www.investing.com/) then import to Google Sheets.

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

[Click here](https://docs.google.com/spreadsheets/d/1CMeBjHsBpL8_txMd6hhwQkfvEhAknmi-rNLycZaXszc/edit?usp=sharing) to access my work-in-progress spreadsheet, with sample data.

2022-12-09 update: TIL:
- I can simply use the [[notes.tutorial.google-sheets-excel.function.importxml]] formula to import the historical data from [investing.com](https://www.investing.com/) into Google Sheets. [Click here](https://blog.coupler.io/googlefinance-function-advanced-tutorial/) to read the tutorial written by `coupler.io`. For this reason, the plan to practice python for web scraping is procrastinated again
- IMPORTXML seems to be refreshed automatically every day, which is good enough for my simple trading sheet 
- Apply [[notes.tutorial.google-sheets-excel.tips.custom-formatting-numbers]] to indicate the `millions` by `M`, the `thousands` with a `k`.