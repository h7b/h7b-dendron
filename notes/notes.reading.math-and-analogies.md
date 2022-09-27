---
id: zprqro38f1hwut6pkxcddxx
title: Math and Analogies
desc: ''
updated: 1649111764925
created: 1649111764925
---
# Reading 2022-04-05

## Metadata

- Ref:: [Better Explained](https://betterexplained.com/articles/math-and-analogies/)
- Title:: Math and Analogies
- Author:: Kalid Azad
- Year of publication:: 2019
- Category:: Blog
- Topic:: 
- Related:: 
    - [Rethinking Arithmetic: A Visual Guide](https://betterexplained.com/articles/rethinking-arithmetic-a-visual-guide/)
    - [A Visual, Intuitive Guide to Imaginary Numbers](https://betterexplained.com/articles/a-visual-intuitive-guide-to-imaginary-numbers/)
    - [Understanding Why Complex Multiplication Works](https://betterexplained.com/articles/understanding-why-complex-multiplication-works/)

## Notes from reading

Using the symbol `0` to represent nothingness is a really weird concept. And when you've tied your concept of a number to physical items, concepts like zero become difficult. How about this negative number? What's less than nothing? What's a negative rock?

It took a few thousand years to accept this new feature — negative numbers were still controversial in the 1700s! Negatives aren’t something we can touch or hold, but they describe certain relationships well (like debt). It was a useful fiction.

An idea: numbers are 2D directions

![number-lines](https://betterexplained.com/wp-content/uploads/math-analogies/math-analogies-jpg.015.jpeg){max-width: 300px, display: block, margin: 0 auto}

The imaginary dimension lets us get to negatives in two steps. Saying *"i squared is negative one"* is really saying: I'm starting at 1. We multiply by i, multiply by i again, and get to -1. So i represents a 90-degree rotation, and rotating twice points you backwards. That's what *"i squared equals -1"* means.

![complex-number](https://betterexplained.com/wp-content/webp-express/webp-images/uploads/complex/a_plus_bi.png.webp){max-width: 300px, display: block, margin: 0 auto}

what multiplication of two complex numbers does:
- Regular multiplication (*"times 2"*) scales up a number (makes it larger or smaller)
- Imaginary multiplication (*"times i"*) rotates you by 90 degrees

![multiplication-complex-number](https://betterexplained.com/wp-content/webp-express/webp-images/uploads/complex_multiplication/complex-table-rules.png.webp){max-width: 300px, display: block, margin: 0 auto}

Multiplying by `(2 + i)` means *double your number and add in a perpendicular rotation*

What about visualizing the multiplication of two complex numbers ("triangles"), like $(3+4i).(2+3i)$. I see this as: *Make a scaled version of our original triangle (times 2) and add a scaled/rotated triangle (times 3i)*

![multiplication-complex-number-1](https://betterexplained.com/wp-content/webp-express/webp-images/uploads/complex_multiplication/complex-multiplication-1.png.webp){max-width: 300px, display: block, margin: 0 auto}

Let’s take a look. Suppose I’m on a boat, with a heading of 3 units East for every 4 units North. I want to change my heading 45 degrees counter-clockwise. What’s the new heading?

![apply-complex-number](https://betterexplained.com/wp-content/webp-express/webp-images/uploads/complex/imaginary_example2.png.webp){max-width: 300px, display: block, margin: 0 auto}

An approach by complex number: 
- We’re on a heading: 3 units East, 4 units North = $3 + 4i$
- we want to rotate counter-clockwise by 45 degrees = multiply by $1 + i$
- We noticed that 45 degrees is $1 + i$ (perfect diagonal), so we can multiply by that amount

By multiplying together:
$$(3+4i).(1+i)=3+3i+4i+4i^2=-1+7i$$

So our new orientation is 1 unit West (-1 East), and 7 units North