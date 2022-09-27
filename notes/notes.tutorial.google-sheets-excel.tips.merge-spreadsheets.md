---
id: kMyz5gwL4xY8buPuxnEa1
title: Merge Spreadsheets
desc: ''
updated: 1653345395374
created: 1639180793342
---
# How to combine / consolidate multiple spreadsheets

## Two types of combination

Append  
Three spreadsheets are appended into one based on column names
![append](https://miro.medium.com/max/875/1*Nz9XJR5wXwvqom3magTY3g.png){max-width: 300px, display: block, margin: 0 auto}

Join / Merge  
Similar to [[SQL Join|notes.tutorial.sql.sql-join]], two spreadsheets are joined into one based on the same `Name` values
![join](https://miro.medium.com/max/528/1*_ISxVeW0kMDqfvUpcYGFBg.png){max-width: 300px, display: block, margin: 0 auto}

## Use [[Power Query|notes.tutorial.google-sheets-excel.power-query]] in Microsoft Excel

Some easy-to-follow tutorials to combine tables:
- [[Merge tables|notes.tutorial.google-sheets-excel.power-query.merge-query]]
- [[Append tables|notes.tutorial.google-sheets-excel.power-query.append-query]]
- [[Combine files|notes.tutorial.google-sheets-excel.power-query.combine-files]]
- [Xelplus](https://www.xelplus.com/combine-excel-sheets-power-query/)
- [TrumpExcel](https://trumpexcel.com/merge-tables/)
- [Access Analytic | Youtube](https://www.youtube.com/watch?v=cPN24NK3_68)

Thoughts:
- My favorite method
- Since most of white-collar worker have license of Microsoft 365, this method is free and also easy to use
- Is applicable for both `Join` or `Append` type

## Use function in Google Sheets
ref: [Learn Google Spreadsheets | Combine Multiple Google Sheets (Workbooks) to Master Data File](https://www.youtube.com/watch?v=qsqjUxBcgAs)

Append multiple spreadsheet by combinining [IMPORTRANGE](https://support.google.com/docs/answer/3093340?hl=en) functions into an `array`  
```javascript
{
    IMPORTRANGE();
    IMPORTRANGE();
    IMPORTRANGE()
    }
```

Append only records which is non-blank in column A (1st column), using [[QUERY function|notes.tutorial.google-sheets-excel.function.query]]
```javascript
=QUERY({
    IMPORTRANGE();
    IMPORTRANGE();
    IMPORTRANGE();
    },
    "SELECT * WHERE Col1 is not null",
    [optional_header_param]
    )
```

Append only records which is non blank in column A, using [FILTER](https://support.google.com/docs/answer/3093197?hl=en) function  
```javascript
={
    FILTER(IMPORTRANGE(sheet1_id,"data!A1:G"),IMPORTRANGE(data!A1:A)<>"");
    FILTER(IMPORTRANGE(sheet2_id,"data!A1:G"),IMPORTRANGE(data!A1:A)<>"");
    FILTER(IMPORTRANGE(sheet3_id,"data!A1:G"),IMPORTRANGE(data!A1:A)<>"")
}
```

## Use KNIME Analytics Platform
ref: [NickyDee | Youtube](https://www.youtube.com/watch?v=KspVX4DF0-I), [KNIMETV | Youtube](https://www.youtube.com/watch?v=9uV99ByH-TA)

Download [KINIME Analytics Platform](https://www.knime.com/?) and do join operation.

Thoughts: 
- This tool is free to use locally
- Not simple and intuitive to use like Power Query. Knime also has more features than [Mito](https://trymito.io/).
- This platform could be considered as an alternative of [Alteryx](https://www.alteryx.com/)

## Use Mito to generate Python script
ref: [Mito | Merging Datasets Together](https://docs.trymito.io/how-to/merging-datasets-together), [Mito | Youtube](https://www.youtube.com/watch?v=H6VAG-CrHZI)

Instead of writing custom Python script, I can use [Mito](https://trymito.io/) to generate a standardized Python code to do the merge.

Thoughts:
- [Pricing plan](https://trymito.io/plans) starts at USD 10/month. However, it's free to use on local machine.
- Simpler than writing my own Python script
- Currently Mito only works as a spreadsheet extension to the JupyterLab notebook
- [[Installing Mito|notes.tutorial.python.packages.mito#getting-started-with-mito]] is not complicated but it's quite daunting for users who may not be familiar with codings

## Use Python script
ref: [Love Spreadsheets | Medium](https://lovespreadsheets.medium.com/merging-spreadsheets-with-python-append-591d599d49da)

Clone this [gist](https://gist.github.com/asharma327/b76258558f3a8394637ad4949321bf9b#file-append-py) to practice `Append`-type join.

ref: [Python In Office](https://pythoninoffice.com/merge-multiple-excel-files-in-python/)

Or Read this [tutorial](https://pythoninoffice.com/merge-multiple-excel-files-in-python/) to practice `Merge`

## My least favorite would be paid services

### [Merge Spreadsheets](https://www.mergespreadsheets.com/)  
ref: 
- [Merge Spreadsheets | How to Combine Excel Files](https://www.mergespreadsheets.com/guides/combine-excel-files.html)
- [Merge Spreadsheets | A Better Alternative to Vlookup & Index Match](https://www.mergespreadsheets.com/guides/mergespreadsheets-vlookup-indexmatch.html)
- [Love Spreadsheets | Youtube](https://www.youtube.com/watch?v=lEk83SczW7U)

![demo-paid-service](https://project-static-assets.s3.amazonaws.com/MergeSpreadsheets/mergeStep3.png){max-width: 300px, display: block, margin: 0 auto}

Thoughts:
- [Pricing plan](https://www.mergespreadsheets.com/pricing) starts at USD 4/month. Limited free tier, with file size at 1 MB max, 1 merge every 1 hour.
- another simple approach to manually merge workbooks

### [Sheetgo](https://www.sheetgo.com/)
ref: [Sheetgo | Youtube](https://www.youtube.com/watch?v=F8U7Mq5skoE)

Thoughts:
- [Pricing plan](https://www.sheetgo.com/pricing/) starts at USD 26.7/month. Limited free tier, but enough for individual use
- Can be used with both Google Sheets and Excel
- Sheetgo is implemented as an workflow inside spreadsheet, so it can be updated automatically too.
- More complicated than [Merge Spreadsheets](https://www.mergespreadsheets.com/)
