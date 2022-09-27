---
id: JGcQFbwcoemTQGc2dZhtF
title: Pivot Columns
desc: ''
updated: 1639455201667
created: 1639454635723
---
# Pivot and Unpivot columns

## Pivot columns
ref: [Microsoft | Pivot](https://docs.microsoft.com/en-us/power-query/pivot-columns)

In Power Query, you can create a table that contains an aggregate value for each unique value in a column. Power Query groups each unique value, does an aggregate calculation for each value, and pivots the column into a new table.  
![pivot-diagram](https://docs.microsoft.com/en-us/power-query/images/pivot-operation-diagram.png){max-width: 300px, display: block, margin: 0 auto}

You can pivot columns without aggregating when you're working with columns that can't be aggregated, or aggregation isn't required for what you're trying to do. Example  
![pivot-not-aggregated](https://docs.microsoft.com/en-us/power-query/images/me-pivot-columns-da-pivot-icon.png){max-width: 300px, display: block, margin: 0 auto}

## Unpivot columns
ref: [Microsoft | Unpivot](https://docs.microsoft.com/en-us/power-query/unpivot-column)

In Power Query, you can transform columns into attribute-value pairs, where columns become rows.  
![unpivot-diagram](https://docs.microsoft.com/en-us/power-query/images/unpivot-operation-diagram.png){max-width: 300px, display: block, margin: 0 auto}

You can also select the columns that you don't want to unpivot and unpivot the rest of the columns in the table. This transformation is crucial for queries that have an unknown number of columns. The operation will unpivot all columns from your table except the ones that you've selected.


