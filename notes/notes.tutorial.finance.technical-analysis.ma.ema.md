---
id: 9o5c8jy9akypc7rwk2v8sgh
title: Exponential Moving Average (EMA)
desc: ''
updated: 1650026084498
created: 1649902259855
---
# Exponential Moving Average (EMA)

ref: [Investopedia](https://www.investopedia.com/terms/e/ema.asp), [Wikipedia](https://en.wikipedia.org/wiki/Moving_average)

The EMA is a moving average that places a greater weight and significance on the most recent data points.

An exponentially weighted moving average reacts more significantly to recent price changes than a [[simple moving average (SMA)|notes.tutorial.finance.technical-analysis.ma.sma]], which applies an equal weight to all observations in the period.

Since EMAs place a higher weighting on recent data than on older data, they are more responsive to the latest price changes than SMAs.

## Calculation

$$EMA_{today} = EMA_{yesterday} + \alpha(price_{today}-EMA_{yesterday})$$

Expanding out

$$EMA_{today} = \alpha[p_1 + (1-\alpha)p_2 + (1-\alpha)^2p_3 + (1-\alpha)^3p_4 + ...]$$

where:
- $p_1 = price_{today}$
- $p_2 = price_{yesterday}$ and so on

Since $\frac{1}{\alpha} = 1 + (1-\alpha) + (1-\alpha)^2 + ...$

then $EMA_{today} = \frac{p_1 + (1-\alpha)p_2 + (1-\alpha)^2p_3 + (1-\alpha)^3p_4 + ...}{1 + (1-\alpha) + (1-\alpha)^2 + (1-\alpha)^3 + ...}$

A commonly used value for $\alpha$ is $\alpha = \frac{2}{N+1}$

In an equivalent expression, $EMA_{today} = ClosingPrice * multiplier + EMA_{previousDay} * (1 - multiplier)$

where:
- $multiplier = \frac{smoothing(weighting)}{number\ of\ Observations + 1}$
- there are many possible choices for the smoothing factor, the most common choice is: $smoothing=2$

Example: a 20-day EMA, the multiplier would be $\frac{2}{20+1} = 0.0952$.

## What Does the Exponential Moving Average Tell You?

The 12- and 26-day exponential moving averages (EMAs) are often the most quoted and analyzed short-term averages. The 12- and 26-day are used to create indicators like the [[moving average convergence divergence (MACD)|notes.tutorial.finance.technical-analysis.macd]]
