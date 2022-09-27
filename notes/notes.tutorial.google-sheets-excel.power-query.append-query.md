---
id: ys23TKHpuUryk5g4eXqaV
title: Append Query
desc: ''
updated: 1639454142919
created: 1639453832392
---
# Append query
ref: [Microsoft | Append queries](https://docs.microsoft.com/en-us/power-query/append-queries)

The append operation creates a single table by adding the contents of one or more tables to another, and aggregates the column headers from the tables to create the schema for the new table  
![append-diagram](https://docs.microsoft.com/en-us/power-query/images/append-queries-diagram.png){max-width: 300px, display: block, margin: 0 auto}

The append operation requires at least two tables.  
![append-operation](https://docs.microsoft.com/en-us/power-query/images/me-append-queries-sample-three-more-tables-window.png){max-width: 300px, display: block, margin: 0 auto}

Power Query performs the append operation based on the names of the column headers found on both tables, and not based on their relative position in the headers sections of their respective tables. The final table will have all columns from all tables appended.

In the event that one table doesn't have columns found in another table, null values will appear in the corresponding column