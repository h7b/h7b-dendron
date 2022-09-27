---
id: 6rqb1ZRRrep7N7taDmmKc
title: Date Time Table
desc: Create Date Time table as a dimension in data model
updated: 1663193162429
created: 1640233847463
---
# Create Date Time table as a dimension in data model

ref: [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=1243), [ExcelIsFun | pdf notes](https://people.highline.edu/mgirvin/AllClasses/348/MSPTDA/Content/PowerBIDesktop/016and017-MSPTDA-IntoductionPowerBIDesktop.pdf), [Microsoft | Create date tables in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/guidance/model-date-tables), 

In Power BI Desktop, there is a feature called [Auto date/time](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-auto-date-time) to support convenient time intelligence reporting based on date columns loaded into a model
![auto-date-time](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-auto-date-time/auto-date-time-hidden-table-example-rows.png){max-width: 300px, display: block, margin: 0 auto}

However, `Auto date/time` tables are permanently hidden, even from modelers. They cannot be seen in the Fields pane or the Model view diagram, and its rows cannot be seen in Data view. Also, the table and its column cannot be directly referenced by DAX expressions

Hence, if we need more date/time measures, we can disable the `Auto date/time` for our specific file, and create manually a new helper table of `Date` dimension using [CALENDAR](https://docs.microsoft.com/en-us/dax/calendar-function-dax) DAX function

A `Date Dimension Table` help us to evaluate Time Intelligence Analysis, which should contain
- every possible day for every given year in the Date
Column in the Fact Table
- Month, MonthNumber, Year, Quarter
- Fiscal Quarter / Year / Period

![date-table](https://i.imgur.com/abhNJXE.jpg){max-width: 300px, display: block, margin: 0 auto}

[23:54](https://youtu.be/nBu1Bqa1jjs?t=1432) DAX custom date table

```dax
dDate = CALENDAR(DATE(YEAR(MIN(fTable[Date])),1,1), DATE(YEAR(MIN(fTable[Date])),12,31))
```

## Date table for Power BI using Power Query M code

ref: [How to Power BI](https://www.youtube.com/watch?v=MhC4zj2byBQ)

The code of query is accessible at this [gist](https://gist.github.com/h7b/83bcdcbb255df18b583e6c8af26ec2cb#file-ddate_powerquery_v1).

The query creates a `dDate` table, which consists of: date, day, day number, month, month number, quarter, quarter number, week of year, year.

## Adding Workday And Weekend Numbers Into Your Date Table

ref: [enterprisedna](https://blog.enterprisedna.co/placing-workday-and-weekend-day-numbers-into-the-date-table-in-power-bi/)

![add-day-type](https://i0.wp.com/blog.enterprisedna.co/wp-content/uploads/2020/04/4-9.png?w=1155&ssl=1){max-width: 300px, display: block, margin: 0 auto}

## Build A Comprehensive Date Table In Power BI

ref: [enterprisedna](https://blog.enterprisedna.co/how-to-create-a-detailed-date-table-in-power-bi-fast/)

This version added fiscal year into Date table.

The code of query is accessible at this [gist](https://gist.github.com/h7b/83bcdcbb255df18b583e6c8af26ec2cb#file-ddate_powerquery_v3).

![add-fiscal-year](https://i0.wp.com/blog.enterprisedna.co/wp-content/uploads/2019/08/reviewing-7-FY.png?w=688&ssl=1){max-width: 300px, display: block, margin: 0 auto}

## Related

- [[notes.tutorial.power-bi.guides.custom-dim-table]]
- [BI Gorilla | Create Date Table or Calendar in Power Query M](https://gorilla.bi/power-query/date-table/)
    - The code of query is accessible at this [gist](https://gist.github.com/h7b/83bcdcbb255df18b583e6c8af26ec2cb#file-ddate_powerquery_v2)
    - This version added a dynamic current year to Date table