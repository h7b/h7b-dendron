---
id: hudhkth24p63snce1guuakp
title: DGET
desc: ''
updated: 1653343946733
created: 1653342858374
---
# DGET

## Google Sheets

- [Docs](https://support.google.com/docs/answer/3094148?hl=en)
- Usage: Returns a single value from a database table-like array or range using a SQL-like query.
- Syntax
    - `DGET(database, field, criteria)`
        - `database` - The array or range containing the data to consider, structured in such a way that the first row contains the labels for each column's values
        - `field` - Indicates which column in `database` contains the values to be extracted and operated on
            - `field` may either be a text label corresponding to a column header in the first row of `database` or a numeric index indicating which column to consider, where the first column has the value 1
        - `criteria` - An array or range containing zero or more criteria to filter the `database` values by before operating.

## Related

- [Learn Google Spreadsheets | DGET - Powerful VLOOKUP, INDEX-MATCH Replacement - Google Sheets Tutorial](https://www.youtube.com/watch?v=fhWR8yXYqwY)
    - Learn how to match data, join data from different tables & worksheets using DGET function in Google Sheets. Learn differences between DGET, VLOOKUP, INDEX/MATCH and why DGET might be an interesting or sometimes better alternative to VLOOKUP & INDEX/MATCH
    - The different output when using `DGET` vs `VLOOKUP` (see in [clip](https://youtu.be/fhWR8yXYqwY?t=269)), will happen when we have many occurrences of a record. `DGET` will return an error which states there are many occurrences. `VLOOKUP` will return the value