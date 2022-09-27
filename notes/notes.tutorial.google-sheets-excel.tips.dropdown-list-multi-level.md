---
id: ypZUL3k0YAU07wTXjpfuC
title: Dropdown List Multi Level
desc: ''
updated: 1653346370095
created: 1638995782583
---
# Create a multi level dependent dropdown list in Google Sheets

ref: 
- [Learn Google Spreadsheets | Google Sheets - Yes / No Dropdown List, Multiple Selection Based on Other Cells](https://www.youtube.com/watch?v=j_0z4FReN5A)
- [Learn Google Spreadsheets | QUERY - Drop Down List to Filter Data - Google Sheets](https://www.youtube.com/watch?v=nLW8SerwnJo)

Situation: We have a data table as follows. We need to create the 1st row with 3 dropdown list
- User select choice from 1st one for column `Make`. 
- 2nd dropdown list for column `Model`, which depends on the input of `Make`. 
- then a 3rd dependent cell `Model version`, based on value of 2nd dropdown input `Model` 

![example-table-2](https://i.imgur.com/D1Lh2yc.jpg){max-width: 300px, display: block, margin: 0 auto}

Idea 1: use `FILTER` function to create a helper table to filter out the records in dependent column

Idea 2: use `QUERY` function to create a helper table to filter out the records in dependent column.

Thoughts: 
- these 2 methods require a helper table for each dependent dropdown list.
- applicable for only one row

---
ref: [Learn Google Spreadsheets | Google Sheets - Dependent Drop Down List for Entire Column, Multiple Levels](https://www.youtube.com/watch?v=s-I8Z4nTDak)

I have similar situation as above, 3 level dropdown list. But now need to be applicable to all rows, not only the 1st row. Supposing all of possible options for 3 dropdown list are listed as in table below.

![example-table-2](https://i.imgur.com/MVQ6quW.jpg){max-width: 300px, display: block, margin: 0 auto}

Idea: use custom [Google Apps Script](https://developers.google.com/apps-script) to apply a data validation rule using method [requireValueInList](https://developers.google.com/apps-script/reference/spreadsheet/data-validation-builder#requirevalueinlistvalues) to each dependent dropdown.

Clone this [gist](https://gist.github.com/h7b/3c11a4595559e58efd586cde06dede97#file-threelvldropdownlist-gs) as a new project inside your spreadsheet to practice.

Note from an user in practicing the [gist](https://gist.github.com/h7b/3c11a4595559e58efd586cde06dede97#file-threelvldropdownlist-gs)

>For those who gets the "TypeError: Cannot read property 'range' of undefined." for the OnEdit(e) function, try change the first two lines of `onEdit` function:
```javascript
function onEdit(activeCell) {
  var activeCell = ws.getActiveCell();
```
Also, I think you need to do Data > Date Validation for cells in column A on the "master" worksheet first before running the app script.

Thoughts:
- this method is applicable to all rows
- don't need to have a secondary helper table for each dependent dropdown list.
- The script run row by row, on each input of user in the 1st column.
- This script will encounter an execution error for `onEdit` says: `The data validation rule has more items than the limit of 500. Use the "List from a range" criteria instead.` It means that the limit of number of choices in `Option` sheet for each dependent dropdown is 500.

---
ref:
- [Learn Google Spreadsheets | Google Sheets - Dependent Dropdown List for Entire Column - App Scipt, Run On User Input - Part 1](https://www.youtube.com/watch?v=1SIN5NyQ9fw)
- [Learn Google Spreadsheets | Google Sheets - Dependent Dropdown List for Entire Column - Apps Scipt, Match Alternative - Part 2](https://www.youtube.com/watch?v=8aOn0VMgG1w)

This is a workaround from the `limit of 500` of method [requireValueInList](https://developers.google.com/apps-script/reference/spreadsheet/data-validation-builder#requirevalueinlistvalues) mentioned previously. But not as neat as above solution.

Idea: use custom [Google Apps Script](https://developers.google.com/apps-script) to apply a data validation rule using method [requireValueInRange](https://developers.google.com/apps-script/reference/spreadsheet/data-validation-builder#requirevalueinrangerange) instead.

The tutorial presented a 2 level dependent dropdown, with the options for data validation being structured  as in the figure below. 
- Row 1 is used for the dropdown `Brand`. 
- Each column is reserved for the dependent dropdown `Model`

![example-table-3](https://i.imgur.com/qzeSYgU.jpg){max-width: 300px, display: block, margin: 0 auto}

Clone this [gist](https://gist.github.com/h7b/3c11a4595559e58efd586cde06dede97#file-twolvldropdownlist-gs) as a new project inside your spreadsheet to practice.

Thoughts:
- I need to write temporary data range somewhere in the spreadsheet, which will be quite messy.
