---
id: 3AVFn8txpRewVX5DvaML2
title: Relationship in Data Model
desc: ''
updated: 1640395929922
created: 1639887641096
---
# What is a Relationship in data model of Microsoft 365 products (PowerPivot, Power BI)

ref:
- [Microsoft | star schema](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema)
- [Microsoft | Model relationships](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-relationships-understand)
- [Microsoft | Create relationships in Diagram View in Power Pivot](https://support.microsoft.com/en-us/office/create-relationships-in-diagram-view-in-power-pivot-12e00cb6-cb4d-469c-97ce-caa08349ad76)
- [SumProduct](https://www.sumproduct.com/blog/article/power-pivot-principles/ppp-creating-relationships)
- [Goodly](https://www.goodly.co.in/create-relationships-power-pivot-power-bi/)
- [radacad](https://radacad.com/basics-of-modeling-in-power-bi-what-is-a-dimension-table-and-why-say-no-to-a-single-big-table)
- [keboola](https://www.keboola.com/blog/star-schema-vs-snowflake-schema)

A relationship is a connection between two tables of data, based on one or more columns in each table
![relationship-table](https://support.content.office.net/en-us/media/dc2ab80d-a5aa-44d6-9f28-36c6493e2856.png){max-width: 300px, display: block, margin: 0 auto}

Relationship purpose: Power BI relationships propagate filters applied on the columns of model tables to other model tables. Filters will propagate so long as there's a relationship path to follow, which can involve propagation to multiple tables.
![relationship-propagation](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-relationships-understand/animation-filter-propagation.gif){max-width: 300px, display: block, margin: 0 auto}

A model relationship relates one column in a table to one column in a different table

Supported relationships in Power BI
- One-to-many (1:*)
- [[One-to-one (1:1)|notes.tutorial.power-bi.relationship-in-data-model.one-to-one]]
- [[Many-to-many (*:*)|notes.tutorial.power-bi.relationship-in-data-model.many-to-many]]

The one to many relationship is the foundation of Power Pivot
- Dimension tables (or Lookup tables): 
    - on the one side of the relationship. 
    - This table keeps descriptive information that can slice and dice the data of the fact table
    - contain a relatively small number of rows
    - support `filtering` and `grouping`
- Fact tables (or Data tables): 
    - on the many side of the relationship. 
    - This table keeps numeric data that might be aggregated in the reporting visualizations
    - contain a very large number of rows and continue to grow over time
    - support `summarization`

## Star schema
Star schema requires modelers to classify their model tables as either `dimension` or `fact`
![star-schema-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/star-schema-example1.png){max-width: 300px, display: block, margin: 0 auto}
Fact Table with most atomic granular data surrounded by Dimension Tables using One-To-Many Relationships
![star-schema-2](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/star-schema-example2.png){max-width: 300px, display: block, margin: 0 auto}

## Snowflake schema
A snowflake schema is very similar to the simple star schema above. The main difference is that snowflake schemas split dimensional tables into further dimensional tables, following `Database Normalization` rules where columns in tables should not have duplicate values and must be broken apart into separate tables.
![snowflake-schema](https://assets.website-files.com/5e6f9b297ef3941db2593ba1/614df5d249f1d56f764083ef_Screenshot%202021-09-24%20at%2017.47.02.png){max-width: 300px, display: block, margin: 0 auto}

## Star vs Snowflake in schema design

| star | snowflake |
|---|---|
| stores redundant data in dimension   tables, or their dimensions are denormalized | Each dimension is split until it is normalized - aka, there is no   redundancy in the dimensional table, no repetition of values |
| A simple star schema leads to simple   query writing | snowflake schemas require a more complex query design |
| Faster query execution time | Slower query execution time |
| Star schemas might run queries faster,   but they require more storage space than snowflake schemas because of their   data redundancy | less diskspace |
| Data integrity is more at risk in star   schemas than snowflake schemas. Because data is stored redundantly, multiple   copies of the same data exist in the star schema’s dimensional tables. This   means new inserts, updates, or deletes can compromise the integrity of data | the snowflake schema is less prone to data integrity issues, because it   fully normalizes dimensional tables, storing dimension data only once in the   appropriate table |

## Star vs Snowflake in Power BI point of view

Generally, the benefits of a single model table outweigh the benefits of multiple model tables.

Consequences when you choose to mimic a snowflake dimension design:

- Power BI loads more tables, which is less efficient from storage and performance perspectives. Because `Columnar Database` will store Dimension Tables with duplicates in an efficient way. No need to complicate model with many tables. Since these tables must include columns to support model relationships, and it can result in a larger model size.
- Longer relationship filter propagation chains will need to be traversed, which will likely be less efficient than filters applied to a single table. According to tests done by `Marco Russo` and `Alberto Ferrari`, for larger models the extra relationships used in a `Snow Flake Schema` can be less efficient than a `single Dimension table` with `Duplicate Values`
- The Fields pane presents more model tables to report authors, which can result in a less intuitive experience, especially when snowflake dimension tables contain just one or two columns.
- It's not possible to create a hierarchy that spans the tables.

## Measure

In star schema design, a `measure` is a fact table column that stores values to be summarized, which is a formula written in [Data Analysis Expressions (DAX)](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-quickstart-learn-dax-basics) that achieves summarization. Measure expressions often leverage DAX aggregation functions like SUM, MIN, MAX, AVERAGE, etc. to produce a scalar value result at query time (values are never stored in the model)
![measure-example](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/field-list-example.png){max-width: 300px, display: block, margin: 0 auto}

## Slowly changing dimensions

A `slowly changing dimension` (SCD) is one that appropriately manages change of dimension members over time. It applies when business entity values change over time, and in an ad hoc manner. A good example of a slowly changing dimension is a customer dimension, specifically its contact detail columns like email address and phone number. In contrast, some dimensions are considered to be rapidly changing when a dimension attribute changes often, like a stock's market price.

Star schema design theory refers to two common SCD types: Type 1 and Type 2
- `Type 1 SCD` always reflects the latest values, and when changes in source data are detected, the dimension table data is overwritten
- `Type 2 SCD` supports versioning of dimension members

![version-hierarchy-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/hierarchy-drill-down.png){max-width: 300px, display: block, margin: 0 auto}

![version-hierarchy-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/hierarchy-drill-down2.png){max-width: 300px, display: block, margin: 0 auto}

## Role-playing dimensions

A role-playing dimension is a dimension that can filter related facts differently. For example, at Adventure Works, the date dimension table has three relationships to the reseller sales facts. The same dimension table can be used to filter the facts by order date, ship date, or delivery date.

The 1st approach is use [USERELATIONSHIP function](https://docs.microsoft.com/en-us/dax/userelationship-function-dax) to choose one active relationship between two Power BI model tables, which leads to the limitation of not possible to simultaneously filter reseller sales by different types of dates
![role-playing-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/relationships.png){max-width: 300px, display: block, margin: 0 auto}

Another 2nd approach is to create a dimension-type table for each role-playing instance, each with a single and active relationship to their respective facts table columns.
![role-playing-2](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/relationships2.png){max-width: 300px, display: block, margin: 0 auto}

## Junk dimensions

The design objective of a junk dimension is to consolidate many "small" dimensions into a single dimension to reduce the model storage size
![junk-dimension](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/junk-dimension.png){max-width: 300px, display: block, margin: 0 auto}

## Cross filter direction

Each model relationship must be defined with a cross filter direction. Your selection determines the direction(s) that filters will propagate. The possible cross filter options are dependent on the cardinality type.

| Cardinality type | Cross filter options |
|---|---|
| One-to-many (or Many-to-one) | Single<br>Both |
| One-to-one | Both |
| Many-to-many | Single (Table1 to Table2)<br>Single (Table2 to Table1)<br>Both |

A relationship that filters in both directions is commonly described as `bi-directional`

Notice that when the cardinality type includes a **one** side, that filters will always propagate from that side

## Relationship evaluation

A Composite model can comprise tables using different storage modes (Import, DirectQuery or Dual), or multiple DirectQuery sources

In this example, the Composite model consists of two source groups: a Vertipaq source group and a DirectQuery source group. The Vertipaq source group contains three tables, and the DirectQuery source group contains two tables. One cross source group relationship exists to relate a table in the Vertipaq source group to a table in the DirectQuery source group.
![composite-model](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-relationships-understand/source-group-example.png){max-width: 300px, display: block, margin: 0 auto}

### Regular relationship

A model relationship is regular when the query engine can determine the "one" side of relationship. It has confirmation that the "one" side column contains unique values. All One-to-many intra source group relationships are regular relationships

In the following example, there are two regular relationships, both marked as R
![regular-relationship](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-relationships-understand/source-group-example-regular.png){max-width: 300px, display: block, margin: 0 auto}

### Limited relationships

A model relationship is limited when there's no guaranteed "one" side. It can be the case for two reasons:
- The relationship uses a Many-to-many cardinality type (even if one or both columns contain unique values)
- The relationship is cross source group
![limited-relationship](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-relationships-understand/source-group-example-limited.png){max-width: 300px, display: block, margin: 0 auto}
