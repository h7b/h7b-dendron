---
id: SCwgExPm9TLc6iosSIHkO
title: Comments in JavaScript
desc: ''
updated: 1640702982662
created: 1639011847309
---
# How to Use Comments Efficiently in JavaScript

ref: [Dharmen Shah's Blog](https://blog.shhdharmen.me/comments-usage-and-best-practices-in-javascript), [Bits and Pieces](https://blog.bitsrc.io/best-practices-for-using-comments-in-javascript-4c4cd8619c18)

Single-line Comments
```javascript
let p= 3.14; // The value of Pi (π)
```

Multi-line Comments
```javascript
/**
 * Standard
 * Multi-line
 * Comment
 */
```

Code tells `how` and comments tells `why`  
the code should be able to self-explain how it works, keeping comments to address why it’s there in the first place.  
```javascript
// Do
let p = 3.14; // Rounded value of Pi
let c = 2 * p * 10; // Calculate the circumference of a circle with 

// Don't
let p = 3.14; // Initiate the value of the variable p
let c = 2 * p * 10 // Multiply the value p into 20
```

Avoid Abbreviations

| Short form | Preferred full form           |
|------------|-------------------------------|
| aka        | also known as                 |
| i.e.       | "that is" or "to be specific" |
| e.g.       | for example                   |
| viz.       | "in other words" or "namely"  |

When should I use comments?
- Prefacing
    - Prefacing or explaining the code is one of the main goals of using comments
- For Debugging
    - Since the JavaScript engine does not interpret commented-out codes, we can use comments for debugging purposes
    - if there is an error in your code, you can comment out code lines and re-run the code to see which line is causing the error
- Tagging
    - Most commonly used keywords for tag: `TODO`, `BUG` or `FIXME` (a known bug that should be corrected), `UNDONE` (a reversal or roll back of previous code), `HACK` (a workaround)
    ```javascript
        /**
         * ...
         * TODO:
         * - [x] task 1
         * - [ ] task 2
         */
    ```
- Store Metadata
    - we can include information author, version, repo links within metadata
    ```javascript
        /**
         * Represents a book.
         * @author FN LN <hey@fnln.me>
         * @version 1.2.3
         * @see {@link http://github.com|GitHub}
         * @since 1.0.1
         * ...
         */
        function Book(title, author) {}
    ```

In VS Code, you just need to type `/**` and it will create the closing tag
![vs-code-comment-javascript](https://cdn.hashnode.com/res/hashnode/image/upload/v1599824523773/jLH7mUGf3.gif?auto=format,compress&gif-q=60&format=webm){max-width: 300px, display: block, margin: 0 auto}

Plugin [Document This](https://marketplace.visualstudio.com/items?itemName=oouo-diogo-perdigao.docthis) is helpful when you want to generate comments based on your function
![plugin-docthis](https://cdn.hashnode.com/res/hashnode/image/upload/v1599825129965/Q5E8RBO4d.gif?auto=format,compress&gif-q=60&format=webm){max-width: 300px, display: block, margin: 0 auto}

Plugin [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) helps to highlight comments
![plugin-better-comments](https://miro.medium.com/max/875/1*Me6NdOC9TmZZXoO9vHOCEw.png){max-width: 300px, display: block, margin: 0 auto}