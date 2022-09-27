---
id: fD1VlgtfwGzb36Dv3VajC
title: Look up Multi Criteria
desc: ''
updated: 1653347350315
created: 1638926606960
---
# Lookup with multiple criteria from multiple columns in Google Sheets

ref: [Learn Google Spreadsheets | IF Functions from Hell in Excel & Google Sheets Formulas](https://www.youtube.com/watch?v=6cwZoKdZh94)

Learn how to replace multiple nested IF functions (horrible like what you could encounter in this image) in Excel & Google Sheets formulas with other more manageable alternatives

![if-function-hell](https://i.imgur.com/PPP75Vv.jpg){max-width: 300px, display: block, margin: 0 auto}

Better solution: Use `VLOOKUP` with a helper table
![vlookup-multi-criteria](https://infoinspired.com/wp-content/uploads/2019/11/vlookup-multi-columns-29111.jpg){max-width: 300px, display: block, margin: 0 auto}

Example use case:
- define commission rate based on 1 condition: sales revenues
- define commission rate based on combination of 2 conditions: sales name, region (`VLOOKUP` tutorial starts from [here](https://youtu.be/6cwZoKdZh94?t=691))
- assign sales representative to office location

Alternative solutions: 
- [[DGET|notes.tutorial.google-sheets-excel.function.dget]] with a helper table. This could be a better solution for lookup with multiple criteria, vs [[VLOOKUP|notes.tutorial.google-sheets-excel.function.vlookup]] or `INDEX MATCH combo`. Watch [tutorial](https://www.youtube.com/watch?v=lipWG59UJts) for more details
- [[QUERY function in Google Sheets|notes.tutorial.google-sheets-excel.function.query]]
- [[FILTER function with logical arrays|notes.tutorial.google-sheets-excel.function.filter.usage#filter-function-with-multiple-criteria]]

## Related resources

- [infoinspired | How to Use VLOOKUP with Multiple Criteria in Google Sheets](https://infoinspired.com/google-docs/spreadsheet/vlookup-with-multiple-criteria-in-google-sheets)
- [Learn Google Spreadsheets | Lookup with Multiple Criteria - VLOOKUP, MATCH solved with DGET - Google Sheets](https://www.youtube.com/watch?v=lipWG59UJts)
