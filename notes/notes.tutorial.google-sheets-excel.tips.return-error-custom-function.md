---
id: cwp5hnf081pm3nmg79sznse
title: Return an error from a custom function in Google Sheets
desc: 'Return an error from a custom function in Google Sheets'
updated: 1673867996055
created: 1673867742834
---
# Return an error from a custom function in Google Sheets

ref: [spreadsheet.dev](https://spreadsheet.dev/how-to-return-error-from-custom-function-google-sheets)

How should we deal with invalid user input to custom functions?
- One way would be to return an output that informs the user that the input was invalid. However, with the approach, Google Sheets functions like [ISERROR()](https://support.google.com/docs/answer/3093349?hl=en) will not be able to detect that an error occurred.
- A better approach in these situations is to return an error from the custom function that tells the user why the error occurred, so they can then fix it. Use the `throw` statement to throw errors instead of returning values to communicate that an error occurred.