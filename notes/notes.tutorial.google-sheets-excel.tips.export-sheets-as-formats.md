---
id: bpkccrkje6xavrhca8c034y
title: Export Sheets as Formats
desc: ''
updated: 1673871403949
created: 1673870851890
---
# Export a Google Sheets spreadsheet into other file formats

ref: [spreadsheet.dev](https://spreadsheet.dev/comprehensive-guide-export-google-sheets-to-pdf-excel-csv-apps-script)

Export a Google Sheets spreadsheet into other file formats (pdf, csv, xls, html)

## Export a Google Sheet using Apps Script

[getblob()](https://developers.google.com/apps-script/reference/drive/file#getblob) method: Return the data inside this object as a blob.

What is a blob?
- A blob is a data interchange format in Apps Script. It is a mechanism to store and transmit data across Apps Script APIs.

Example of a custom function `getFileAsBlob()` takes the URL as input and returns the file as a blob. Then you can rename the exported file, save to Google Drive, send as email attachment.
```javascript
function getFileAsBlob(exportUrl) {
 let response = UrlFetchApp.fetch(exportUrl, {
     muteHttpExceptions: true,
     headers: {
       Authorization: 'Bearer ' +  ScriptApp.getOAuthToken(),
     },
   });
 return response.getBlob();
}
```