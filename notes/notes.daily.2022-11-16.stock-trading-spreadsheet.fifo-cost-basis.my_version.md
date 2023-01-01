---
id: tesj8d1zr6wuvk20bbdhi41
title: My version
desc: ''
updated: 1672544623321
created: 1672460883406
---
# My version

After having researched on several [[solutions from others|notes.daily.2022-11-16.stock-trading-spreadsheet.fifo-cost-basis.script]], here is my attempt.

## Thoughts

Use the function `getTransactionsByTicker(stockTicker)` to retrieve all the transactions of a specific stock. From these extracted transactions, calculate the realized gain/loss of this stock by calling the custom formula `realizedGainByTicker(stockTicker)`. Then return the result using these two User-defined formula (UDF) `REALIZEDGAINBYTICKER()` and `COSTOFUNSOLD()`

Logic:
- Retrieve all transactions of a stock, and sort them by date
- if a transaction has `type` as `buy` or `stock dividend`, then `push()` its `price` (unit price per share in this transaction) to the `buyQueue` multiple times. The number of time here is defined by the `quantity` of this transaction
- if a transaction has `type` as `sell`,
    - `shift()` one element out of the array `buyQueue` and take this element into sum as `costOfGoodsSold`
    - `push()` its `price` (unit price per share in this transaction) to the `sellQueue` multiple times. The number of time here is defined by the `quantity` of this transaction
- `revenue` from selling this specific stock is the sum of all elements in the `sellQueue` array
- realized gain is the difference between `revenue` and `costOfGoodsSold`
- cost of the unsold shares is the sum of all remaining elements in the `buyQueue` array

DONE:
- how about the unrealized gain/loss?
- did i take into account of tax and trading fee?
- how to treat the type `stock dividend` and `cash dividend`?

## User-defined function

Here is my version of the User-defined function (UDF), embedded in the spreadsheet, written in google apps script.

<script src="https://gist.github.com/h7b/4fc057be0fff4a5db9fd207c7d156560.js"></script>

## Explanation

### Explain 1

```javascript
// Sort the transactions by date in ascending order
transactions.sort(function(a, b) {
  return new Date(a.date) - new Date(b.date);
});
```

A by chatGPT:

The `sort` method is a built-in method of the `Array` object in JavaScript that sorts the elements of an array in place and returns the sorted array. The sort method can take an optional comparison function as an argument.

The comparison function is a function that compares two elements of the array and returns a value indicating their relative order. If the return value is negative, the first element is considered to be "less than" the second element and is sorted to an earlier position. If the return value is positive, the first element is considered to be "greater than" the second element and is sorted to a later position. If the return value is zero, the elements are considered to be equal and their order is not changed.

In the `getTransactionsByTicker` function, the `sort` method is called on the `transactions` array and the comparison function compares the dates of two transactions. The comparison function takes two arguments, `a` and `b`, which represent two transactions in the array.

The comparison function first converts the dates of the two transactions to `Date` objects using the `Date` constructor. The `Date` constructor takes a string representation of a date as an argument and returns a `Date` object that represents the same date.

The comparison function then returns the result of subtracting the `Date` object of the second transaction from the `Date` object of the first transaction. If the result is negative, it means that the date of the first transaction is earlier than the date of the second transaction, and the first transaction is sorted to an earlier position in the array. If the result is positive, it means that the date of the first transaction is later than the date of the second transaction, and the first transaction is sorted to a later position in the array. If the result is zero, it means that the dates of the two transactions are equal, and their order is not changed.

The `sort` method should not be called inside the `for` loop in the `getTransactionsByTicker` function.

If you call the `sort` method inside the `for` loop, it will sort the transactions array after each iteration of the loop, which is inefficient and unnecessary. Instead, you should wait until all the transactions have been added to the `transactions` array and then sort the array once.

### Explain 2

```javascript
  // Adding up all of the elements in the `sellQueue` array and returning the sum
  const revenue = sellQueue.reduce((sum, price) => sum + price, 0);
```
A by chatGPT:

