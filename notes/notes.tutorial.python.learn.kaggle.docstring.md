---
id: tztR3njf3mKPkC5p
title: Docstring
desc: ''
updated: 1639159393047
created: 1626889576190
---
# Docstring

When I write a function, I can provide a description in what's called the **docstring**.

The docstring is a triple-quoted string (which may span multiple lines) that comes immediately after the header of a function. 

Example:
```python
def least_difference(a, b, c):
    """Return the smallest difference between any two numbers
    among a, b and c.
    
    >>> least_difference(1, 5, -5)
    4
    """
    diff1 = abs(a - b)
    diff2 = abs(b - c)
    diff3 = abs(a - c)
    return min(diff1, diff2, diff3)
```
When we call `help()` on a function, it shows the docstring.

```python
>>> help(least_difference)

Help on function least_difference in module __main__:

least_difference(a, b, c)
    Return the smallest difference between any two numbers
    among a, b and c.
    
    >>> least_difference(1, 5, -5)
    4
```
