---
id: 707hc8wcas05asaa291ddxy
title: Why is using 1inch better than a DEX
desc: ''
updated: 1655161997877
created: 1655161694261
---
# Why is using 1inch better than a DEX (like Uniswap or Pancakeswap)?

ref: [1inch](https://help.1inch.io/en/articles/6200682-why-is-using-1inch-better-than-a-dex-like-uniswap-or-pancakeswap)

- Efficient routing
    - By design, 1inch uses a dynamic "aggregation" protocol. This is completely different from the AMM protocols of individual DEXes. Instead of executing transactions, it finds the cheapest rate amongst a multitude of Dexes (including Uniswap and Pancakeswap), and submits the transaction through that DEX. This means that if Sushiswap has a cheaper rate than Uniswap, 1inch will do the work for you and route your swap through Sushiswap.
- Transaction splitting
    - If you were to make a swap on an individual DEX (like Uniswap), your trade could only go through one single liquidity pool
    - With 1inch, your single trade can be split up and routed through multiple liquidity sources
- Gas optimization
    - cheaper gas fees than most of the leading DEXes