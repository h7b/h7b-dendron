---
id: lk09ao2x5czatp8qkti4bjk
title: Track Daily History
desc: ''
updated: 1672718293191
created: 1672712963809
---
# Track Daily History

caveat: this approach only works for values and formulas that don't need the spreadsheet to be open. For example, if your values are calculated using the GoogleFinance() function then the above approach will not work. The problem is that GoogleFinance() only executes when the spreadsheet is open.

## Situation

- I want
    - to automatically record a daily history of values in `pnl` sheet
    - to force refreshing `IMPORTXML` function in `tmp_currentPrice` sheet, while the document is not opened
- Reason: watch the daily performance of my portfolio, to learn when I missed the chance to realize the profit.

## Script

## Related

- [gadgetsappshacks | How to automatically record a daily history of values in a Google Spreadsheet](https://www.gadgetsappshacks.com/2013/08/how-to-automatically-record-daily.html)
- [google | How to automatically record a daily history of values in a Spreadsheet](https://support.google.com/docs/thread/105288786/how-to-automatically-record-a-daily-history-of-values-in-a-spreadsheet?hl=en)
- [google | How to automatically capture data from a cell at regular time intervals?](https://support.google.com/docs/thread/5686718/how-to-automatically-capture-data-from-a-cell-at-regular-time-intervals?hl=en)
- [sheetgo | Track changes in Google Sheets: How to record historic values](https://blog.sheetgo.com/how-to-solve-with-sheetgo/track-changes-in-google-sheets/)