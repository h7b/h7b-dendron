---
id: y0xnookb0xf0ifb3kaal0t1
title: Discounted Cash Flow Model
desc: ''
updated: 1650321983345
created: 1647317532092
---
# Discounted Cash Flow Model
ref: 
- [Investopedia](https://www.investopedia.com/terms/d/dcf.asp)
- [Aswath Damodaran | Session 2: Intrinsic Value - Foundation](https://www.youtube.com/watch?v=8vYQpWXQ5hE&list=PLUkh9m2BorqnKWu0g5ZUps_CbQ-JGtbI9&index=2)
- [Aswath Damodaran | Discounted Cashflow Valuation: Equity and Firm Models](https://people.stern.nyu.edu/adamodar/pdfiles/ovhds/dam2ed/dcfveg.pdf)
- [Aswath Damodaran | Dividend Discount Models](http://pages.stern.nyu.edu/~adamodar/pdfiles/valn2ed/ch13.pdf)
- [SimplyWallSt | Simply Wall St Company Analysis Model](https://github.com/SimplyWallSt/Company-Analysis-Model/blob/master/MODEL.markdown)

Discounted cash flow (DCF) analysis attempts to figure out the value of an investment today, based on projections of how much money it will generate in the future.

![dcf-model](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-03-21_230130_Hml7ZRE5b.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1647900103621){max-width: 300px, display: block, margin: 0 auto}

## Formula

In general,

$$Value = \frac{CF_1}{(1+r)^1} + \frac{CF_2}{(1+r)^2} + ... + \frac{CF_n}{(1+r)^n}$$

where
- $CF =$ the cash flow for the given year
  - $CF_1 =$ the cash flow for the 1st year
  - $CF_2 =$ the cash flow for the 2nd year
  - $CF_n =$ the cash flow for the year $n^{th}$
- $r =$ the discount rate
  - Companies typically use the weighted average cost of capital (WACC) for the discount rate, because it takes into consideration the rate of return expected by shareholders

## What DCF Can Tell You

The purpose of DCF analysis is to estimate the money an investor would receive from an investment, adjusted for the time value of money. The time value of money assumes that a dollar today is worth more than a dollar tomorrow because it can be invested.

## Variations of DCF
ref: [Aswath Damodaran](https://pages.stern.nyu.edu/~adamodar/New_Home_Page/lectures/basics.html), [Simply Wall St Help Center](https://support.simplywall.st/hc/en-us/articles/360001741016-How-is-fair-value-calculated)

### Which DCF model to choose?

The fundamental choices for DCF valuation:
- Cashflows to Discount
    - Dividends
        - for firms which pay dividends (and repurchase stock) which are close to the Free Cash Flow to Equity (over a extended period)
        - for firms where FCFE are difficult to estimate (Example: Banks and Financial Service companies)
    - Free Cash Flows to Equity (FCFE)
        - for firms which pay dividends which are significantly higher or lower than the Free Cash Flow to Equity. (What is significant? ... As a rule of thumb, if dividends are less than 75% of FCFE or dividends are greater than FCFE)
        - for firms where dividends are not available (Example: Private Companies, IPOs)
        - for firms which have stable leverage, whether high or not, and
        - if equity (stock) is being valued
    - Free Cash Flows to Firm (FCFF)
        - for firms which have high leverage, and expect to lower the leverage over time, because
            - debt payments do not have to be factored in
            - the discount rate (cost of capital) does not change dramatically over time.
        - for firms for which you have partial information on leverage (eg: interest expenses are missing..)
        - in all other cases, where you are more interested in valuing the firm than the equity.
- Expected Growth. Use the growth model only if cash flows are positive
    - Stable Growth
    - Two Stages of Growth: High Growth -> Stable Growth
        - Use the two-stage growth model if the firm is growing at a moderate rate ( within 8% of the stable growth rate)
    - Three Stages of Growth: High Growth -> Transition Period -> Stable Growth
        - Use the three-stage growth model if the firm is growing at a high rate ( more than 8% higher than the stable growth rate)
- Discount Rate: should be consistent with the cash flow being discounted
    - Cash Flow to Equity -> Cost of Equity
    - Cash Flow to Firm -> Cost of Capital
- Base Year Numbers
    - Current Earnings / Cash Flows
    - Normalized Earnings / Cash Flows

Fig: The building blocks of Valuation

![building-blocks-of-valuation](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-04-09_000324_X5I-DEaP8.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1649455494781){max-width: 300px, display: block, margin: 0 auto}

#### Three stages of Growth

![[notes.tutorial.finance.stock-valuation.dcf-model.three-stages-of-growth#three-stages-of-growth,1]]

#### Summary - DCF model choice

![[notes.tutorial.finance.stock-valuation.dcf-model.summary-dcf-model-choice#summary---dcf-model-choice,1]]

### DCF model for Firm with stable growth

![[notes.tutorial.finance.stock-valuation.dcf-model.gordon-growth-model#dcf-model-for-firm-with-stable-growth,1]]

#### Related readings

- pp. v3_440 - v3_448. Section *3 The Gordon Growth Model*. Book *2022 CFA Program Curriculum Level II Box Set Volumes 1-6*. Calibre Library id:"=1828".

### DCF model for Firm with two distinct stages of growth

![[notes.tutorial.finance.stock-valuation.dcf-model.two-stage-model#dcf-model-for-firm-with-two-distinct-stages-of-growth,1]]

#### Related readings

- pp. v3_456 - v3_461. Section *6.1 Multistage Dividend Discount Models: Two-Stage Dividend Discount Model and Valuing a non-dividend paying company*. Book *2022 CFA Program Curriculum Level II Box Set Volumes 1-6*. Calibre Library id:"=1828".

### DCF model for Firm with three distinct stages of growth

aka three-stage growth model.

#### H-model

![[notes.tutorial.finance.stock-valuation.dcf-model.h-model#h-model,1]]

#### Three-Stage Model

![[notes.tutorial.finance.stock-valuation.dcf-model.three-stage-model#three-stage-model,1]]

#### Related readings

- pp. v3_461 - v3_461. Section *7 The H-model and three-stage Dividend Discount Model*. Book *2022 CFA Program Curriculum Level II Box Set Volumes 1-6*. Calibre Library id:"=1828".

### Excess Returns Model

![[notes.tutorial.finance.stock-valuation.dcf-model.excess-returns-model#excess-returns-model,1]]

### Adjusted-Funds-From-Operations (AFFO) 2-Stage Discounted Cash Flow Model

![[notes.tutorial.finance.stock-valuation.dcf-model.affo-model#adjusted-funds-from-operations-affo-2-stage-discounted-cash-flow-model,1]]

### [[Dividend Discount Model (DDM)|notes.tutorial.finance.stock-valuation.dividend-discount-model]]

Suitable for companies that consistently pay out a meaningful portion of their earnings as dividends.
