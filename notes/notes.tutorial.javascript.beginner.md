---
id: l79o0xfy7ck1sog82b8uz3s
title: JavaScript for Beginners
desc: 'JavaScript for Beginners'
updated: 1672532153674
created: 1672015579049
---
# JavaScript for Beginners

## Note from saperis' clip

ref: [saperis](https://www.youtube.com/watch?v=x3xZXJmb05U&list=PLNwCcck1-mNgYUMHlfFYXpMNqfQ9sJsxp)

[01:05](https://youtu.be/x3xZXJmb05U?t=65): assign a variable ![assign-variable](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_65_D5A_GrqlP.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672015915176){max-width: 300px, display: block, margin: 0 auto}

[07:40](https://youtu.be/x3xZXJmb05U?t=460): 3 keywords to declare a variable ![const-let-var](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_460_Wa4YoZmBA.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672015915177){max-width: 300px, display: block, margin: 0 auto}

[00:47](https://youtu.be/ujlnQfd1ams?t=47): function ![function](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_47_eGL6hmlN-.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672014956270){max-width: 300px, display: block, margin: 0 auto}

[00:13](https://youtu.be/w0rdFMPz7mQ?t=13): data type is an attribute of data which tells the compiler or interpreter how the programmer intends to use the data ![data-type](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_75_djVd312fS.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672016373216){max-width: 300px, display: block, margin: 0 auto}

[03:26](https://youtu.be/w0rdFMPz7mQ?t=206): a variable without value is `undefined`. [^1] `Null` means there is intentionally no object ![null](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_206_Wjsr6bwMf.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672016373068){max-width: 300px, display: block, margin: 0 auto}

[^1]: https://developer.mozilla.org/en-US/docs/Glossary/undefined

[00:13](https://youtu.be/cENsx0cbSwc?t=13):  an `object` is a standalone `entity`, with `properties` and `type` ![object](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_13_I7GaTFfVv.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672014956198){max-width: 300px, display: block, margin: 0 auto}

[00:38](https://youtu.be/cENsx0cbSwc?t=38): example: "hotel" object with 3 properties "name", "city", "room" ![object](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_38_bUBgtgwot.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672014956293){max-width: 300px, display: block, margin: 0 auto}

[01:33](https://youtu.be/cENsx0cbSwc?t=93): get access to values in an object by notation `object.property` ![object.property](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_93_9XK-mPfS4.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672014956284){max-width: 300px, display: block, margin: 0 auto}

[01:46](https://youtu.be/cENsx0cbSwc?t=106): 3 different ways to create an object ![create-an-object](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_113_4dPsW-HG2.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672014956327){max-width: 300px, display: block, margin: 0 auto}

[03:40](https://youtu.be/cENsx0cbSwc?t=220): a [method](https://developer.mozilla.org/en-US/docs/Glossary/Method) is a function associated with an object, or put differently, a method is a property of an object that is a function ![method](https://ik.imagekit.io/casa/h7b-dendron/javascript_for_beginners__time_237_QFR2u1Nlb.png?ik-sdk-version=javascript-1.4.3&updatedAt=1672014956269){max-width: 300px, display: block, margin: 0 auto}

## Unsorted notes

[shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) method removes the first element from an array and returns that removed element. This method changes the length of the array.

The [pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) method has similar behavior to `shift()`, but applied to the last element in an array.

The [push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) method adds one or more elements to the end of an array and returns the new length of the array.

[Object-oriented programming (OOP)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_programming) is about modeling a system as a collection of objects, where each object represents some particular aspect of the system. Objects contain both functions (or methods) and data. An object provides a public interface to other code that wants to use it but maintains its own private, internal state; other parts of the system don't have to care about what is going on inside the object.

The value of ["this"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) keyword depends on in which context it appears: function, class, or global.

## Var, Let, and Const – What's the Difference?

ref: [freecodecamp](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/)

### Var

Before the advent of ES6, `var` declarations ruled.

`Scope` essentially means where these variables are available for use. `var` declarations are globally scoped or function/locally scoped.
- The scope is global when a `var` variable is declared outside a function. This means that any variable that is declared with `var` outside a function block is available for use in the whole window.
- `var` is function scoped when it is declared within a function. This means that it is available and can be accessed only within that function.

`var` variables can be re-declared and updated

Problem with var: (read in article)

### Let

`let` is block scoped. A block is a chunk of code bounded by curly braces `{}`.

`let` can be updated but not re-declared.

### Const

Variables declared with the `const` maintain constant values.

`const` declarations are block scoped

`const` cannot be updated or re-declared