---
id: Gk31YsEdjfMJJdLKrqJyJ
title: Parent Child Hierarchy
desc: ''
updated: 1640140070997
created: 1640137147346
---
# Parent-child hierarchies relationship

ref: [Microsoft](https://docs.microsoft.com/en-us/dax/understanding-functions-for-parent-child-hierarchies-in-dax), [DAX Patterns](https://www.daxpatterns.com/parent-child-hierarchies/), [BIccountant](https://www.thebiccountant.com/2017/02/14/dynamically-flatten-parent-child-hierarchies-in-dax-and-powerbi/)

Parent-child hierarchies are often used to represent charts of accounts, stores, salespersons and such. Take example, we can use parent-child hierarchies to show budget, actual and forecast values in a report using both a chart of accounts and a geographic hierarchy.
![example](https://www.daxpatterns.com/daxpatterns/wp-content/uploads/sites/151/2020/07/F-21-03.png){max-width: 300px, display: block, margin: 0 auto}

Since it's not possible to relate a column to a different column in the same table in Microsoft 365, we need to use DAX functions as workaround to achieve achieve this `table self-referencing` concept.

With these functions a user can obtain the entire lineage of parents a row has, how many levels has the lineage to the top parent, who is the parent n-levels above the current row, who is the n-descendant from the top of the current row hierarchy and is certain parent a parent in the current row hierarchy.

The situation: we have input data structure (exported from database).
![input-example](https://www.daxpatterns.com/daxpatterns/wp-content/uploads/sites/151/2020/07/F-21-04.png){max-width: 300px, display: block, margin: 0 auto}
And we need to flatten the hierarchy by converting that structure to this new table, where there is one column for each level of the hierarchy
![output-example](https://www.daxpatterns.com/daxpatterns/wp-content/uploads/sites/151/2020/07/F-21-05.png){max-width: 300px, display: block, margin: 0 auto}

For solution in details, please read the tutorials:
- [DAX Patterns | static depth level](https://www.daxpatterns.com/parent-child-hierarchies/)
- [BIccountant | dynamic depth level](https://www.thebiccountant.com/2017/02/14/dynamically-flatten-parent-child-hierarchies-in-dax-and-powerbi/)
