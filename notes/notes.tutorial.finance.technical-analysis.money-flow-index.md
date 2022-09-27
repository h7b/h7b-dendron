---
id: 43qnke4zru6l6y3iqhepb1f
title: Money Flow Index
desc: ''
updated: 1649984597110
created: 1649980727556
---
# Money Flow Index - MFI

ref: [Investopedia](https://www.investopedia.com/terms/m/mfi.asp), [Fidelity](https://www.fidelity.com/learning-center/trading-investing/technical-analysis/technical-indicator-guide/MFI), [Wikipedia](https://en.wikipedia.org/wiki/Money_flow_index)

The Money Flow Index (MFI) is a momentum indicator that measures the flow of money into and out of a security over a specified period of time. It is related to the [[Relative Strength Index (RSI)|notes.tutorial.finance.technical-analysis.rsi]] but incorporates volume, whereas the RSI only considers price. Hence MFI is sometimes also called as volume-weighted RSI.

An MFI reading above 80 is considered overbought and an MFI reading below 20 is considered oversold, although levels of 90 and 10 are also used as thresholds.

![mfi-example](https://www.fidelity.com/bin-public/060_www_fidelity_com/images/LC/MFI602x345.png){max-width: 300px, display: block, margin: 0 auto}

## Calculation

$$Money\ Flow\ Index = 100 * \frac{Positive\ Money\ Flow}{Positive\ Money\ Flow + Negative\ Money\ Flow}$$

Generally, the Money Flow Index (MFI) is calculated by 
- accumulating positive and negative Money Flow values, 
- then compared how many percent Posivitive Money Flow vs the sum of both positive and negative Money Flow

The steps for calculating the Money Flow Index for 14-day holding period (a period can be intra-day or any time interval) are as follows.

1. Calculate the $Typical\ Price$ for each of the last 14 days

    $$Typical\ Price = \frac{High+Low+Close}{3}$$

2. Calculate the positive and negative money flow.

    The money flow for a certain day is typical price multiplied by volume on that day.

    $$Money\ Flow = Typical\ Price * Volume$$

    The money flow is divided into positive and negative money flow.
    - *Positive money flow* is calculated by adding the money flow of all the days where the $Typical\ Price$ is higher than the previous day's $Typical\ Price$
    - *Negative money flow* is calculated by adding the money flow of all the days where the $Typical\ Price$ is lower than the previous day's $Typical\ Price$
    - If $Typical\ Price$ is unchanged then that day is discarded

3. Calculate $Money\ Flow\ Ratio = \frac{Positive\ Money\ Flow}{Negative\ Money\ Flow}$

4. Calculate the Money Flow Index (MFI) using the ratio found

    $$Money\ Flow\ Index = 100 - \frac{100}{1+Money\ Flow\ Ratio}$$

    Or it can be also expressed as

    $$Money\ Flow\ Index = 100 * \frac{Positive\ Money\ Flow}{Positive\ Money\ Flow + Negative\ Money\ Flow}$$
