---
id: 75dd1mcxayd7teu781pjfne
title: Create Trading Spreadsheet
desc: 'Create a Trading Spreadsheet'
updated: 1670107181066
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

To do
- Create an automated sheet to calculate the current value of the portfolio, with P/L

## Thinking

I have written about [[notes.daily.2022-10-24.vn-stock-market-research]]. From that research, I learned that there is no free API data feed for hobbyist to play with the historical data of Vietnam stock market. So I have to write python script to crawl historical data from [investing.com](https://www.investing.com/) then import to Google Sheets.

- Use [investiny](https://github.com/alvarobartt/investiny) python package to crawl data
- Read tutorials
    - [Youtube | How to Use Google Sheets With Python](https://www.youtube.com/watch?v=bu5wXjz2KvU)
    - [coupler | How to Connect Python to Google Sheets](https://blog.coupler.io/python-to-google-sheets/)
    - [Lucas Nunes Fernandes | How to locally run Python on Google Sheets](https://betterprogramming.pub/how-to-enable-pythons-access-to-google-sheets-e4264cdb545b)
    - [Youtube | Google Sheets Database with Python Web Scraping](https://www.youtube.com/watch?v=ct0xvw_Z0tU)
    - [Youtube | Google Sheets - Python API, Read & Write Data](https://www.youtube.com/watch?v=4ssigWmExak)

[Click here](https://docs.google.com/spreadsheets/d/1CMeBjHsBpL8_txMd6hhwQkfvEhAknmi-rNLycZaXszc/edit?usp=sharing) to access my work-in-progress spreadsheet, with sample data.