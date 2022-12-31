---
id: tesj8d1zr6wuvk20bbdhi41
title: My_version
desc: ''
updated: 1672462790110
created: 1672460883406
---
# My version

## Thoughts

Use the function `getTransactionsByTicker(stockTicker)` to retrieve all the transactions of a specific stock.

From these extracted transactions, calculate the realized gain/loss of this stock by calling the custom formula `realizedGainByTicker(stockTicker)`.

Logic:
- Retrieve all transactions of a stock, and sort them by date
- if a transaction has `type` as `buy`, `push()` its `price` (unit price per share in this transaction) to the `buyQueue` multiple times. The number of time here is defined by the `quantity` of this transaction
- if a transaction has `type` as `sell`,
    - `shift()` one element out of the array `buyQueue` and take this element into sum as `costOfGoodsSold`
    - `push()` its `price` (unit price per share in this transaction) to the `sellQueue` multiple times. The number of time here is defined by the `quantity` of this transaction
- `revenue` from selling this specific stock is the sum of all elements in the `sellQueue` array
- realized gain is the difference between `revenue` and `costOfGoodsSold`

TODO:
- how to treat the type `stock dividend` and `cash dividend`?
- how about the unrealized gain/loss?
- did i take into account of tax and trading fee?

## Script

```javascript
/**
 * Retrieve all the transactions of a specific stock
 * 
 * There are 4 types of transactions: buy, sell, stock dividend, cash dividend
 * 
 * @param {String<string>} ticker of the specific stock to be retrieved.
 * @return {Array<object>} [{date: date, ticker: ticker, type: type, quantity: quantity, price: price}];
 * 
 *
 */
function getTransactionsByTicker(stockTicker) {
  // Get the active spreadsheet
  let spreadsheet = SpreadsheetApp.getActiveSpreadsheet();

  // Get the data from the "orderBook" sheet
  let data = spreadsheet.getSheetByName("orderBook");
  let values = data.getDataRange().getValues();

  // Create an array to store the transactions of the specified stock
  let transactions = [];

  // Iterate through the rows of the table data
  for (let i = 0; i < values.length; i++) {
    let date = values[i][0];
    let ticker = values[i][1];
    let type = values[i][2];
    let quantity = values[i][3];
    let price = values[i][4];

    if (ticker === stockTicker) {
      // Add the transaction to the array
      transactions.push({date: date, ticker: ticker, type: type, quantity: quantity, price: price});
    }
  }

  // Sort the transactions by date in ascending order
  transactions.sort(function(a, b) {
    return new Date(a.date) - new Date(b.date);
  });

  return transactions;
}

/**
 * Apply FIFO on transactions sorted ascending by date, to calculate the realized gain/loss
 * 
 * If it is a BUY transaction, the type is 'buy'
 * If it is a SELL transaction, the type is 'sell'
 * 
 * @param {String<string>} ticker of the specific stock to calculate its realized gain/loss.
 * @return {Number<number>} realized gain/loss;
 * 
 * @customfunction
 */
function realizedGainByTicker(stockTicker) {
  let transactions = getTransactionsByTicker(stockTicker);

  // Create a blank queue for the buy and sell transactions of the specified stock
  let buyQueue = [];
  let sellQueue = [];

  // Initialize the realized gain for the specified ticker
  let costOfGoodsSold = 0;

  // Iterate over all of the objects in the `transactions` array
  for (let i = 0; i < transactions.length; i++) {
    const type = String(transactions[i].type);
    const quantity = Number(transactions[i].quantity);
    const price = Number(transactions[i].price);

    switch (type) {
      case 'buy':
        for (let i = 0; i < Math.abs(quantity); i++) {
          buyQueue.push(price);
        }
        break;
      case 'sell':
        for (let i = 0; i < Math.abs(quantity); i++) {
          costOfGoodsSold += buyQueue.shift();
          sellQueue.push(price);
        }
        break;
      default:
        // do nothing
        break;
    }
  }
  
  // Adding up all of the elements in the `sellQueue` array and returning the sum
  const revenue = sellQueue.reduce((sum, price) => sum + price, 0);

  // Calculate realized gain from selling a specific stock
  const gain = revenue - costOfGoodsSold;
  
  return gain;
}
```

## Q&A with chatGPT

### Explain 1 by chatGPT

```javascript
  // Sort the transactions by date in ascending order
  transactions.sort(function(a, b) {
    return new Date(a.date) - new Date(b.date);
  });
```

The `sort` method is a built-in method of the `Array` object in JavaScript that sorts the elements of an array in place and returns the sorted array. The sort method can take an optional comparison function as an argument.

The comparison function is a function that compares two elements of the array and returns a value indicating their relative order. If the return value is negative, the first element is considered to be "less than" the second element and is sorted to an earlier position. If the return value is positive, the first element is considered to be "greater than" the second element and is sorted to a later position. If the return value is zero, the elements are considered to be equal and their order is not changed.

In the `getTransactionsByTicker` function, the `sort` method is called on the `transactions` array and the comparison function compares the dates of two transactions. The comparison function takes two arguments, `a` and `b`, which represent two transactions in the array.

The comparison function first converts the dates of the two transactions to `Date` objects using the `Date` constructor. The `Date` constructor takes a string representation of a date as an argument and returns a `Date` object that represents the same date.

The comparison function then returns the result of subtracting the `Date` object of the second transaction from the `Date` object of the first transaction. If the result is negative, it means that the date of the first transaction is earlier than the date of the second transaction, and the first transaction is sorted to an earlier position in the array. If the result is positive, it means that the date of the first transaction is later than the date of the second transaction, and the first transaction is sorted to a later position in the array. If the result is zero, it means that the dates of the two transactions are equal, and their order is not changed.

The `sort` method should not be called inside the `for` loop in the `getTransactionsByTicker` function.

If you call the `sort` method inside the `for` loop, it will sort the transactions array after each iteration of the loop, which is inefficient and unnecessary. Instead, you should wait until all the transactions have been added to the `transactions` array and then sort the array once.

### Explain 2 by chatGPT

```javascript
  // Adding up all of the elements in the `sellQueue` array and returning the sum
  const revenue = sellQueue.reduce((sum, price) => sum + price, 0);
```
A:

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