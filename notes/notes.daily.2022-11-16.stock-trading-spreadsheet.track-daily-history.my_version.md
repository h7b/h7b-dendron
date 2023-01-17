---
id: 04geuklafavqf0wsj77mxrn
title: My version
desc: ''
updated: 1673937408315
created: 1672718315847
---
# My version

## Force refreshing IMPORTXML

Set this function to be triggered by time, daily, at 16h (GMT+7). Since the closing time of Vietnam stock market is 20h (GMT+7).

```javascript
function refreshImportXml() {
  // Get the sheet that contains the IMPORTXML formula
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("test");

  // Get the range of cells that contain the IMPORTXML formula
  const range = sheet.getRange("$C$2:$C");

  // Retrieve the formulas of all cells in range
  const formulas = range.getFormulas();

  // Clear the content of all cells in range
  range.clearContent();
  SpreadsheetApp.flush();

  // then refresh the IMPORTXML formula in all cells in range
  range.setFormulas(formulas);
  SpreadsheetApp.flush();
}
```

ref: [stackoverflow](https://stackoverflow.com/questions/41175326/why-do-we-use-spreadsheetapp-flush)

Q: Why do I use `SpreadsheetApp.flush();`?

A: A programmer will use `flush()` when they want to ensure that the previous code's output and/or effects are written to the spreadsheet before continuing. If you do not `flush()`, then the code may be automatically "optimized" by using some built-in caching and bundling of operations.

Q: Explain the use of `getFormulas()` and `setFormulas()`

A: 

[getFormulas()](https://developers.google.com/apps-script/reference/spreadsheet/range#getformulas)
- Returns the formulas (A1 notation) for the cells in the range
- Result is a two-dimensional array of formulas in string format. Entries in the 2D array are empty strings for cells with no formula.

[setFormulas()](https://developers.google.com/apps-script/reference/spreadsheet/range#setformulasformulas)
- Sets a rectangular grid of formulas (must match dimensions of this range)
- This method takes input as a two-dimensional string array of formulas, indexed by row, then by column

## Capture daily history of values

1 hour after the `IMPORTXML` is refreshed. This `recordValues()` will be triggered to duplicate `pnl` into `pnl_daily`

### Version 1

Retrieve all non-empty rows in the range `A2:M` from sheet `pnl` and duplicate into sheet `pnl_daily`. 

```javascript
function recordValues() {
  // First the code accesses the spreadsheet that the script is associated with
  const ss = SpreadsheetApp.getActive()

  // Select the source Sheet that you want to retrieve the values of
  const sourceSheet = ss.getSheetByName("pnl");

  // Select the destination Sheet that you want to store the daily values
  const destSheet = ss.getSheetByName("pnl_daily");
  
  // Get the values of the range A2:M
  const range = sourceSheet.getRange('A2:M');
  const values = range.getValues();
  // Filter the `values` array to remove the blank rows
  const filteredValues = values.filter(row => row.some(cell => cell !== ''));

  // set triggered date
  const triggerDate = Utilities.formatDate(new Date(), "GMT", "yyyy-MM-dd");

  // Append the values to the history sheet
  for (let i=0; i<filteredValues.length; i++) {
    destSheet.appendRow([triggerDate, ...filteredValues[i]]);
  }
}
```

This code will get the values of the specified range in the source sheet, use the [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) method to create a new array that only contains the rows that are not blank, set the current date as the trigger date, and append the filtered values and the trigger date as new rows in the destination sheet.

The [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) method takes a callback function as an argument and returns a new array that contains only the elements for which the callback function returns a truthy value. In this example, the callback function uses the [some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some) method to check if any of the cells in the row are not blank, and returns `true` if at least one cell is not blank. This ensures that only the rows that are not completely empty are included in the filtered array.

The [appendRow()](https://developers.google.com/apps-script/reference/spreadsheet/sheet#appendRow(Object)) method takes an array of values as an argument and appends the values as a new row in the sheet. By using the [spread operator (...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) to spread the values of the `i` row of the `filteredValues` array, then append all of these values in that row as separate columns in the destination sheet.

### Version 2

Instead of retrieving all columns as in v1, now I take into account only these separated ranges `A2:A`, `H2:K`, `M2:M` from sheet `pnl` then duplicate into sheet `test_daily`.

```javascript
function recordValues() {
  // set spreadsheet
  const ss = SpreadsheetApp.getActive()

  // Select the sourceSheet that you want to record the values of
  const sourceSheet = ss.getSheetByName("pnl");

  // Select the destSheet that you want to store the daily values
  const destSheet = ss.getSheetByName("pnl_daily");

  // Get the values of column A
  const rangeA = sourceSheet.getRange('A2:A');
  const valuesA = rangeA.getValues();
  // Filter the valuesA array to remove the blank rows
  const filteredValuesA = valuesA.filter(row => row.some(cell => cell !== ''));

  // Get the values of the 4 columns H to K
  const rangeHK = sourceSheet.getRange('H2:K');
  const valuesHK = rangeHK.getValues();
  const filteredValuesHK = valuesHK.filter(row => row.some(cell => cell !== ''));

  // Get the values of column M
  const rangeM = sourceSheet.getRange('M2:M');
  const valuesM = rangeM.getValues();
  const filteredValuesM = valuesM.filter(row => row.some(cell => cell !== ''));

  // set date
  const triggerDate = Utilities.formatDate(new Date(), "GMT", "yyyy-MM-dd");

  // Append the values to the history sheet
  for (let i=0; i<filteredValuesA.length; i++) {
    destSheet.appendRow([triggerDate, filteredValuesA[i][0], filteredValuesHK[i][0], filteredValuesHK[i][1], filteredValuesHK[i][2], filteredValuesHK[i][3], filteredValuesM[i][0]]);
  }
}
```

### Version 3

Instead of writing a single row of data to the spreadsheet as in v2, now I replace [appendRow()](https://developers.google.com/apps-script/reference/spreadsheet/sheet#appendrowrowcontents) method with a custom function to write the data in batch at once.

Learned from [this tutorial by spreadsheet.dev](https://spreadsheet.dev/write-multiple-rows-to-google-sheets-using-apps-script).

The idea is to access the range in the spreadsheet where the data needs to be written and write the data to that range at once.

```javascript
function recordValues() {
  ...
  // Create an array to hold the value of triggered date
  const currentDate = Utilities.formatDate(new Date(), "GMT", "yyyy-MM-dd");
  const lenDate = filteredValuesA.length;
  let valuesDate = [];
  for (let i = 0; i < lenDate; i++) {
    valuesDate.push([currentDate]);
  }

  // Append the values to the history sheet
  // Write the 1st column which is Date
  destSheet.getRange(lastRow + 1,1,filteredValuesA.length, 1).setValues(valuesDate);
  // Write the 2nd column which is Ticker
  destSheet.getRange(lastRow + 1,2,filteredValuesA.length, filteredValuesA[0].length).setValues(filteredValuesA);
  // Write the next four columns, which are H to K
  destSheet.getRange(lastRow + 1,3,filteredValuesA.length, filteredValuesHK[0].length).setValues(filteredValuesHK);
  // Write the last column, which is M
  destSheet.getRange(lastRow + 1,7,filteredValuesA.length, filteredValuesM[0].length).setValues(filteredValuesM);
}
```

### Version 4

Replace the configuration of installable trigger from UI to Apps Script. Create a time-based trigger using Apps Script that will run the function `recordValues()` at a certain time on a recurring schedule. This trigger is managed programmatically with the [Script service](https://developers.google.com/apps-script/reference/script).

By default, the time you specify will be indexed to the timezone of the script. You can override this default by specifying the timezone using the [inTimezone()](https://developers.google.com/apps-script/reference/script/clock-trigger-builder#intimezonetimezone) method

Learned from [this tutorial by spreadsheet.dev](https://spreadsheet.dev/create-triggers-programmatically-using-apps-script), and [stackoverflow](https://stackoverflow.com/questions/19223823/google-script-trigger-weekdays-only)

```javascript
/**
 * Creates two time-driven triggers tied to the spreadsheet with the given ID
 * @see https://developers.google.com/apps-script/guides/triggers/installable#time-driven_triggers
 */
function createTimeDrivenTriggers() {
  let weekDays = [
    ScriptApp.WeekDay.MONDAY,
    ScriptApp.WeekDay.TUESDAY,
    ScriptApp.WeekDay.WEDNESDAY,
    ScriptApp.WeekDay.THURSDAY,
    ScriptApp.WeekDay.FRIDAY
    ];

  for (var i=0; i<weekDays.length; i++) {
    // Trigger refreshImportXml() function every weekday at 17:00 timezone Saigon.
    ScriptApp.newTrigger('refreshImportXml')
      .forSpreadsheet('put_your_spreadsheet_id_here')
      .timeBased()
      .onWeekDay(weekDays[i])
      .atHour(17)
      .everyDays(1)
      .inTimezone('Asia/Saigon')
      .create();
    // Trigger recordValues() function every weekday at 19:00 timezone Saigon.
    ScriptApp.newTrigger('recordValues')
      .forSpreadsheet('put_your_spreadsheet_id_here')
      .timeBased()
      .onWeekDay(weekDays[i])
      .atHour(19)
      .everyDays(1)
      .inTimezone('Asia/Saigon')
      .create();
  }
}
```