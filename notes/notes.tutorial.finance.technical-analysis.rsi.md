---
id: mbm1vidwed90xyd1t5gtfa6
title: Relative Strength Index (RSI)
desc: ''
updated: 1650027280697
created: 1649905202115
---
# Relative Strength Index (RSI)

ref: [Investopedia](https://www.investopedia.com/terms/r/rsi.asp), [Wikipedia](https://en.wikipedia.org/wiki/Relative_strength_index)

The relative strength index (RSI) is a popular momentum oscillator developed in 1978 by [J. Welles Wilder](https://en.wikipedia.org/wiki/J._Welles_Wilder_Jr.)

The RSI is displayed as an oscillator (a line graph that moves between two extremes) and can have a reading from 0 to 100.

The RSI measures the magnitude of recent price changes to evaluate overbought or oversold conditions in the price of a stock or other asset. 
- An asset is usually considered overbought or overvalued when the RSI is above 70 and may be primed for a trend reversal or corrective pullback in price
- An RSI reading of 30 or below indicates an oversold or undervalued condition

![rsi-example](https://upload.wikimedia.org/wikipedia/commons/6/67/RSIwiki.gif){max-width: 300px, display: block, margin: 0 auto}

## Interpretation of RSI

The RSI was designed to indicate whether a security is overbought or oversold in relation to recent price levels. The RSI is calculated using average price gains and losses over a given period of time. The default time period is 14 periods, with values bounded from 0 to 100.

- The slope of the RSI is directly proportional to the velocity of a change in the trend. 
- The distance traveled by the RSI is proportional to the magnitude of the move.

[[Moving Average Convergence Divergence (MACD)|notes.tutorial.finance.technical-analysis.macd]] and Relative Strength Index (RSI) are indicators that measure the momentum of an asset. However, they measure different factors, so they sometimes give contradictory indications. 
- For example, the RSI may show a reading above 70 for a sustained period of time, indicating the security is overextended to the buy side
- At the same time, the MACD could indicate that buying momentum is still increasing for the security

The basic idea behind the RSI is to measure how quickly traders are bidding the price of the security up or down. Traders will often place this RSI chart below the price chart for the security, so they can compare its recent momentum against its market price.

## Calculation

For each trading period an upward change $U$ or downward change $D$ is calculated. 

- Up periods are characterized by its close being higher than the previous close.

    $$U = close_{now} - close_{previous}$$
    
    $$D = 0$$

- Down period is characterized by the close being lower than the previous period's close

    $$U = 0$$
    
    $$D = |close_{now} - close_{previous}|$$

- If the last close is the same as the previous, both $U$ and $D$ are zero

The average $U$ and $D$ are calculated using an n-period [[smoothed or modified moving average (SMMA or MMA)|notes.tutorial.finance.technical-analysis.ma.mma]].

The ratio of these averages is the Relative Strength (RS) or relative strength factor:

$$RS = \frac{SMMA(U,n)}{SMMA(D,n)}$$

The relative strength factor is then converted to a relative strength index between 0 and 100:

$$RSI = 100 - \frac{100}{1+RS}$$