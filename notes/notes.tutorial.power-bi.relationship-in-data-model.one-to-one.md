---
id: eCfZNjttZsvxnprfUmnZQ
title: One to One
desc: ''
updated: 1640301369675
created: 1640134058773
---
# One-to-one relationship

ref: [Microsoft](https://docs.microsoft.com/en-us/power-bi/guidance/relationships-one-to-one)

There are two scenarios that involve one-to-one relationships:
- Degenerate dimensions: You can derive a degenerate dimension from a fact-type table.
- Row data spans across tables: A single business entity or subject is loaded as two (or more) model tables, possibly because their data is sourced from different data stores. This scenario can be common for dimension-type tables. For example, master product details are stored in an operational sales system, and supplementary product details are stored in a different source.

## Degenerate dimensions

When columns from a fact-type table are used for filtering or grouping, you can consider making them available in a separate table.

Example: The OrderNumber column stores the order number, and the OrderLineNumber column stores a sequence of lines within the order.

![degenerate-dim-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/relationships-one-to-one/sales-order-rows.png){max-width: 300px, display: block, margin: 0 auto}

In the following model diagram, notice that the order number and order line number columns haven't been loaded to the `Sales` table. Instead, their values were used to create a [surrogate key](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema#surrogate-keys) column named `SalesOrderLineID`. The `Sales Order` table provides a rich experience for report authors with three columns: `Sales Order`, `Sales Order Line`, and `Line Number`. It also includes a hierarchy. These table resources support report designs that need to filter, group by, or drill down through orders and order lines.

![degenerate-dim-2](https://docs.microsoft.com/en-us/power-bi/guidance/media/relationships-one-to-one/sales-order-degenerate.png){max-width: 300px, display: block, margin: 0 auto}

## Row data spans across tables

Example: A one-to-one relationship relates the two SKU columns. The relationship filters in both directions, which is always the case for one-to-one relationships
![data-span-example-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/relationships-one-to-one/product-to-product-category.png){max-width: 300px, display: block, margin: 0 auto}

![data-span-example-2](https://docs.microsoft.com/en-us/power-bi/guidance/media/relationships-one-to-one/product-to-product-category-2.png){max-width: 300px, display: block, margin: 0 auto}

When possible, we recommend you avoid creating one-to-one model relationships when row data spans across model tables. Please consider to consolidate the data into a single model table like what `ExcelIsFun` demonstrated in his [tutorial](https://www.youtube.com/watch?v=iK0uKo2G8tA) to merge 2 fact tables with one-to-one relationship to a single fact table.  
Or Power BI will evaluate the one-to-one model relationship as a [limited relationship](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-relationships-understand#limited-relationships). Therefore, take care to ensure there are matching rows in the related tables, as unmatched rows will be eliminated from query results
