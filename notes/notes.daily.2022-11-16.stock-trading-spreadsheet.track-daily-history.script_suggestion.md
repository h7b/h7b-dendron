---
id: wiokgdttlj7kgcw687rwwna
title: Script from others
desc: ''
updated: 1672795409381
created: 1672718255723
---
# Script from others

## Force refereshing IMPORTXML

ref: [reddit](https://www.reddit.com/r/googlesheets/comments/y9tmrb/automatically_update_importxml_without_opening/)

reddit suggestion

```javascript
function refreshXML(){
  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const sheet = ss.getSheetByName("tmp_currentPrice"); // choose the Sheet Name which contains the XML formulaIs
  const range = sheet.getRange("A1");
  const formula = range.getFormula();

  range.clearContent();
  SpreadsheetApp.flush();

  range.setFormula(formula);
  SpreadsheetApp.flush();
}
```

chatgpt suggestion

```javascript
function refreshImportXml() {
  // Get the sheet that contains the IMPORTXML formula
  const sheet = SpreadsheetApp.getActiveSheet();

  // Get the range of cells that contain the IMPORTXML formula
  const range = sheet.getRange("A1:A10");

  // Get the values of the range
  const values = range.getValues();

  // Loop through the values and refresh the IMPORTXML formula for each cell
  for (let i = 0; i < values.length; i++) {
    for (let j = 0; j < values[i].length; j++) {
      if (values[i][j].startsWith("=IMPORTXML")) {
        range.setFormula(values[i][j]);
      }
    }
  }
}
```

You can set a trigger to refresh every day

## Capture daily history of values

Q: How to automatically record a daily history of values of a spreadsheet using apps script? What if I want to catch the values at the end of day only, but not `onEdit` event?

Answer by chatGPT:

```javascript
function recordValues() {
  // Get the sheet that you want to record the values of
  const sheet = SpreadsheetApp.getActiveSheet();

  // Get the values of the sheet
  const values = sheet.getValues();

  // Create a new sheet for the daily history
  const historySheet = SpreadsheetApp.create("History");

  // Append the values to the history sheet
  historySheet.appendRow([new Date(), values]);
}
```

This code will create a new sheet for the daily history every time the function is run, and append the values of the sheet that you specified to the history sheet. The values will be appended as a new row in the history sheet, along with the current date.