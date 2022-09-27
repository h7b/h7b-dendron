---
id: OMkfItmAX5Cxf0BN
title: String
desc: ''
updated: 1639159447442
created: 1627340146752
---
# Strings

Ref: [Kaggle](https://www.kaggle.com/colinmorris/strings-and-dictionaries)

strings in Python can be defined using either single or double quotations
- Double quotes are convenient if your string contains a single quote character (e.g. representing an apostrophe).
- Similarly, it's easy to create a string that contains double-quotes if you wrap it in single quotes:
```python
print("Pluto's a planet!")
print('My dog is named "Pluto"')
```
- If we try to put a single quote character inside a single-quoted string, Python gets confused. We can fix this by "escaping" the single quote with a backslash.
```python
print('Pluto\'s a planet!')
```
- A major way in which strings differ from lists is that strings are immutable. We can't modify them.

We call `.format()` on a "format string", where the Python values we want to insert are represented with `{}` placeholders.
```python
>>> "{}, you'll always be the {}th planet to me.".format(planet, position)
"Pluto, you'll always be the 9th planet to me."
```

Going between strings and lists: `.split()` and `.join()`

`str.split()` turns a string into a list of smaller strings, breaking on whitespace by default.
```python
>>> words = claim.split()
>>> words
['Pluto', 'is', 'a', 'planet!']
```

split on something other than whitespace:
```python
datestr = '1956-01-31'
year, month, day = datestr.split('-')
```
`str.join()` takes us in the other direction, sewing a list of strings up into one long string, using the string it was called on as a separator.
```python
>>> '/'.join([month, day, year])
'01/31/1956'
```

## string slices
Ref: [Link](https://developers.google.com/edu/python/strings)
The "slice" syntax is a handy way to refer to sub-parts of sequences -- typically strings and lists. The slice `s[start:end]` is the elements beginning at start and extending up to but not including end. Suppose we have `s = "Hello"`
![img from google](https://developers.google.com/edu/python/images/hello.png)
- s[1:] is 'ello' -- omitting either index defaults to the start or end of the string
- s[1:4] is 'ell' -- chars starting at index 1 and extending up to but not including index 4
- s[:] is 'Hello' -- omitting both always gives us a copy of the whole thing (this is the pythonic way to copy a sequence like a string or list)
- s[:-3] is 'He' -- going up to but not including the last 3 chars.
- s[-3:] is 'llo' -- starting with the 3rd char from the end and extending to the end of the string.

## difference `str.isdigit` vs `str.isnumeric`?
Ref: [Link](https://lerner.co.il/2019/02/17/pythons-str-isdigit-vs-str-isnumeric/)

`str.isdigit` only returns True for strings containing solely the digits 0-9

`str.isnumeric` returns True if it contains any numeric characters (the digits 0-9, plus any character from another language that’s used in place of digits)

```python
>>> '12345'.isdigit()
True

>>> '12345'.isnumeric()
True

>>> '一二三四五'.isdigit()
False

>>> '一二三四五'.isnumeric()
True
```
