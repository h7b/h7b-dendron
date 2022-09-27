---
id: 1qday0wx7xvy0at6u86x66e
title: 005 NumPy Boolean Arrays
desc: ''
updated: 1653437805836
created: 1653437315571
---
# NumPy Boolean Arrays

(Also called masks)

Link: [NumPy Boolean Arrays](https://www.freecodecamp.org/learn/data-analysis-with-python/data-analysis-with-python-course/numpy-boolean-arrays)

In:
```python
a = np.arange(4)
a
```
Out:
```
array([0, 1, 2, 3])
```
In:
```python
a[[True, False, False, True]]
# choose 1st and 4th item
```
Out:
```
array([0, 3])
```
In:
```python
a >= 2
# compare each element of array a with 2
```
Out:
```
array([False, False,  True,  True])
```
In:
```python
a[a >= 2]
```
Out:
```
array([2, 3])
```