---
id: Stb8HPlV80D6Xb85
title: Dictionnary
desc: ''
updated: 1639159389738
created: 1627340655243
---
# Dictionaries

Ref: [Kaggle](https://www.kaggle.com/colinmorris/strings-and-dictionaries)

Dictionaries are a built-in Python data structure for mapping keys to values.
```python
numbers = {'one':1, 'two':2, 'three':3}
```
In this case 'one', 'two', and 'three' are the **keys**, and 1, 2 and 3 are their corresponding **values**.

Values are accessed via square bracket syntax similar to indexing into lists and strings.
```python
>>> numbers['one']

1
```
We can use the same syntax to add another key, value pair
```python
>>> numbers['eleven'] = 11
>>> numbers

{'one': 1, 'two': 2, 'three': 3, 'eleven': 11}
```

Or to change the value associated with an existing key
```python
>>> numbers['one'] = 'Pluto'
>>> numbers

{'one': 'Pluto', 'two': 2, 'three': 3, 'eleven': 11}
```

Python has dictionary comprehensions with a syntax similar to the list comprehensions.
```python
>>> planets = ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']
>>> planet_to_initial = {planet: planet[0] for planet in planets}
>>> planet_to_initial

{'Mercury': 'M',
 'Venus': 'V',
 'Earth': 'E',
 'Mars': 'M',
 'Jupiter': 'J',
 'Saturn': 'S',
 'Uranus': 'U',
 'Neptune': 'N'}
```

The `in` operator tells us whether something is a key in the dictionary
```python
>>> 'Saturn' in planet_to_initial
True
>>> 'Betelgeuse' in planet_to_initial
False
```

A for loop over a dictionary will loop over its keys
```python
>>> for k in numbers:
>>>     print("{} = {}".format(k, numbers[k]))

one = Pluto
two = 2
three = 3
eleven = 11
```
