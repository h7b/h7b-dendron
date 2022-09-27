---
id: o44RSMA5tlggn30K
title: Fibery Lookup
desc: ''
updated: 1640316191132
created: 1626712219340
---
# Query or Vlookup similar method in Fibery.io

Imagine that I have 2 Types as follows

`Fund Information` Type with 2 fields
- Ticker
- Fund Name

`Fund Metadata` Type with 3 fields
- Ticker
- Type of Metadata
- Meta

`Fund Information` is related to `Fund Metadata` as `1:n`

I want to create a new field in `Fund Information` Type that lookup the content of `Meta` field in `Fund Metadata` Type that satisfies 2 conditions:
- `Fund Information`.`Ticker` is the same as `Fund Metadata`.`Ticker`
- have a specific value in `Type of Metadata` field

A pseudo query of my needs

```sql
SELECT Meta 
FROM Fund_Metadata
WHERE Fund_Metadata.Type_of_Metadata = "my_criteria" 
    AND Ticker = Fund_Metatadata.Ticker
```

Currently, I'm doing a hacky way like this in Fibery.

I create a new formula-type field named `Tmp` in `Fund Information` Type
> [Fund Metadata].Filter(([Type of Metadata].Name = "Auditor") and (Ticker = [Fund Information].Ticker)).Join(Meta,",")

 in order to retrieve the content from `Meta` field in `Fund Metadata` that satisfy my 2 conditions.

 **Update 20210723**: Since I setup the [Fund Metadata].Ticker as merely a lookup field of [Fund Information].Ticker, I can omit its logic check. The formula should be simpler as follows.
 > [Fund Metadata].Filter(([Type of Metadata].Name = "Auditor")).Join(Meta,",")


Up until now, there isn't any proper way (a query-type formula OR a lookup-type field with multiple conditions) to implement this task in Fibery