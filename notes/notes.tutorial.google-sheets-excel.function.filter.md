---
id: 64j50kfic6d4w2ijv5zhd49
title: FILTER function
desc: ''
updated: 1653347264637
created: 1653346739230
---
# FILTER function

## Google Sheets

- [Docs](https://support.google.com/docs/answer/3093197?hl=en)
- Usage: Returns a filtered version of the source range, returning only rows or columns that meet the specified conditions.
- Syntax
    - `FILTER(range, condition1, [condition2, ...])`
        - `range` - The data to be filtered
        - `condition1` - A column or row containing `TRUE` or `FALSE` values corresponding to the first column or row of `range`, or an array formula evaluating to `TRUE` or `FALSE`
        - `condition2` ... - [ OPTIONAL ] - Additional rows or columns containing boolean values `TRUE` or `FALSE` indicating whether the corresponding row or column in `range` should pass through `FILTER`. Can also contain array formula expressions which evaluate to such rows or columns. All conditions must be of the same type (row or column). Mixing row conditions and column conditions is not permitted
        - `condition` arguments must have exactly the same length as `range`.
- Notes
    - `FILTER` can only be used to filter rows or columns at one time. In order to filter both rows and columns, use the return value of one `FILTER` function as `range` in another
    - If `FILTER` finds no values which satisfy the provided conditions, `#N/A` will be returned.

## My usage

![[notes.tutorial.google-sheets-excel.function.filter.usage#usage,1]]

## Related