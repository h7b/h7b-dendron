---
id: 6mv2pym5xhl50lop417altq
title: Two Stage Model
desc: ''
updated: 1649800575847
created: 1649800553162
---
# DCF model for Firm with two distinct stages of growth

aka two-stage growth model.

Basically, the two-stage DCF is a multiple-period model. It means that simply find the present value of the first $n$ dividends and the present value of the projected value at time $n$

$$V_0 = \displaystyle\sum_{t=1}^n \frac{CF_t}{(1+r)^t} + \frac{V_n}{(1+r)^n}$$

The two-stage model assumes that the first $n$ dividends grow at an extraordinary short-term rate, $g_S$.

$$CF_t = CF_0(1+g_S)^t$$

After time $n$, the annual dividend growth rate changes to a normal long-term rate, $g_L$. The cash flow at time $n+1$ is:

$$CF_{n+1} = CF_n(1+g_L) = CF_0(1+g_S)^n(1+g_L)$$

Applying Gordon growth model to find:

$$V_n = \frac{CF_{n+1}}{r-g_L} = \frac{CF_0(1+g_S)^n(1+g_L)}{r-g_L}$$

Which leads to the formula to find the value at $t=0$

$$V_0 = \displaystyle\sum_{t=1}^n \frac{CF_0(1+g_S)^t}{(1+r)^t} + \frac{CF_0(1+g_S)^n(1+g_L)}{(1+r)^n(r-g_L)}$$

where:
- $V_0=$ Value of Equity (if cash flows to equity are discounted) or Firm (if cash flows to firm are discounted)
- $CF=$ Cash Flow in period t; Dividends or FCFE if valuing equity; FCFF if valuing firm
- $r=$ Cost of Equity (if discounting Dividends or FCFE) or Cost of Capital (if discounting FCFF)
- $g_S=$ Expected high growth short-term rate for the initial period
- $g_L=$ Expected sustainable growth long-term rate for the next period

Suitable for companies that are not expected to grow at a constant rate over time. These companies tend to be high-growth initially and become stable after a couple of years.
