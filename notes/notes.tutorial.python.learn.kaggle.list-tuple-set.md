---
id: V4zWfFYNzVCL2G7eVaO4f
title: List Tuple Set
desc: ''
updated: 1653435881408
created: 1628382303456
---
# The differences b/w list vs tuple vs set

All are used to store multiple items in a single variable.

## List
```python
mylist = ["apple", "banana", "cherry"]
```
- Created using square brackets
- List items are ordered, changeable, and allow duplicate values.
- List items are indexed, the first item has index `[0]`

### [List Slicing](https://www.learnbyexample.org/python-list-slicing/)
- To access a range of items in a list, you need to slice a list. One way to do this is to use the simple slicing operator `:`
- Syntax
    - ![list-slicing](https://www.learnbyexample.org/wp-content/uploads/python/Python-List-Slicing-Syntax.png){max-width: 300px, display: block, margin: 0 auto}
- Example 1:
    - ```python
      L = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i']
      print(L[2:7])
      ```
    - ![list-slicing-example-1](https://www.learnbyexample.org/wp-content/uploads/python/Python-List-Slicing-Illustration.png){max-width: 300px, display: block, margin: 0 auto}
    - Note that the item at index 7 (the upper limit) 'h' is not included.
- Example 2:
    - Slice with Negative Indices
    - ```python
      L = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i']
      print(L[-7:-2])
      ```
    - ![list-slicing-example-2](https://www.learnbyexample.org/wp-content/uploads/python/Python-List-Slicing-Negative-Indices.png){max-width: 300px, display: block, margin: 0 auto}
- Example 3:
    - Slice with Positive & Negative Indices
    - ```python
      L = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i']
      print(L[2:-5])
      # Prints ['c', 'd']
      ```
- Example 4:
    - Specify Step of the Slicing
    - ```python
      # Return every 2nd item between position 2 to 7
      L = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i']
      print(L[2:7:2])
      # Prints ['c', 'e', 'g']
      ```
    - ![list-slicing-example-4](https://www.learnbyexample.org/wp-content/uploads/python/Python-List-Slicing-Specifying-Step-Size.png){max-width: 300px, display: block, margin: 0 auto}
- Example 5:
    - Clone or Copy a List
    - ```python
      L1 = ['a', 'b', 'c', 'd', 'e']
      L2 = L1[:]
      print(L2)
      # Prints ['a', 'b', 'c', 'd', 'e']
      print(L2 is L1)
      # Prints False
      ```
    - When you execute new_List = old_List, you don’t actually have two lists. The assignment just copies the reference to the list, not the actual list
    - You can use slicing operator `:` to actually copy the list (also known as a shallow copy)


## Tuple
```python
mytuple = ("apple", "banana", "cherry")
```
- Created using round brackets
- Tuple items are ordered, unchangeable, and allow duplicate values

## Set
```python
myset = {"apple", "banana", "cherry"}
```
- Created using curly brackets
- Set items are unordered, unchangeable, and do not allow duplicate values
