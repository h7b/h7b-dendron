---
id: lbsup0a5sh4z0g0b3d6mdn7
title: Excess Returns Model
desc: ''
updated: 1649800323332
created: 1649800076468
---
# Excess Returns Model
ref: [SimplyWallSt](https://github.com/SimplyWallSt/Company-Analysis-Model/blob/master/MODEL.markdown#excess-returns-model--how-is-this-calculated=)

Used for financial companies such as banks and insurance firms. These companies generally do not have a significant proportion of physical assets and face different regulatory requirements for cash holdings to other businesses.

*Excess Returns* method is better suited to calculate the intrinsic value of financial companies than the traditional discounted cash flows model. The key assumption for this model is that equity value is how much the firm can earn, over and above its cost of equity, given the level of equity it has in the company at the moment. The returns above the cost of equity is known as excess returns:

> Excess Return = (Return on Equity – Cost Of Equity) \ (Book Value Of Equity)

We use this value to calculate the terminal value of the company, which is how much we expect the company to continue to earn every year, forever. This is a common component of discounted cash flow models:

$$Terminal Value = \frac{Excess Return}{Cost of Equity – Expected Growth Rate}$$

Putting this all together, we get the value of the company:

> Company Valuation = Book Value of Equity + Present Value of Terminal Value

$$Value Per Share = \frac{Book Value of Equity + Present Value of Terminal Value}{Shares Outstanding}$$

Note that the component *Book Value of Equity (BVE)* represents the equity capital that has been invested in the company plus retained earnings. For each year going forward, BVE is estimated in order to reflect the growing nature of the company.
