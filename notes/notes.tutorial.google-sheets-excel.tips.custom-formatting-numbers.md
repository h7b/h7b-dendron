---
id: rga3z63rms3dwve55kjsjo5
title: Custom Formatting Numbers
desc: 'Custom formatting of numbers, dates, and currencies'
updated: 1670541987944
created: 1670541276450
---
# Custom formatting of numbers, dates, and currencies

ref: [benlcollins](https://www.benlcollins.com/spreadsheets/google-sheets-custom-number-format/)

When creating a custom format, note that the formatting can consist of up to 4 parts separated by semicolons: `positive;negative;zero;non-numeric`.

![number-format](https://www.automateexcel.com/excel/wp-content/uploads/2021/11/millions-number-format-initial-data.png){max-width: 300px, display: block, margin: 0 auto}

If you add thousand separators but don’t specify a format after the comma (e.g. 0,) then the hundreds will be chopped off the number.
- you can indicate the `thousands` with a `k` by applying the custom format `0.0,"k"`
- or you can use only `M` to indicate `millions` with the custom format `0.0,,"M"`

## Related

- [automateexcel | Number Format – Millions in Excel & Google Sheets](https://www.automateexcel.com/how-to/millions-number-format/)
- [Docs by Google](https://support.google.com/docs/answer/56470?hl=en#zippy=%2Ccustom-number-formatting)