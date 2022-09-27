---
id: ac7n09upryyhaopekx9ic2x
title: VLOOKUP
desc: ''
updated: 1653346031436
created: 1653343503506
---
# VLOOKUP

## Google Sheets

- [Docs](https://support.google.com/docs/answer/3093318?hl=en)
- Usage: If you have known information on your spreadsheet, you can use `VLOOKUP` to search for related information by row. For example, if you want to buy an orange, you can use `VLOOKUP` to search for the price.
- Syntax
    - `VLOOKUP(search_key, range, index, [is_sorted])`
        - `search_key`: The value to search for in the first column of the range
        - `range`: The upper and lower values to consider for the search
        - `index`: The index of the column with the return value of the range. The index must be a positive integer
        - `is_sorted`: Optional input. Choose an option
            - `FALSE` = Exact match. This is recommended
            - `TRUE` = Approximate match. This is the default if `is_sorted` is unspecified
                - Important: Before you use an approximate match, sort your search key in ascending order. Otherwise, you may likely get a wrong return value. [Learn why you may encounter a wrong return value.](https://support.google.com/docs/answer/3093318?hl=en#Vlookupexactorapproximatetitle)

## My thoughts

With `INDEX` `MATCH` combination, the lookup column don't need to be at leftmost position.
![index-match-formula](https://project-static-assets.s3.amazonaws.com/MergeSpreadsheets/IndexMatch1.png){max-width: 300px, display: block, margin: 0 auto}

I can use `VLOOKUP` with sorted column and `approximate match` to get the nearest match with given data.  
In the example, I need to find commission rate based on sales figures, which are defined in lookup table
![sorted-approx-match](https://i.imgur.com/D1JO6MI.jpg){max-width: 300px, display: block, margin: 0 auto}

[[DGET|notes.tutorial.google-sheets-excel.function.dget]] is also a good alternative of `VLOOKUP`, both in Googles Sheets and Excel.

With [[QUERY function|notes.tutorial.google-sheets-excel.function.query]], I can achieve similar results in Google Sheets for `VLOOKUP`-related tasks.

Interestingly, there's a [clip](https://www.youtube.com/watch?v=qR3HVrhsoh4) that try to benchmark XLOOKUP vs INDEX MATCH with a data set of 500k rows, or 2M cells with formulas. Results tested on a `4GB RAM Virtual Machine` are as follows.

|                               | runtime | filesize  |
|-------------------------------|---------|-----------|
| original file without formula | N/A     | 5,195 KB  |
| INDEX MATCH version           | 19.12 s | 22,726 KB |
| XLOOKUP version               | 17.71 s | 22,163 KB |

Lastly, for large data set (more than 10k rows), do not use `VLOOKUP`, `INDEX MATCH` or even `QUERY`, please consider 
- [[POWER QUERY merges|notes.tutorial.google-sheets-excel.power-query.merge-query]]
- [[POWER PIVOT relationships|notes.tutorial.power-bi.relationship-in-data-model]]
- [Franchise | an open-source notebook for sql](https://franchise.cloud/)

## Related

- [Learn Google Spreadsheets | VLOOKUP - Part 1](https://www.youtube.com/watch?v=0rWeMHdWvOc)
- [Learn Google Spreadsheets | INDEX MATCH - Part 5](https://www.youtube.com/watch?v=-nqLkqXnAvg)
- [Learn Google Spreadsheets | VLOOKUP - Is Sorted, Approximate Match - Part 3](https://www.youtube.com/watch?v=AwOM3yzN3so)
- [Access Analytic | Which is faster XLOOKUP or INDEX MATCH?](https://www.youtube.com/watch?v=qR3HVrhsoh4)
- [Merge Spreadsheets | A Better Alternative to Vlookup & Index Match](https://www.mergespreadsheets.com/guides/mergespreadsheets-vlookup-indexmatch.html)
