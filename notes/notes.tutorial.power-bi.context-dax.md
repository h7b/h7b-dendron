---
id: Er7oNzJ8GUxYfEn8MilnN
title: Context in DAX
desc: ''
updated: 1661643350856
created: 1640236804623
---
# Context in DAX Formulas

ref: [Microsoft | Context in DAX Formulas](https://support.microsoft.com/en-us/office/context-in-dax-formulas-2728fae0-8309-45b6-9d32-1d600440a7ad)

Context is what enables you to perform dynamic analysis with DAX formulas. There are different types of context: row context, query context, and filter context.

## Row Context

Row context can be thought of as "the current row.” If you have created a calculated column, the row context consists of the values in each individual row and values in columns that are related to the current row.

If you create a formula in a calculated column, the row context for that formula includes the values from all columns in the current row. 

If the table is related to another table, the content also includes all the values from that other table that are related to the current row. Row context automatically follows the relationships between tables to determine which rows in related tables are associated with the current row.

This [short clip](https://www.youtube.com/watch?v=JCGoZe24CXc) from "How to Power BI" explain clearly with visuals, the concept of "row context" and "iterator".

### Multiple Row Context (Iterator)

DAX includes functions that iterate calculations over a table. These functions can have multiple current rows and current row contexts. In programming terms, these formulas recurse over a loop.

## Query context

Query context refers to the subset of data that is implicitly retrieved for a formula.

## Filter context

Filter context is added when you specify filter constraints on the set of values allowed in a column or table, by using arguments to a formula. Filter context applies **on top of other contexts**, such as row context or query context.

Filter context describes the filters that are applied during the evaluation of a measure or measure expression.

A clip explaining the concept of filter context in Power BI by [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=2443). I found it's easier to understand.

The row context does not propagate automatically through relationships, whereas the filter context does traverse relationships independently of the DAX code. However, you can control the filter context and its propagation using DAX functions.

## Related resources

- [How to Power BI | ROW CONTEXT & ITERATORS | DAX Essentials 2](https://www.youtube.com/watch?v=JCGoZe24CXc)
    - short, concise
- [Salvatore Cagliari | A hard lesson on Filter Context with Power BI and DAX](https://app.box.com/s/s5toz7ei8uuqcxoirfinm0i3jmiftsly)
- [Microsoft Learn | Modify DAX filter context in Power BI Desktop models](https://docs.microsoft.com/en-us/learn/modules/dax-power-bi-modify-filter/)
- [Microsoft | Context in DAX Formulas](https://support.microsoft.com/en-us/office/context-in-dax-formulas-2728fae0-8309-45b6-9d32-1d600440a7ad)
- [sqlbi | DAX 101: Row context in DAX](https://www.sqlbi.com/articles/row-context-in-dax/)
- [sqlbi | Row Context and Filter Context in DAX](https://www.sqlbi.com/articles/row-context-and-filter-context-in-dax/)
- [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=2443)