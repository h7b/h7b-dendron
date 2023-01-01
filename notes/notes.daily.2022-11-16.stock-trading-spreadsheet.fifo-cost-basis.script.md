---
id: 4kl38k7cwfg78sk9ea8bw8t
title: Script from others
desc: ''
updated: 1672544654623
created: 1671913183587
---
# Custom script

Here are the custom user-defined function in google apps script proposed by [allstacksdeveloper](https://www.allstacksdeveloper.com/2022/09/fifo-stock-portfolio-google-sheets.html), [OpenAI chatGPT](https://chat.openai.com/chat) and [YouChat](https://you.com/search?q=who+are+you&fromSearchBar=true&tbm=youchat)

## by allstacksdeveloper

In [this article](https://www.allstacksdeveloper.com/2022/09/fifo-stock-portfolio-google-sheets.html), the author explained in details his way of thinking, how the logic of FIFO affects on unit cost per trade.

```javascript
/**
 * Apply FIFO on transactions sorted ascending by date. 
 * 
 * If it is a BUY transaction, the amount is negative and the quantity is positive.
 * If it is a SELL transaction, the amount is positive and the quantity is negative.
 * 
 * @param {Array<number>} amounts The amounts of transactions sorted ascending by date.
 * @param {Array<number>} quantities The quantities of transactions sorted ascending by date.
 * @return {Array<number>} [remaining quantity, cost of remaining, cost of goods sold];
 * 
 * @customfunction
 */
function fifo(amounts, quantities) {
  if (amounts.length === 0) {
    throw new Error('Amounts and quantities must have at least one element');
  }

  if (amounts.length !== quantities.length) {
    throw new Error('Amounts and quantities do not have the same length');
  }

  if (amounts[0] > 0) {
    throw new Error('The first transaction should be a BUY transaction');
  }

  const queue = [];
  let costOfGoodsSold = 0;
  for (let k = 0; k < amounts.length; k++) {
    costOfGoodsSold = 0; // Reset cost of goods sold before handling the next transaction
    if (isNaN(quantities[k])) {
      throw new Error('Quantitiy ' + quantities[k] + ' is not a number');
    }
    if (isNaN(amounts[k])) {
      throw new Error('Amount ' + amounts[k] + ' is not a number');
    }
    const quantity = Number(quantities[k]);
    const amount = Number(amounts[k]);

    if ((quantity < 0 && amount < 0) || (quantity > 0 && amount > 0)) {
      throw new Error('Amount and quantity can not both be same sign');
    }

    const unitCost = amount / quantity;

    if (amount < 0) { // BUY
      for (let i = 0; i < Math.abs(quantity); i++) {
        queue.push(unitCost);
      }
    }

    if (amount > 0) { // SELL
      for (let i = 0; i < Math.abs(quantity); i++) {
        costOfGoodsSold += queue.shift();
      }
    }
  };

  const remainingQuantity = queue.length;
  const costOfRemaining = queue.reduce((sum, unitCost) => sum + unitCost, 0);
  return [remainingQuantity, Math.abs(costOfRemaining), Math.abs(costOfGoodsSold)];
}
```

## by openai chatgpt

### Q1

Q: implement a fifo user defined function in google appscript

A: 

To implement a FIFO (first-in, first-out) queue in Google Apps Script, you can use an array to store the elements of the queue. Here's an example of how you can create a FIFO queue as a user-defined function:

```javascript
function FIFOQueue() {
  this.queue = [];
}

FIFOQueue.prototype.enqueue = function(element) {
  this.queue.push(element);
}

FIFOQueue.prototype.dequeue = function() {
  if (this.queue.length > 0) {
    return this.queue.shift();
  }
}

FIFOQueue.prototype.size = function() {
  return this.queue.length;
}

FIFOQueue.prototype.isEmpty = function() {
  return this.queue.length === 0;
}
```

To use the FIFO queue, you can create an instance of the `FIFOQueue` class and use the `enqueue` method to add elements to the queue, the `dequeue` method to remove elements from the queue, the `size` method to get the number of elements in the queue, and the `isEmpty` method to check if the queue is empty.

Here's an example of how you can use the FIFO queue:

```javascript
// Create a new FIFO queue
var queue = new FIFOQueue();

// Add some elements to the queue
queue.enqueue('A');
queue.enqueue('B');
queue.enqueue('C');

// Print the size of the queue
Logger.log(queue.size()); // Output: 3

// Remove an element from the queue
var element = queue.dequeue();
Logger.log(element); // Output: A

// Check if the queue is empty
Logger.log(queue.isEmpty()); // Output: false
```

### Q2

Q: The table has four columns. Column one is date of transaction. Column two is stock symbol. Column three is pricer per share. Column four is quantity of shares. Column five is type of transactions, which consists of three choices: buy, sell, dividend. Calculate the realized gain with respect to fifo accounting method, using google apps script

A:

To calculate the realized gain using the FIFO (first-in, first-out) accounting method in Google Apps Script, you can use the following steps:

First, you need to create a function that takes in the table data as an input. You can do this by reading the data from the table using the getDataRange and getValues methods of the Spreadsheet class.

```javascript
function calculateRealizedGain(data) {
  // Get the data from the table
  var values = data.getDataRange().getValues();
}
```

Next, you can create a FIFO queue to store the buy transactions. You can use the user-defined function provided in the previous answer to implement the FIFO queue.

```javascript
function calculateRealizedGain(data) {
  // Get the data from the table
  var values = data.getDataRange().getValues();

  // Create a FIFO queue for the buy transactions
  var buyQueue = new FIFOQueue();
}
```

Then, you can iterate through the rows of the table data and process each transaction. If the transaction is a buy, you can add it to the FIFO queue. If the transaction is a sell, you can remove a buy transaction from the FIFO queue and calculate the realized gain for the sell transaction. If the transaction is a dividend, you can ignore it.

```javascript
function calculateRealizedGain(data) {
  // Get the data from the table
  var values = data.getDataRange().getValues();

  // Create a FIFO queue for the buy transactions
  var buyQueue = new FIFOQueue();

  // Iterate through the rows of the table data
  for (var i = 0; i < values.length; i++) {
    var date = values[i][0];
    var symbol = values[i][1];
    var price = values[i][2];
    var quantity = values[i][3];
    var type = values[i][4];

    if (type === 'buy') {
      // Add the buy transaction to the FIFO queue
      buyQueue.enqueue({date: date, symbol: symbol, price: price, quantity: quantity});
    } else if (type === 'sell') {
      // Remove a buy transaction from the FIFO queue
      var buy = buyQueue.dequeue();

      // Calculate the realized gain for the sell transaction
      var gain = (price - buy.price) * quantity;
      Logger.log(`Realized gain for sell transaction on ${date}: ${gain}`);
    } else if (type === 'dividend') {
      // Ignore the dividend transaction
    }
  }
}
```

Finally, you can call the `calculateRealizedGain` function and pass in the table data as an argument to calculate the realized gain for each sell transaction.

```javascript
function main() {
  // Get the active spreadsheet
  var spreadsheet = SpreadsheetApp.getActiveSpreadsheet();

  // Get the data from the "Transactions" sheet
  var data = spreadsheet.getSheetByName("Transactions");

  // Calculate the realized gain
  calculateRealizedGain(data);
}
```
### Q3

Q: expanding from previous method, what if the quantity of shares sold in a transaction is not equal to the quantity of shares bought?

A:

If the quantity of shares sold in a transaction is not equal to the quantity of shares bought, you can modify the `calculateRealizedGain` function as follows to handle the remaining shares in the buy transaction:

```javascript
function calculateRealizedGain(data) {
  // Get the data from the table
  var values = data.getDataRange().getValues();

  // Create a FIFO queue for the buy transactions
  var buyQueue = new FIFOQueue();

  // Iterate through the rows of the table data
  for (var i = 0; i < values.length; i++) {
    var date = values[i][0];
    var symbol = values[i][1];
    var price = values[i][2];
    var quantity = values[i][3];
    var type = values[i][4];

    if (type === 'buy') {
      // Add the buy transaction to the FIFO queue
      buyQueue.enqueue({date: date, symbol: symbol, price: price, quantity: quantity});
    } else if (type === 'sell') {
      // Initialize the realized gain for the sell transaction
      var gain = 0;

      // Keep removing buy transactions from the FIFO queue until the sell transaction is fully satisfied
      while (quantity > 0) {
        // Remove a buy transaction from the FIFO queue
        var buy = buyQueue.dequeue();

        // Calculate the realized gain for the sell transaction
        var sellQuantity = Math.min(buy.quantity, quantity);
        gain += (price - buy.price) * sellQuantity;
        quantity -= sellQuantity;
      }

      Logger.log(`Realized gain for sell transaction on ${date}: ${gain}`);
    } else if (type === 'dividend') {
      // Ignore the dividend transaction
    }
  }
}
```

In this modified version of the function, we keep removing buy transactions from the FIFO queue until the sell transaction is fully satisfied. For each buy transaction, we calculate the realized gain using the quantity of shares sold in the sell transaction that have not been accounted for yet. Once the sell transaction is fully satisfied, we log the total realized gain for the sell transaction.

### Q4

Q: Can you wrap this modified version into a user-defined function, applied to separate stock symbol?

A:

Sure! Here's how you can wrap the modified version of the calculateRealizedGain function into a user-defined function that calculates the realized gain for a specific stock symbol:

```javascript
function realizedGainBySymbol(symbol) {
  // Get the active spreadsheet
  var spreadsheet = SpreadsheetApp.getActiveSpreadsheet();

  // Get the data from the "Transactions" sheet
  var data = spreadsheet.getSheetByName("Transactions");
  var values = data.getDataRange().getValues();

  // Create a FIFO queue for the buy transactions of the specified symbol
  var buyQueue = new FIFOQueue();

  // Initialize the realized gain for the specified symbol
  var gain = 0;

  // Iterate through the rows of the table data
  for (var i = 0; i < values.length; i++) {
    var date = values[i][0];
    var stockSymbol = values[i][1];
    var price = values[i][2];
    var quantity = values[i][3];
    var type = values[i][4];

    if (stockSymbol === symbol) {
      if (type === 'buy') {
        // Add the buy transaction to the FIFO queue
        buyQueue.enqueue({date: date, symbol: symbol, price: price, quantity: quantity});
      } else if (type === 'sell') {
        // Keep removing buy transactions from the FIFO queue until the sell transaction is fully satisfied
        while (quantity > 0) {
          // Remove a buy transaction from the FIFO queue
          var buy = buyQueue.dequeue();

          // Calculate the realized gain for the sell transaction
          var sellQuantity = Math.min(buy.quantity, quantity);
          gain += (price - buy.price) * sellQuantity;
          quantity -= sellQuantity;
        }
      } else if (type === 'dividend') {
        // Ignore the dividend transaction
      }
    }
  }

  return gain;
}
```

To use this function, you can pass in the stock symbol as an argument and it will return the realized gain for that symbol. For example:

```javascript
var gain = realizedGainBySymbol('AAPL');
Logger.log(`Realized gain for stock symbol AAPL: ${gain}`);
```

### Q5

Q: why do we need the "prototype" in FIFOQueue?

A: 

The `prototype` property is used in the `FIFOQueue` function to define the methods that will be available for all instances of the `FIFOQueue` class.

When you define a method for a class using the `prototype` property, it is added to the `prototype` object of the class, which means that all instances of the class will have access to that method. This is useful when you want to define methods that will be shared by all instances of the class, rather than creating a separate copy of the method for each instance.

For example, in the `FIFOQueue` function, the `enqueue`, `dequeue`, `size`, and `isEmpty` methods are defined using the `prototype` property. This means that all instances of the `FIFOQueue` class will have access to these methods, and you can call them on any instance of the `FIFOQueue` class using the `.` operator.

Here's an example of how you can create an instance of the `FIFOQueue` class and call the `enqueue` method on it:

```javascript
var queue = new FIFOQueue();
queue.enqueue('A');
```

### Q6

Q: write a function that retrieves only the transactions of one ticker

A:

To retrieve only the transactions of a specific ticker from a table in Google Sheets, you can use the following function:

```javascript
function getTransactionsByTicker(ticker) {
  // Get the active spreadsheet
  var spreadsheet = SpreadsheetApp.getActiveSpreadsheet();

  // Get the data from the "Transactions" sheet
  var data = spreadsheet.getSheetByName("Transactions");
  var values = data.getDataRange().getValues();

  // Create an array to store the transactions of the specified ticker
  var transactions = [];

  // Iterate through the rows of the table data
  for (var i = 0; i < values.length; i++) {
    var date = values[i][0];
    var symbol = values[i][1];
    var price = values[i][2];
    var quantity = values[i][3];
    var type = values[i][4];

    if (symbol === ticker) {
      // Add the transaction to the array
      transactions.push({date: date, symbol: symbol, price: price, quantity: quantity, type: type});
    }
  }

  return transactions;
}
```

To use this function, you can pass in the ticker symbol as an argument and it will return an array of objects, each representing a transaction of the specified ticker. For example:

```javascript
var transactions = getTransactionsByTicker('AAPL');
Logger.log(transactions);
```

### Q7

Q: why do `transactions` object has curly brackets, while `values` has square brackets?

A:

In JavaScript, objects are denoted by curly braces `{}` and arrays are denoted by square brackets `[]`.

In the `getTransactionsByTicker` function, the `transactions` variable is an array of objects, where each object represents a transaction. Therefore, the `transactions` variable is denoted by square brackets [].

On the other hand, the `values` variable is a two-dimensional array that represents the data in the "Transactions" sheet. Therefore, the `values` variable is denoted by square brackets `[]`.

Here's a brief overview of how objects and arrays are used in JavaScript:

**Objects**:

Objects are used to store data as key-value pairs. The keys are strings and the values can be of any data type.

Here's an example of an object in JavaScript:

```javascript
var person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30
};
```

In this example, the person object has three properties: firstName, lastName, and age. The keys are strings and the values are strings and numbers, respectively.

**Arrays**:

Arrays are used to store a list of items. The items can be of any data type.

Here's an example of an array in JavaScript:

```javascript
var numbers = [1, 2, 3, 4, 5];
```

In this example, the `numbers` array has five elements: 1, 2, 3, 4, and 5. The elements are numbers.

## by YouChat

Here is another version from [YouChat](https://you.com/search?q=who+are+you&fromSearchBar=true&tbm=youchat). In my opinion, the current version of YouChat is not as polished as chatgpt. I tried a more detailed question as in previous part with chatgpt, but YouChat refused to answer due to its complexity.

Q: calculate the realized gain with fifo method using google apps script

A:

This script will calculate the realized gain for each row of data in the spreadsheet and set the result in the fifth column.

```javascript
function calculateRealizedGain() {
  // Get the data from the spreadsheet
  var sheet = SpreadsheetApp.getActiveSheet();
  var data = sheet.getDataRange().getValues();
  
  // Iterate over the data
  for (var i=0; i<data.length; i++) {
    var costPerShare = data[i][2];
    var sharesSold = data[i][3];
    var pricePerShare = data[i][4];
    
    // Calculate the realized gain
    var realizedGain = (pricePerShare - costPerShare) * sharesSold;
    
    // Set the realized gain value in the spreadsheet
    sheet.getRange(i+1, 5).setValue(realizedGain);
  }
}
```

## Related

- [stackoverflow | Creating a function to calculate realized gains of stock using FIFO method based on transactional history](https://stackoverflow.com/questions/68962874/creating-a-function-to-calculate-realized-gains-of-stock-using-fifo-method-based)
- [stackoverflow | Calculate Avg Price, Realized gain & Unrealized gain via UDF using FIFO method](https://stackoverflow.com/questions/68351891/calculate-avg-price-realized-gain-unrealized-gain-via-udf-using-fifo-method)
- [stackoverflow | FIFO Capital Gains Calculation Formula](https://stackoverflow.com/questions/67899452/fifo-capital-gains-calculation-formula)
- [stackoverflow | Calculate Profit/Capital Gains on Sold Inventory/Shares](https://stackoverflow.com/questions/67930020/calculate-profit-capital-gains-on-sold-inventory-shares)