---
id: 942uvytcapn6cueddj1tfk4
title: FLATTEN
desc: 'FLATTEN'
updated: 1671232422032
created: 1671231588197
---
# FLATTEN

## Google Sheets

- [Docs](https://support.google.com/docs/answer/10307761?hl=en)
- Usage: merge a list of arrays into a single-column, flat table
- Syntax
    - `=FLATTEN(range1, [range2, …])`
    - `range1` - The first range to flatten
    - ![demo](https://www.benlcollins.com/wp-content/uploads/2022/02/flattenExample.jpg){max-width: 300px, display: block, margin: 0 auto}
- Notes:
    - Values are ordered by argument, then row, then column.
- Use case:
    - unpivot in Google Sheets
        - Unpivot is a method to turn wide data into tall data
        - It’s the opposite action to a pivot table, which turns data from the tall format (database) to a wide table format
        - A characteristic of wide tables is that they have a column for each variable. Wide-format data is useful when setting up a dataset for a chart or visualization. It’s also the easiest format to analyze because it’s easy to see the values for each variable.
        - Tall format data has values that repeat in a column. A tall format is most useful when you need to have a base dataset to create a pivot table from.
        - ![demo-unpivot](https://www.benlcollins.com/wp-content/uploads/2022/02/unpivotExample.jpeg){max-width: 300px, display: block, margin: 0 auto}

## Related

- [benlcollins | The FLATTEN Function in Google Sheets](https://www.benlcollins.com/spreadsheets/flatten-function/)
- [sheetaki | How to Turn Wide Data into Tall Data in Google Sheets](https://sheetaki.com/wide-data-tall-data-google-sheets/)