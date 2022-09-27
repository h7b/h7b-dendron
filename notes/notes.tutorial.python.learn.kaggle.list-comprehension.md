---
id: syMjtGBeW1iJtZZm
title: List Comprehension
desc: ''
updated: 1639159428536
created: 1627054389708
---
# List comprehensions

List comprehensions are one of Python's most beloved and unique features. The easiest way to understand them is probably to just look at a few examples:

In:
```python
>>> squares = [n**2 for n in range(10)]
>>> squares

[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

Here's how we would do the same thing without a list comprehension:

```python
squares = []
for n in range(10):
    squares.append(n**2)
squares
```
We can also add an if condition:

```python
short_planets = [planet for planet in planets if len(planet) < 6]
short_planets
```
