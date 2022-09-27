---
id: nm5o9qom86y55osxm5p7rk8
title: Payment for Order Flow
desc: ''
updated: 1651453451787
created: 1651451917646
---
# Reading 2022-05-02

## Metadata

- Ref:: [Alpaca](https://alpaca.markets/learn/love-it-or-hate-it-inside-payment-for-order-flow-and-commission-free-trading-apps/)
- Title:: Love it or Hate it: Inside Payment for Order Flow and Commission-Free Trading Apps
- Author:: Alpaca Team
- Year of publication:: 2021
- Category:: Blog
- Topic:: #topic.investment
- Related:: 

## Notes from reading

Payment for Order Flow (PFOF) (also known as or revenue from order flow, or market maker rebates) is worth paying attention to when it comes to understanding how the U.S. stock market works.

Certain markets, such as the U.K. have banned payment for order flow.

PFOF means that retail brokerages are compensated by market makers for sending clients’ orders to the market maker instead of the stock exchange.

This "rebate" is usually fractions of a penny for every share bought or sold. 
- Some of the top market makers include Virtu, Citadel Securities, Susquehanna, Jane Street, Two Sigma, and UBS, 
- while online brokerages include Charles Schwab, Interactive Brokers, Robinhood, Alpaca, TD Ameritrade, Webull, and more.

### Why is Payment for order flow (PFOF) Controversial?

Critics argue that 
- PFOF creates a conflict of interest by giving firms an incentive to encourage clients’ frequent trading. The more clients trade, the larger the order flow a brokerage can sell
- your orders leaked to front-running high-frequency traders in secretive kickback schemes

But consider these facts
- Frontrunning is illegal. Laws may not always stop people and companies from doing bad things, but why would a market-making firm, which is typically a profitable enterprise, risk its business to front-run a retail order?
- [Regulation NMS](https://www.investopedia.com/terms/r/regulation-nms.asp) requires your order to be filled at a price equal to or better than the [National Best Bid and Offer (NBBO)](https://www.investopedia.com/terms/n/nbbo.asp), which is the best available displayed price across all exchanges.

### Why would a market maker pay your broker for your order?

Market makers are willing to pay for your order because on average, they can profit from it. The reality is that retail order flow is more diverse and less toxic than institutional flow [^1].

[^1]: Bank of Canada. ["Staff Working Paper/Document de travail du personnel 2016-20 - Retail Order Flow Segmentation"](https://www.bankofcanada.ca/wp-content/uploads/2016/04/swp2016-20.pdf). Accessed on 2022-05-02

Whether you are crossing the spread or waiting patiently to get filled, the wholesale market maker and your broker can generate a tiny profit on your order, which helps offset their costs and provide you with their services.
- As an example, imagine that you send a [market order](https://www.investopedia.com/terms/m/marketorder.asp) to buy 100 shares of a stock and that this order is routed to a market maker. The wholesaler receiving your order knows that:
    - The average retail order does not have more shares behind and hence will not impact price significantly
    - The average retail order is uncorrelated with past and future order flow
    - The average retail order does not have a short-term positive expectation
- As another example, imagine that you send a [limit order](https://www.investopedia.com/terms/l/limitorder.asphttps://www.investopedia.com/terms/l/limitorder.asp) to your broker. This is a passive order that adds liquidity to the order book and is only executed when an aggressive counterparty interacts with it. The wholesaler or your broker themselves may route this order to an exchange that will pay them a small rebate (fractions of a cent per share) if it is filled. The arrangement of receiving rebates for passive fills and paying fees for aggressive fills is the predominant access fee schedule for U.S. equity exchanges and is known as the [maker-taker model](https://www.investopedia.com/articles/active-trading/042414/what-makertaker-fees-mean-you.asp)

Under Securities and Exchange Commission [Rule 606](https://www.ecfr.gov/current/title-17/chapter-II/part-242/subject-group-ECFRac68bdd026a46db/section-242.606), all broker-dealers are required to provide publicly available quarterly reports on their order routing practices. Additional information on Rule 606 can be found in the Commission’s adopting release, available at [here](https://www.sec.gov/rules/final/2018/34-84528.pdf).

Robinhood reported that PFOF and transaction rebates represented 75% of its total revenue for the year ended December 31, 2020 [^2].

[^2]: ["Form S-1 REGISTRATION STATEMENT Robinhood Markets, Inc.", p. 194](https://www.sec.gov/Archives/edgar/data/1783879/000162828021013318/robinhoods-1.htm). Accessed on 2022-05-02