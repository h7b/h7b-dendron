---
id: 2qvqusnh257sk1mjlq8u4b4
title: Modified Moving Average
desc: ''
updated: 1650026547257
created: 1650024121980
---
# Modified Moving Average

ref: [Wikipedia](https://en.wikipedia.org/wiki/Moving_average#Modified_moving_average)

A modified moving average (MMA), running moving average (RMA), or smoothed moving average (SMMA) is defined as:

$$\bar{P}_{MM,today} = \frac{(N-1)\bar{P}_{MM,yesterday} + P_{today}}{N}$$

In short, this is an [[notes.tutorial.finance.technical-analysis.ma.ema]] with $\alpha = \frac{1}{N}$.

For EMA, the customary choice is $\alpha = \frac{2}{N+1}$.
