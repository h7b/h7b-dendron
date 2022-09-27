---
id: bs7g8tMAvIHz1yCekerGt
title: Add Index Column
desc: ''
updated: 1639456275332
created: 1639455693239
---
# Add an index column
ref: [Microsoft](https://docs.microsoft.com/en-us/power-query/add-index-column)

The Index column command adds a new column to the table with explicit position values, and is usually created to support other transformation patterns.

For the example in this article, you start with the following table that has only one column, but notice the data pattern in the column.  
![ex-input](https://docs.microsoft.com/en-us/power-query/images/me-add-index-column-start-table.png){max-width: 300px, display: block, margin: 0 auto}

Let's say that your goal is to transform that table into the one shown in the following image, with the columns Date, Account, and Sale.  
![ex-output](https://docs.microsoft.com/en-us/power-query/images/me-add-index-column-sample-output-table.png){max-width: 300px, display: block, margin: 0 auto}

Idea: add 2 helper index column. One column `modulo 3` for column position. And another helper column `divide by 3` for row position. Then [[Pivot column|notes.tutorial.google-sheets-excel.power-query.pivot-columns]].
![ex-helper-columns](https://docs.microsoft.com/en-us/power-query/images/me-add-index-column-add-divide-integer-column.png){max-width: 300px, display: block, margin: 0 auto}