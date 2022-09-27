---
id: 0oaxe59xc2dkpfekkf5mpul
title: 003 NumPy Arrays
desc: ''
updated: 1653437218792
created: 1653437173091
---
# NumPy Arrays

Link: [NumPy Arrays](https://www.freecodecamp.org/learn/data-analysis-with-python/data-analysis-with-python-course/numpy-arrays)

## Indexing and Slicing of Matrices
In:
```python
# Square matrix
A = np.array([
#.   0. 1. 2.
    [1, 2, 3], # 0
    [4, 5, 6], # 1
    [7, 8, 9]  # 2
])
```
In:
```python
A[:, :2] 
# ':' means selecting all rows
# ':2' means selecting up to column 1
```
Out:
```
array([[1, 2],
       [4, 5],
       [7, 8]])
```