---
id: uqi5q8ynnmi2r6j50seuref
title: Usage
desc: ''
updated: 1653344902247
created: 1653344776533
---
# Usage

## QUERY function with Variables, Referencing value in a cell
ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=JPrhBUhxlPY)

Duplicate [this spreadsheet file](https://docs.google.com/spreadsheets/d/10QXfX2OqIbHJNnylAuTL6-MJ0EfNADG7e75ZKq-j_F4/) to practice

Consider an example of `data` table

![example-data-table](https://i.imgur.com/fSdVn1B.jpg){max-width: 300px, display: block, margin: 0 auto}

with a 1st query
```javascript
=QUERY(data!A1:G100, "SELECT * WHERE G > 8000", 1)
```

The statement `SELECT * WHERE G > 8000` of the query is a string (text). So when I want to interpret the query, I need to alter the query with the ampersand (`&`) to concatenate strings.

If I want to set the `8000` value to the cell `B1`, and my query will change dynamically with the input of user in cell `B1`, the `select` statement is modified as
```javascript
"SELECT * WHERE G > "&B1
```

Now if I need to alter a 2nd query
```javascript
=QUERY(data!A1:G100, "SELECT * WHERE G > 8000 ORDER BY A DESC", 1)
```
With the desire of setting `8000` to cell `B1` as above, I will change the `select` statement by concatenating 2 strings `"SELECT * WHERE G > "` and `" ORDER BY A DESC"`, with my cell `B1` in the middle.
```javascript
"SELECT * WHERE G > "&B1&" ORDER BY A DESC"
```

Now if the altered value is not a number `8000` but a string `South`, will the same trick work with my 3rd query?
```javascript
=QUERY(data!A1:G100, "SELECT * WHERE B = 'South'", 1)
```
Frankly, I need to concatenate 2 strings 
- `"SELECT * WHERE B = '"` and 
- `"'"`, the apostrophe `'` is embraced by the double quotes `""`), 

with the string `South` in the middle replaced by cell `B1`. Hence the modified `select` statement will be
```javascript
"SELECT * WHERE B = '"&B1&"'"
```

## QUERY function with case insensitive comparison
ref: [Learn Google Spreadsheets](https://youtu.be/JPrhBUhxlPY?t=755)

Alternate the `select` statement by `LOWER` function, to interpret the strings as `lowercase` letter. The `UPPER` function would have the same effect.
```javascript
=QUERY(data!A1:G100, "SELECT * WHERE LOWER(B) = '"&LOWER(B1)&"'", 1)
```

An interesting fact, in the query above, 
- the 1st `LOWER(B)` is a clause from `SELECT` statement of the query languange
- the 2nd `LOWER(B1)` is a function of Google Sheets

These two `LOWER` are different entities with similar syntax. 

## Filtering With Dates In The QUERY Function
ref: [BenCollins](https://www.benlcollins.com/spreadsheets/query-dates/), [Learn Google Spreadsheets](https://www.youtube.com/watch?v=Fbdu5jvjBYg)

The problem occurs because dates in Google Sheets are actually stored as serial numbers, but the Query function requires a date as a string literal in the format `yyyy-mm-dd`, otherwise it can’t perform the comparison filter.

Desired output
```sql
select C, B where B > date '2000-01-01'
```

The QUERY should be written as
```javascript
="select C, B where B > date '"&TEXT(DATEVALUE("1/1/2000"),"yyyy-mm-dd")&"'"
```

If I want to reference to a date in cell A1, the query is
```javascript
=QUERY(Data!$A$1:$H$136,"select C, B where B > date '"&TEXT(A1,"yyyy-mm-dd")&"'",1)
```
The `TEXT(A1,"yyyy-mm-dd")` function converts the date in cell `A1` to the required format for the Query formula by specifying a format of `yyyy-mm-dd`. It then will be inserted in the middle of these 2 strings by concatenation:
- string 1: `"select C, B where B > date '"`
- string 2: `"'"`

Which lead to the query
```javascript
"select C, B where B > date '"&TEXT(A1,"yyyy-mm-dd")&"'"
```

## Add a total row to a Query Function table
ref: [BenCollins](https://www.benlcollins.com/spreadsheets/query-total-row/)

use an array formula

```javascript
= { QUERY ; { "TOTAL" , SUM(range) } }
```

## Query from multiple ranges
ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=_N5zhAipVn0)

- Put the combined ranges inside an `array` by enclosing them within brackets `{}`, and separating these ranges by semicolons (`;`) (read [[here|notes.tutorial.google-sheets-excel.tips.arrays-in-sheets]] to understand the reason)
- Instead of referencing columns by their letter `A, B`, refer to them as `Col1, Col2` depending on their order

Example

```javascript
=query({sheets1!A:B; sheets2!A:B}, "SELECT Col1 WHERE Col2 CONTAINS 'value' ")
```

## Query from a different sheet
ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=_N5zhAipVn0)

use `IMPORTRANGE` function inside of `QUERY` function.

```javascript
=QUERY(IMPORTRANGE("sheet_id","all_orders!E1:I21"),
  "SELECT Col1,Col4,Col5 WHERE Col5>50 ORDER BY Col4 LABEL Col1 'Sandwich name'")
```

## How to build Less Error-Prone QUERY Function

ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=qHm7P155wWo)

Consider an example of `data` table

![example-data-table](https://i.imgur.com/fSdVn1B.jpg){max-width: 300px, display: block, margin: 0 auto}

A typical query
```javascript
=QUERY(data!A1:G100, "SELECT A, D, G WHERE G > 8000", 1)
```

The query above will be error if we change column order (by inserting new column on the most left) in the `data` table

So the query will be more robust if we modify
```javascript
=QUERY({data!A1:G100}, "SELECT Col1, Col4, Col7 WHERE Col7 > 8000", 1)
```
But in this version, the query will give wrong output if we insert a new column in the middle of `data` table.

This inspire us to find a better, but longer syntax by choosing separately 3 columns that we need, and putting them in an array.
```javascript
=QUERY({data!A1:A100,data!D1:D100,data!G1:G100}, "SELECT Col1, Col2, Col3 WHERE Col3 > 8000", 1)
```
- be aware that the 3 elements in the array are seperated by commas (`,`)
- read [[here|notes.tutorial.google-sheets-excel.tips.arrays-in-sheets]] to understand the reason

## Use `QUERY` to filter data based on dropdown list
ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=nLW8SerwnJo)

Use combination of `IF` and `QUERY` to enable an `All Regions` option in dropdown list.
```javascript
=QUERY(
    data!A1:F, 
    "SELECT * WHERE 1=1 "
    &IF(A2="All Regions","","AND LOWER(B)=LOWER('"&A2&"')")
    &IF(B2="All Reps","","AND LOWER(C)=LOWER('"&B2&"')"),
    1
    )
```
When `All Regions` and `All Reps` are chosen, the output strings will be blank. Hence I need to use the `1=1` trick to keep `SELECT` statement in correct syntax 
```sql
SELECT * WHERE 1=1
```

## Rename columns and format results
ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=eQKmAcdVccs)

how to rename columns using `label`, `format` clause in Google Sheets QUERY & format results as number, currency, different date types, rename and format multiple columns.

example:  
```javascript
=QUERY(
    data!A1:F, 
    "SELECT A, B, E-F
        LABEL E-F 'Net'
        FORMAT E-F '$#,###.00', A 'DDDD'"
)
```

## Use TEXTJOIN to create dynamic Query statement
ref: [Learn Google Spreadsheets](https://youtu.be/cH__zeKlo7Q?t=798)

By integrating [TEXTJOIN](https://www.sheetaki.com/how-to-use-textjoin-function-in-google-sheets/) function, you can create a dynamic Query statement based on user inputs.
![dynamic-query-example](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-02-08_214228_KAe5rRHro.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1644353011231){max-width: 300px, display: block, margin: 0 auto}