In this JavaScript code, `revenue` is a constant variable that is being assigned the result of calling the `reduce()` function on the `sellQueue` array.

The `reduce()` function is a built-in JavaScript function that applies a callback function to each element in an array, in order to reduce the array to a single value. The callback function takes two arguments: `sum` and `price`. `sum` represents the accumulated value that is returned by the callback function, and `price` represents the current element being processed in the array.

The `reduce()` function also takes an optional initial value as its second argument. In this case, the initial value is 0.

The callback function for the `reduce()` function in this code simply adds `price` to `sum` and returns the result. This has the effect of adding up all of the elements in the `sellQueue` array and returning the sum.

For example, if the `sellQueue` array looks like this:
```javascript
[10, 20, 30]
```
Then the `reduce()` function would be called with the following arguments:
```javascript
callback(0, 10) => 10
callback(10, 20) => 30
callback(30, 30) => 60
```
The final result of the `reduce()` function would be 60, which would be assigned to the `revenue` variable.

### Explain 3

ref: [javascripttutorial](https://www.javascripttutorial.net/javascript-return-multiple-values/)

```javascript
function fifoCalc(stockTicker) {
  //...
  return {realizedGain, costOfUnsold};
}

function costOfUnsold(stockTicker) {
  let result = fifoCalc(stockTicker);
  
  return result.costOfUnsold;
}
```

JavaScript doesn’t support functions that return multiple values. However, you can wrap multiple values into an array or an object and return the array or the object.

In my code, I chose returning multiple values from a function using an object. I use an object because I want to assign a name to each returned value to make it more readable and easier to maintain.

### Explain 4

ref: [stackoverflow](https://stackoverflow.com/questions/17341399/refresh-data-retrieved-by-a-custom-function-in-google-sheet/)

```javascript
function onEdit(e) {
  // Get the name of the sheet that was edited
  const sheetName = e.source.getActiveSheet().getName();

  // Check if the sheet name matches the sheet you are interested in, which is `orderBook`
  if (sheetName === 'orderBook') {
    // If the sheet name matches, update cell F2 of sheet `helper`
    let formattedDate = Utilities.formatDate(new Date(), "GMT", "yyyy-MM-dd'T'HH:mm:ss'Z'");
    e.source.getSheetByName('helper').getRange('$F$2').setValue(formattedDate);
  }
}
```

Situation: 
- without this script, the result of custom formula do not re-evaluated on change of the value of any cell in sheet `orderBook`

Reason:
- Google Sheets doesn't re-run the script as long as the script parameters are similar, it uses cached results from the previous runs.
    - Google Sheets considers that all your custom functions depend only on their parameters values directly to return their result (you can optionally depend on other static data)
    - Given this prerequisite they can evaluate your functions only when a parameter changes.
    - Example: 
        - Let's suppose we have the text "10" on cell B1, then on some other cell we type `=myFunction(B1)`
        - `myFunction` will be evaluated, and its result will be retrieved. Then you change cell B1 value to "35", custom function will be re-evaluated as expected and the new result is retrieved normally. Now, you change cell B1 again to the original "10", there's no re-evaluation, the former result is retrieved immediately from cache.

Solution:
- In the sheet `pnl`, instead of calling `=myFunction(firstParam)`, which is `=realizedGainByTicker($A2)`, I have to add an extra dummy parameter located at `helper!$F$2`. Then the function call will be `=realizedGainByTicker($A2, helper!$F$2)`
- The dummy value at cell F2 of sheet `helper` is updated on the edit event of any cell in sheet `oderBook` (as written in the code above)

### Explain 5

ref: [google](https://developers.google.com/apps-script/guides/sheets/functions)

Create Custom Functions in Google Sheets.

You can use Google Apps Script to write custom functions — say, to convert meters to miles or fetch live content from the Internet — then use them in Google Sheets just like a built-in function.

Custom functions are created using standard JavaScript.

Guidelines for custom functions
- Capitalization does not matter, although the names of spreadsheet functions are traditionally uppercase [^1]
- A custom function call must return within 30 seconds. If it does not, the cell will display an error: `Internal error executing the custom function.` [^2]
- Google Sheets supports autocomplete for custom functions much like for built-in functions, if their script includes a JsDoc `@customfunction` tag. [^3]

[^1]: https://developers.google.com/apps-script/guides/sheets/functions#naming
[^2]: https://developers.google.com/apps-script/guides/sheets/functions#return_values
[^3]: https://developers.google.com/apps-script/guides/sheets/functions#autocomplete

### Explain 6

```javascript
switch (type) {
  case 'stock dividend':
  case 'buy':
    for (let i = 0; i < Math.abs(quantity); i++) {
      buyQueue.push(unitPrice);
    }
    break;
  case 'sell':
    for (let i = 0; i < Math.abs(quantity); i++) {
      costOfGoodsSold += buyQueue.shift();
      sellQueue.push(unitPrice);
    }
    break;
  default:
    // do nothing
    break;
}
```

Logic:
- if a transaction has `type` as `buy` or `stock dividend`, `push()` its `price` (unit price per share in this transaction) to the `buyQueue` multiple times. The number of time here is defined by the `quantity` of this transaction
- if a transaction has `type` as `sell`,
    - `shift()` one element out of the array `buyQueue` and take this element into sum as `costOfGoodsSold`
    - `push()` its `price` (unit price per share in this transaction) to the `sellQueue` multiple times. The number of time here is defined by the `quantity` of this transaction

Explain
- In `switch` statement, if there is no `break` below a `case` clause, execution will continue to the next `case` clause regardless if that `case` meets the criteria. This behavior is called "fall-through" [^4]
- The following is an example of a single operation sequential `case` statement, where four different values (Cow, Giraffe, Dog, Pig) perform exactly the same. [^4]

[^4]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch

```javascript
const Animal = 'Giraffe';
switch (Animal) {
  case 'Cow':
  case 'Giraffe':
  case 'Dog':
  case 'Pig':
    console.log('This animal is not extinct.');
    break;
  case 'Dinosaur':
  default:
    console.log('This animal is extinct.');
}
```

### Explain 7

Q: how to retrieve `quantity` from `transactions` array?

A:

To retrieve the `quantity` property from an object in the `transactions` array, you can use the following syntax, where `i` is the index of the object in the `transactions` array that you want to access.

```javascript
transactions[i].quantity
```

For example, if `transactions` is an array of objects that looks like this:

```javascript
[
  { date: '2022-01-01', ticker: 'AAPL', type: 'BUY', quantity: 10, price: 500 },
  { date: '2022-01-02', ticker: 'AAPL', type: 'SELL', quantity: 5, price: 600 },
  { date: '2022-01-03', ticker: 'GOOG', type: 'BUY', quantity: 15, price: 400 }
]
```

Then you could access the `quantity` property of the first object in the array like this:

```javascript
const quantity = transactions[0].quantity;
// quantity is 10
```

Or you can also use a loop to iterate over all of the objects in the transactions array and access the quantity property of each object.

```javascript
for (let i = 0; i < transactions.length; i++) {
  console.log(transactions[i].quantity);
}
```

### Explain 8

Unrealized Gain/Loss = current position value - cost of unsold share - trading fee

Only calculate if the `current number of share` is not `0`

```javascript
=IF($D2=0, 0, $G2-COSTOFUNSOLD($A2, helper!$F$2)-$F2)
```

### Explain 9

Realized Gain/Loss = realizedGain - trading fee - income tax

Only calculate if the `total shares sold` is not `0`

```javascript
=IF($C2=0, 0, REALIZEDGAINBYTICKER($A2, helper!$F$2)-$F2-QUERY(orderBook!$A:$H, "SELECT sum(H) WHERE B CONTAINS '"&$A2&"' LABEL sum(H) ''"))
```