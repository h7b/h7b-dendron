---
id: ay8s3dxzd0eav1bxuoohq0n
title: Named ranges in Google Sheets
desc: 'Named ranges in Google Sheets'
updated: 1673872321108
created: 1673871812246
---
# Named ranges in Google Sheets

ref: [spreadsheet.dev](https://spreadsheet.dev/named-ranges-in-google-sheets)

A named range is a feature in Google Sheets that lets you give a range a unique name.

Why should you use named ranges?
- Using names for ranges instead of their `A1` notation makes formulas and Apps Script code easier to understand
- You only need to edit range references in one place

According to Google's documentation, there are some [restrictions applied to range's names](https://support.google.com/docs/answer/63175?hl=en).

We can create a named range using
- Google Sheets UI
- Google Apps Script with [setNamedRange()](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet#setnamedrangename,-range) method