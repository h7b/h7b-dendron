---
id: acipw5ba0456xp173rcbtbu
title: Stablecoin
desc: ''
updated: 1661177629662
created: 1654651956435
tags: topic.cryptoasset
---
# Stablecoin

ref: [Binance Academy](https://academy.binance.com/en/articles/what-are-stablecoins)

## Overview

A stablecoin is a cryptoasset pegged to an asset that has a stable price, such as a fiat currency or precious metal. Stablecoins were developed to avoid the high levels of volatility common in the cryptocurrency market.

There are three types of stablecoin: fiat-backed, crypto-backed, and algorithmic.

## How do stablecoins work?

Creating a coin that tracks another commodity’s price or value requires a pegging mechanism. There are multiple ways to do this, and most rely on another asset acting as [collateral](https://academy.binance.com/en/glossary/collateral). Some methods have proved more successful than others, but there is still no such thing as a guaranteed peg.

### Fiat-backed stablecoins

- A fiat-backed stablecoin keeps a fiat currency, such as USD or GBP, in reserves
- Users can then convert from fiat into a stablecoin and vice versa at the pegged rate
- If the price of the token drifts from the underlying fiat, arbitrageurs will quickly bring the price back to the fixed rate
    - Let’s say BUSD is trading above one dollar. Arbitrageurs turn US dollars into BUSD and sell it for more on the market. This increases the supply of BUSD for sale and lowers the price to one dollar again
    - If BUSD trades below one dollar, traders purchase BUSD and convert it to USD. This increases demand for BUSD, raising its price back to one.

### Crypto-backed stablecoins

- Crypto-backed stablecoins work in a similar way as fiat-backed stablecoins. But instead of using dollars or another currency as reserves, we have cryptocurrencies acting as collateral
- As the crypto market is highly volatile, crypto-backed stablecoins usually over-collateralize the reserves as a measure against price swings
- Crypto-backed stablecoins use smart contracts to manage minting and burning. This makes the process more reliable as users can independently audit the contracts
- Some crypto-backed stablecoins are run by [Decentralized Autonomous Organizations](https://academy.binance.com/en/articles/decentralized-autonomous-organizations-daos-explained) (DAOs), where the community can vote for changes in the project
- Let’s look at an example
    - To mint $100 of a [[DAI|notes.daily.2022-06-06.makerdao.dai]] pegged to USD, you will need to provide $150 of crypto working at 1.5x collateral. Once you have your DAI, you could transfer it, invest with it, or simply keep it
    - If you want your collateral back, you’ll need to pay back the 100 DAI. However, if your collateral drops below a certain collateral ratio or the loan’s value, it will be liquidated
    - When the stablecoin is below $1, incentives are created for holders to return their stablecoin for the collateral. This decreases the supply of the coin, causing the price to rise back to $1
    - When it’s above $1, users are incentivized to create the token, increasing its supply and lowering the price
    - DAI is one example, but all crypto-backed stablecoins rely on a mix of [game theory](https://academy.binance.com/en/articles/game-theory-and-cryptocurrencies) and on-chain algorithms to incentivize price stability.

### Algorithmic stablecoins

- Algorithmic stablecoins take a different approach by removing the need for reserves. Instead, algorithms and [smart contracts](https://academy.binance.com/en/articles/what-are-smart-contracts) manage the supply of the tokens issued. This model is much rarer than crypto or fiat-backed stablecoins and more challenging to run successfully
- Essentially, an algorithmic stablecoin system will reduce the token supply if the price falls below the fiat currency it tracks. This could be done via locked staking, burning, or buy-backs. If the price surpasses the value of the fiat currency, new tokens enter into circulation to reduce the stablecoin's value
- A notorious example is the [collapse of algorithmic stablecoin UST and its crypto-collateral LUNA](https://news.ycombinator.com/item?id=31371900) in 2022