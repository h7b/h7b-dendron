---
id: nda315paq8tasysm04ak5l1
title: Average Cost per Share
desc: 'Average Cost per Share'
updated: 1672998402227
created: 1672960881078
---
# How to calculate Average Cost per Share?

## Version 0

In sheet `pnl`, there is a column called `average cost per share`.

Initially, it was calculated as the quotient of the cost of purchasing a specific stock and the total number of shares which were bought. This is also equivalent to the weighted average cost per share (by number of shares bought for each transaction), since the `cost of purchasing` is equals to the sum-product of `price per share` and `number of shares` for each ticker.

$$average\ cost\ per\ share = \frac{cost\ of\ purchasing}{total\ shares\ bought}$$

Possible enhancement from this `version 0`:
- if a share is already sold, the calculation of the weighted average should not take the price of sold shares into consideration.

## Version 0.1

In this version, I replaced the division which requires extra helper columns, by using the [AVERAGE.WEIGHTED function](https://support.google.com/docs/answer/9084098?hl=en).

The formula:
```javascript
=AVERAGE.WEIGHTED(
    QUERY(orderBook!$A:$G, "SELECT E WHERE B CONTAINS '"&$A2&"' AND (C LIKE 'buy' OR C LIKE 'stock dividend') LABEL E ''"), 
    QUERY(orderBook!$A:$G, "SELECT D WHERE B CONTAINS '"&$A2&"' AND (C LIKE 'buy' OR C LIKE 'stock dividend') LABEL D ''")
    )
```

where
- column `E` in sheet `orderBook` is: `price per share`
- column `D` in sheet `orderBook` is: `number of shares`
- and the formula is applicable only to transactions with `type` as `buy` or `stock dividend`

## Version 1

In this version, I replaced the `AVERAGE.WEIGHTED function` by a custom user-defined function to compute the weighted average cost per share unsold. It means that when a share is already sold, its unit price will not be taken into consideration.

```javascript
...
// Calculate the total cost of the unsold shares, then the weighted average cost of unsold
let totalCostOfUnsold = 0;
let avgCostOfUnsold = 0;

switch (true) {
  case buyQueue.length == 0:
    totalCostOfUnsold = 0;
    avgCostOfUnsold = 0;
    break;
  case buyQueue.length > 0:
    // if `buyQueue` array has any elements
    // Adding up all of the remaining elements in the `buyQueue` array and returning the total cost of the unsold shares
    totalCostOfUnsold = buyQueue.reduce((sum, unitPrice) => sum + unitPrice, 0);
    // Calculate the weighted average cost of the unsold shares
    avgCostOfUnsold = totalCostOfUnsold / buyQueue.length;
    break;
  default: 
    // Do nothing
    break;
}
...
```