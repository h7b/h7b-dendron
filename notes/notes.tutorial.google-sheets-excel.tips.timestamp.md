---
id: dsytk0teua0kjns6tdcpj4j
title: Timestamp
desc: Timestamp in Google Sheets
updated: 1662512150068
created: 1662508256719
---
# Timestamp in Google Sheets

ref: [tillerhq](https://www.tillerhq.com/timestamp-google-sheets/)

How to use timestamps in Google Sheets to record when data is created or deleted and keep your spreadsheets organized.

## Manually add timestamp

Use keyboard shortcuts: `CTRL + ALT + SHIFT + ;`

You can also use built-in formula: [NOW](https://support.google.com/docs/answer/3092981?hl=en)

## Automatically timestamp cells

### Using the IFS function

- enable the "iterative calculation" in "Spreadsheet Settings"

![iterative-calculation](https://tillerhq.com/wp-content/uploads/2021/09/ScreenShot2021-09-07at10_19_37PM_bbe8aba9dc3b1190d8732ab450c7cae4_800.png){max-width: 300px, display: block, margin: 0 auto}

- Enter the following formula in the first cell of the timestamp column, where
    - A2 is the first cell of the column you want to insert information in 
    - B2 is the first cell of the timestamp column

```javascript
=IFS(A2="","",B2="",NOW(),TRUE,B2)
```

- [Clip with step-by-step explanation](https://www.youtube.com/watch?v=bU0z_6gxI98) by "Learn Google Sheets".

![ifs-formula](https://tillerhq.com/wp-content/uploads/2021/09/ScreenShot2021-09-07at10_45_49PM_64eea3a1f175d13f1ccdde07a1f1ba24_800.png){max-width: 300px, display: block, margin: 0 auto}

- Expected result:
    - The timestamp cell will remain blank unless something is entered into the Activity cell next to it
    - Every time you type something in the Activity column, a timestamp will appear in the cell next to it, which will remain static after the first time information is entered into it, and will not change even if you proceed to make changes to it at a later time

### Using custom Google Apps Script

- Open "Script Editor"

![script-editor-1](https://tillerhq.com/wp-content/uploads/2021/09/ScreenShot2021-09-07at11_49_56PM_6c427861559ba71ec5516b4aedb8dd99_800.png){max-width: 300px, display: block, margin: 0 auto}

- Version 1: paste this [gs_timestamp_v1 code snippet](https://gist.github.com/h7b/9334af49ea6c4ee0f00da4158f5f8213#file-gs_timestamp_v1-gs) into "Script Editor"
    - Expected behavior: Every time you type something in the spreadsheet, a timestamp will automatically appear in the cell next to it.

![script-editor-2](https://tillerhq.com/wp-content/uploads/2021/09/ScreenShot2021-09-07at11_53_31PM_8735919567c89ca9d1725cf72fabeeb9_800.png){max-width: 300px, display: block, margin: 0 auto}

- Version 2: paste this [gs_timestamp_v2 code snippet](https://gist.github.com/h7b/9334af49ea6c4ee0f00da4158f5f8213#file-gs_timestamp_v2-gs) into "Script Editor"
    - Expected behavior: Every time you type something in the column A, a timestamp for "created_at" will automatically appear in the column C, a timestamp for "modified_at" will automatically appear in the column D
    - Source: [Google Sheets - Add Timestamp When Cell Changes - Apps Script](https://www.youtube.com/watch?v=548dD3iXetg) by "Learn Google Sheets" with step-by-step explanation in video.

![script-editor-3](https://ik.imagekit.io/casa/h7b-dendron/google_sheets__add_timest_time_707_5b50NgMJX.png?ik-sdk-version=javascript-1.4.3&updatedAt=1662510584397){max-width: 300px, display: block, margin: 0 auto}

## Related

- [danwin | How to automatically timestamp a new row in Google Sheets using Apps Script](http://blog.danwin.com/how-to-automatically-timestamp-a-new-row-in-google-sheets-using-apps-script/)