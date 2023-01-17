---
id: no5qlp4pwotcrz5weaavkkz
title: Triggers in Google Sheets
desc: 'Triggers in Google Sheets'
updated: 1673934314904
created: 1673879371252
---
# Triggers in Google Sheets

ref: [spreadsheet.dev](https://spreadsheet.dev/triggers-in-google-sheets)

Triggers are a feature in Google Apps Script and they enable you to automate your tasks and workflows in Google Sheets.

## How triggers work?

Example:
- You enter all the birthdays you want to remember into a spreadsheet and then use a trigger to check it every morning at 6AM and send you an email if it is someone's birthday.
- From a technical standpoint what is happening is that the trigger causes a Google Apps Script function to run every morning and this function reads the birthdays from the spreadsheet and sends you an email if that day happens to be someone's birthday.

![trigger](https://www.googleapis.com/download/storage/v1/b/spreadsheetdev-content/o/spreadsheetdev%2F11b0mv6Z8Tw2Kk10tNZF3kRbMW6u66CzD84jtczsVo88%2F5312.png?generation=1587262943177440&alt=media){max-width: 300px, display: block, margin: 0 auto}

## Types of triggers

There are two types of triggers in Google Sheets
- Time-driven triggers
- Spreadsheet triggers

### Time-driven triggers

Use Time-driven triggers to run a function in your script periodically OR at a specific date and time in the future.

There are six types of Time-based triggers
- Specific date and time
- Minutes timer: run a function in your script every minute or once every N minutes
- Hour timer
- Day timer
- Week timer
- Month timer

### Spreadsheet triggers

Use Spreadsheet triggers to run a function in your script whenever something changes in your spreadsheet.

There are two kinds of Spreadsheet triggers: Simple triggers and Installable triggers.

[Simple triggers](https://developers.google.com/apps-script/guides/triggers):
- do not need user authorization
- Google [restricts what scripts can do](https://developers.google.com/apps-script/guides/triggers#restrictions) when they are run by these triggers

[Installable triggers](https://developers.google.com/apps-script/guides/triggers/installable):
- can access user data but they must be authorized by the user
- There are five types of events that you can use in a Spreadsheet trigger
    - Open: trigger to run a function in your script when the spreadsheet is opened
    - Edit: whenever one or more cells in your spreadsheet are edited
    - Change: whenever the structure of your spreadsheet changes
    - Form Submit: whenever a user submits a Form that is linked to your spreadsheet
    - Selection change: whenever the user selects a new range in your spreadsheet

| Trigger event | Can it be used as a simple trigger? | Can it be used as an installable trigger? |
|---|---|---|
| Open | Yes | Yes |
| Edit | Yes | Yes |
| Change | No | Yes |
| Form Submit | No | Yes |
| Selection change | Yes | No |

## How to create a trigger?

A `simple trigger` can only be created programmatically with the [Script service](https://developers.google.com/apps-script/reference/script), whereas an `installable trigger` can be created manually via a [UI page](https://script.google.com/) or programmatically using Apps Script.
- via UI. Example: ![trigger-ui](https://www.googleapis.com/download/storage/v1/b/spreadsheetdev-content/o/spreadsheetdev%2F11b0mv6Z8Tw2Kk10tNZF3kRbMW6u66CzD84jtczsVo88%2F9157.png?generation=1587262969972447&alt=media){max-width: 300px, display: block, margin: 0 auto}
- using code. Example:
    ```javascript
    function createOnEditTrigger() {
      ScriptApp.newTrigger("sendEmailReport") // Run the sendEmailReport function.
        .forSpreadsheet(SpreadsheetApp.getActive()) // Create the trigger in this spreadsheet.
        .onEdit() // We want to set up an Edit trigger.
        .create(); // Create it!
    }
    ```

## How to modify/delete a trigger?

ref: [google](https://developers.google.com/apps-script/guides/triggers/installable#managing_triggers_programmatically)

Simple triggers like `onOpen()` can't be deactivated manually from this [UI page](https://script.google.com/); instead, you must edit the appropriate script and remove or rename the `onOpen()` function.

An existing installable trigger can be modified programmatically by deleting it and create a new one, OR deactivated manually via the [UI page](https://script.google.com/).

An example of code to delete a trigger via ID
```javascript
/**
 * Deletes a trigger.
 * @param {string} triggerId The Trigger ID.
 * @see https://developers.google.com/apps-script/guides/triggers/installable
 */
function deleteTrigger(triggerId) {
  // Loop over all triggers.
  const allTriggers = ScriptApp.getProjectTriggers();
  for (let index = 0; index < allTriggers.length; index++) {
    // If the current trigger is the correct one, delete it.
    if (allTriggers[index].getUniqueId() === triggerId) {
      ScriptApp.deleteTrigger(allTriggers[index]);
      break;
    }
  }
}
```

## Related

- [spreadsheet.dev | Create triggers programmatically using Apps Script](https://spreadsheet.dev/create-triggers-programmatically-using-apps-script)