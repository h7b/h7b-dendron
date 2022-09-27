---
id: kqxk5fnx258ue80m6llxkqu
title: QUERY function
desc: ''
updated: 1653346015896
created: 1653344381787
---
# QUERY function

## Google Sheets

- [Docs](https://support.google.com/docs/answer/3093343?hl=en)
- Usage: Runs a Google Visualization API Query Language query across data.
- Syntax
    - `QUERY(data, query, [headers])`
        - `data` - The range of cells to perform the query on.
        - `query` - The query to perform, written in the [Google Visualization API Query Language](https://developers.google.com/chart/interactive/docs/querylanguage)
            - The value for `query` must either be enclosed in quotation marks or be a reference to a cell containing the appropriate text
            - See [documents](https://developers.google.com/chart/interactive/docs/querylanguage) for further details on the query language
        - `headers` - [ OPTIONAL ] - The number of header rows at the top of `data`. If omitted or set to `-1`, the value is guessed based on the content of `data`.

## My thoughts

This is an easier-to-write alternative function of `VLOOKUP`, the combination of `INDEX(MATCH)` or `FILTER`.

This function allows me to use database-type commands (a pseudo-SQL), to manipulate data tables in Google Sheets.

Example:
```javascript
=QUERY(sales_data,"SELECT SUM(Col1),Col2 WHERE Col3>5 ORDER BY Col4 LABEL SUM(Col1) 'Sales per month'",1)
```

parameters of query:
- `ORDER BY` clause
    - sorts our data. We can specify column(s) and direction (ascending or descending). It comes after the SELECT and WHERE clauses.
- `LIMIT` clause
    - restricts the number of results returned. It comes after the SELECT, WHERE and ORDER BY clauses
- `LABEL` clause
    - we can rename the header title of a column using the LABEL clause, which comes at the end of the QUERY clause
- `GROUP BY `clause
    - is used with aggregate functions to summarize data into groups, in the same way a pivot table does
- `CONTAINS` clause
    - query by keywords matching
    - ```sql
    =query(range, "SELECT A WHERE A CONTAINS 'keyword' ")
    ```
- Arithmetic functions
    - We can perform standard math operations on numeric columns.
- Aggregation functions
    - We can use other functions in our calculations, for example `MIN`, `MAX` and `AVERAGE`.

### My use case

![[notes.tutorial.google-sheets-excel.function.query.usage#usage,1]]

## Related

- [CIFL | Google Sheets Query Function](https://codingisforlosers.com/google-sheets-query-function/)
- [BenCollins | Google Sheets Query function: The Most Powerful Function in Google Sheets](https://www.benlcollins.com/spreadsheets/google-sheets-query-sql/)
- [coupler.io | QUERY + IMPORTRANGE in Google Sheets](https://blog.coupler.io/query-importrange/)
- [sheetaki | How to Use Query With Importrange in Google Sheets](https://www.sheetaki.com/query-with-importrange-in-google-sheets/)
- [sheetgo | Combine QUERY with IMPORTRANGE in Google Sheets](https://blog.sheetgo.com/google-sheets-formulas/combine-query-with-importrange-in-google-sheets/)
- [Learn Google Spreadsheets | Google Sheets Query function | Youtube playlist](https://www.youtube.com/playlist?list=PLv9Pf9aNgemvAMlqvHP9RhXPW98g_eo7d)
- [Learn Google Spreadsheets | Google Sheets QUERY Function Tutorial - SELECT, WHERE, LIKE, AND, OR, LIMIT statements - Part 1](https://www.youtube.com/watch?v=bW6P2YvLyZg)
- [Learn Google Spreadsheets | Google Sheets - Search, QUERY function](https://www.youtube.com/watch?v=VSGKO5gx974)
- [Learn Google Spreadsheets | Google Sheets QUERY - Filter by Date Range using WHERE Statement Tutorial - Part 3](https://www.youtube.com/watch?v=LFZnSY0YdwU)
- [Learn Google Spreadsheets | QUERY Function - Select Columns with Checkboxes - Google Sheets](https://www.youtube.com/watch?v=VFSrvcqXgi8)
- [Learn Google Spreadsheets | QUERY Pivot Table -Google Sheets - Query Pivot, Group By, Month, Year Functions Tutorial - Part 6](https://www.youtube.com/watch?v=q0B58muHybM)
- [Learn Google Spreadsheets | Google Sheets - Query IN List Like SQL or Many ORs Using a Range Tutorial - Part 7](https://www.youtube.com/watch?v=AH1mRGBsjrk)