---
id: lsjlth2257shq5v12zd63ex
title: Usage
desc: ''
updated: 1653347232608
created: 1653347072436
---
# Usage

How to filter to get a subset data in Google Sheets?

Beside of basic techniques, there are some advanced tips that I used.

## Filter by condition using Custom formula

ref: [Learn Google Spreadsheets | Google Sheets - Filter, Filter by Text, Date, Condition, Custom Formula, Regular Expression Tutorial](https://www.youtube.com/watch?v=e7gLjNp9Qo0)

Logical comparison
![custom-formula](https://i.imgur.com/YY3puM5.jpg){max-width: 300px, display: block, margin: 0 auto}

Text comparison
```javascript
=AND(MID(H2,3,1)="3", LEFT(H2,1)="5")
```

Logical test
```javascript
=OR(AND(D2="NIKE",E2>200),AND(D2="ADIDAS",E2>400))
```

Regular Expression, which is case sensitive
```javascript
=REGEXMATCH(H2,"^5.3")
```

## Filter View and SUBTOTAL function

ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=49kkP04Whn8)

Instead of apply `Filter` to table, I can create a `Filter View` for myself or temporary use, which make the data table less confused for other users.
![filter-view](https://i.imgur.com/q2U3h7m.jpg){max-width: 300px, display: block, margin: 0 auto}

Further I can use [SUBTOTAL](https://support.google.com/docs/answer/3093649?hl=en) function to calculate the aggregation of the filtered data
![subtotal-example](https://i.imgur.com/80hrsbn.jpg){max-width: 300px, display: block, margin: 0 auto}

## FILTER function with multiple criteria

ref: [Learn Google Spreadsheets | Google Sheets - Filter Function Tutorial, Introduction to Logical Arrays](https://www.youtube.com/watch?v=JQSlbQeEz1k)

I can also use FILTER function in Google Sheets to extract data satisfying multiple criteria, through using logical arrays within FILTER function.

**Example 1:** I want to output the subset of orders (stored in column A) that belong to *customer-X* (stored in column B)
```javascript
=FILTER(A2:A100, ARRAYFORMULA(B2:B100="customer-X"))
```

Though, you need to notice the caveat of this method. The length of the logical condition array (in our example `ARRAYFORMULA(B2:B100="customer-X")`) has to match the length of the data source (`A2:A100` in our example)

**Example 2:** next to previous, now I want to extract the subset of orders that belong to 2 customers *person-X* and *person-Y*
```javascript
=FILTER(A2:A100, ARRAYFORMULA(ISNUMBER(MATCH(B2:B100,{"person-X";"person-Y"},0)))
```
You can watch the explanation of formula from [here](https://youtu.be/JQSlbQeEz1k?t=927). Just a remind that `{"person-X";"person-Y"}` is an array of 2 columns, read [[here|notes.tutorial.google-sheets-excel.tips.arrays-in-sheets]] again if you forgot the logic.

Or you can go further, by using [REGEXMATCH fucntion](https://infoinspired.com/google-docs/spreadsheet/how-to-use-regexmatch-function-in-google-sheets/) to extract data with wildcard keywords.

**Example 3:** I want to extract the subset of orders that belong to all customers that has the word *donald* in their name
```javascript
=FILTER(A2:A100, ARRAYFORMULA(REGEXMATCH(LOWER(B2:B100),"\bdonald\b"))
```

Duplicate [this spreadsheet file](https://docs.google.com/spreadsheets/d/1w3nrBtRaGtHfyh6blAt0X0OIAMC8n4MOwFrOdIgdyZE/) to practice