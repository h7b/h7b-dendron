---
id: Oaiww3n9XhhoZAocBjIXZ
title: Power Pivot
desc: ''
updated: 1640400226606
created: 1639506448346
---
# Power Pivot - Data Model in Excel

ref: [goskills](https://www.goskills.com/Excel/Resources/Power-query-vs-power-pivot-power-bi), [The White Pages](https://whitepages.unlimitedviz.com/2021/03/its-time-to-stop-using-power-pivot/), [fluentpro](https://fluentpro.com/blog/difference-between-power-pivot-power-query-and-power-bi), [Microsoft](https://support.microsoft.com/en-us/office/how-power-query-and-power-pivot-work-together-a5f52cba-2150-4fc0-bb8f-b21d69990bc0)

Power Pivot is an in-memory data modeling component that provides highly compressed data storage and extremely fast aggregation and calculation. Power Pivot is used to model your data and perform more complex calculations than Excel can handle.  
![data-model](https://support.content.office.net/en-us/media/9d7ca8cd-ef0b-4e0a-bd0c-7b29ba970a01.png){max-width: 300px, display: block, margin: 0 auto}

Power Pivot is great when working with huge data sets. Once Power Query has imported and cleaned the various data sources, Power Pivot is used to establish relationships between the tables/queries.  
![power-pivot-menu-position](https://cdn2.goskills.com/blobs/blogs/305/241730f9-842a-484b-bd47-67dcc1eeba81.png){max-width: 300px, display: block, margin: 0 auto}

With DAX (Data Analysis Expressions), the formula language of Power Pivot, you can create more powerful calculations and more sophisticated data models than you can in Excel alone.

The Power Pivot window has two views. The Data view looks similar to Excel and enables you to see your data and create calculated columns and measures using DAX formulas.  
![power-pivot-data-view](https://cdn2.goskills.com/blobs/blogs/305/31283917-5cd9-4a01-b775-85c012c96835.png){max-width: 300px, display: block, margin: 0 auto}

And the Diagram view where you can establish the relationships between your tables.  
![power-pivot-diagram-view](https://cdn2.goskills.com/blobs/blogs/305/dc284a0a-bfd0-498d-a691-5213f64c8c4b.png){max-width: 300px, display: block, margin: 0 auto}

The connectors in the `Diagram View` have a "1" on one side, and an "*" on the other. This means that there is a `one-to-many` relationship between the tables, and that determines how the data is used in your PivotTables.

When your model is set up, you can analyze and report on your data using [PivotTables](https://support.microsoft.com/en-us/office/create-a-pivottable-to-analyze-worksheet-data-a9a84538-bfe9-40a9-a8e9-f99134456576)

## Extra readings:

- [Microsoft | memory-efficient Data Model using Excel](https://support.microsoft.com/en-us/office/create-a-memory-efficient-data-model-using-excel-and-the-power-pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)
    - in Microsoft 365, both SharePoint Online and Excel Web App limit the size of an Excel file to 10 MB
    - Data models in Excel use the in-memory analytics engine to store data in memory. On average, you can expect a data model to be 7 to 10 times smaller than the same data at its point of origin
- [Microsoft | columnar databases](https://www.microsoftpressstore.com/articles/article.aspx?p=2449192&seqNum=2)
    - The VertiPaq Engine in DAX. VertiPaq is an in-memory columnar database. Being in-memory means that all of the data handled by a model reside in RAM
    - In a columnar database, data is organized in such a way to optimize vertical scanning. To obtain this result, you need a way to make the different values of a column adjacent one to the other
    ![column-by-column-basis](https://www.microsoftpressstore.com/content/images/chap13_9780735698352/elementLinks/13fig02.jpg){max-width: 300px, display: block, margin: 0 auto}
- [ExcelIsFun | MSPTDA 21 | Youtube](https://www.youtube.com/watch?v=fO_Vymn1e8U)
    - Database takes a table with many columns and stores each column separately as a unique list of values and builds a map to help it reconstruct the table when needed for making DAX Formula calculations.
    - Many calculations can be performed more quickly on individual columns with unique lists of values, rather than making calculation row by row
    - File size is reduced, and when the database is loaded into RAM Memory, less RAM is used, more is left for other tasks
    - This means that for columns with only a few unique values, the file size reduction can be dramatic. (Number of unique items in a column = “Cardinality”).
    ![columnar-database-example-1](https://i.imgur.com/luGk41b.jpg){max-width: 300px, display: block, margin: 0 auto}
    ![columnar-database-example-2](https://i.imgur.com/WfrhEWb.jpg){max-width: 300px, display: block, margin: 0 auto}
- [ExcelIsFun | MSPTDA 14 | Youtube](https://www.youtube.com/watch?v=Nmn6qUJvWWY)
    - Notes in [pdf](https://people.highline.edu/mgirvin/AllClasses/348/MSPTDA/Content/PowerPivot/014-MSPTDA-ColumnarDatabaseNotes-PowerPivotToImportMillions.pdf)
    - Size of Excel file with Data Model imported ~3M rows is quite small, 1.5 MB