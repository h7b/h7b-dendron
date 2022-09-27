---
id: 7hc6JngKcxN5XulRf02oB
title: Pandas
desc: ''
updated: 1653181158495
created: 1643184543645
---
# Learn Pandas

## Creating, Reading and Writing
ref: [kaggle](https://www.kaggle.com/residentmario/creating-reading-and-writing)

[pandas](https://pandas.pydata.org/), open source data analysis and manipulation tool

A DataFrame is a table. It contains an array of individual entries, each of which has a certain value. Each entry corresponds to a row (or record) and a column.

```python
pd.DataFrame({'Yes': [50, 21], 'No': [131, 2]})
```
```
	Yes	No
0	50	131
1	21	2
```

We are using the `pd.DataFrame()` constructor to generate these DataFrame objects

The list of row labels used in a DataFrame is known as an Index. We can assign values to it by using an `index` parameter in our constructor:

```python
pd.DataFrame({'Bob': ['I liked it.', 'It was awful.'], 
              'Sue': ['Pretty good.', 'Bland.']},
             index=['Product A', 'Product B'])
```
```
	        Bob             Sue
Product A	I liked it.     Pretty good.
Product B	It was awful.	Bland.
```

A `Series`, by contrast, is a sequence of data values. If a `DataFrame` is a table, a `Series` is a list.
```python
pd.Series([1, 2, 3, 4, 5])
```

A `Series` is, in essence, a single column of a `DataFrame`. So you can assign column values to the `Series` the same way as before, using an `index` parameter. However, a `Series` does not have a column name, it only has one `overall` name
```python
pd.Series([30, 35, 40], index=['2015 Sales', '2016 Sales', '2017 Sales'], name='Product A')
```

We can use the `shape` attribute to check how large the resulting DataFrame is:
```python
wine_reviews.shape
```
```text
(129971, 14)
```
So our new DataFrame has 130,000 records split across 14 different columns

We can examine the contents of the resultant DataFrame using the `head() `command, which grabs the first five rows:
```python
wine_reviews.head()
```

Use `to_csv` to save a DataFrame to a CSV file
```python
wine_reviews.to_csv("filename.csv")
```

## Indexing, Selecting & Assigning
ref: [kaggle](https://www.kaggle.com/residentmario/indexing-selecting-assigning)
