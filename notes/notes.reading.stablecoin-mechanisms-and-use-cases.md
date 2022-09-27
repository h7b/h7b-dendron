---
id: jxrpd7ntohv84cxg9yhwaef
title: Stablecoin Mechanisms and Use Cases
desc: Stablecoin Mechanisms and Use Cases
updated: 1656519698909
created: 1656378494030
---
# Reading 2022-06-28

## Metadata

- Ref:: [Bits about Money](https://bam.kalzumeus.com/archive/stablecoin-mechanisms-and-use-cases/)
- Title:: Stablecoin mechanisms and use cases
- Author:: Patrick McKenzie (patio11)
- Year of publication:: 2022
- Category:: Blog
- Topic:: #topic.cryptoasset
- Related:: [[notes.daily.2022-06-06.stablecoin]]

## Notes from reading

A stablecoin is designed to be a deposit (i.e. money) recorded in a slow database which is negotiable among other actors who use the same slow database. This compares to deposits at e.g. banks, which are typically recorded in a faster database and are negotiable either at the bank or, through the banking system, at other users of money.

Stablecoins are typically contrasted with other cryptocurrencies, such as Bitcoin, because their unit of account is linked to a government-issued currency (overwhelmingly, the U.S. dollar) rather than more speculative assets one could record in a ledger maintained in a slow database.

Uses of stablecoins
- moving money between cryptocurrency exchanges to assist with arbitrage
- A dominant use is actually collateralizing investments in popular products with embedded leverage, such as [Binance’s USDT/BTC perpetual futures contract](https://www.binance.com/en/futures/BTCUSDT)
- programmable money that can be easily operated on by smart contracts in “decentralized finance” (DeFi)
- stablecoins could be used to settle transactions

**Money market fund style stablecoins**
- A money market fund is a specialized form of investment vehicle designed to have the desirable characteristics of a deposit (liquidity on demand and virtually riskless) while having more yield than deposits do. This is typically achieved by having the money market fund invest in short-term high-quality commercial paper or government-backed securities.
- Now change the money market fund’s fast database to a slow database, make individual units of it movable without cashing out, and set the management fee to equal 100% of interest income. The papers are now diamonds. Or the money market fund is now a stablecoin.
- The money market model is, relative to other ways to construct stablecoins, boring. Boring is a feature! Boring means that the stablecoin operator can’t get seigniorage income through digital alchemy. Boring also means that the stablecoin is unlikely to see its value vaporized under conditions of market stress.

**Equity-backed stablecoins**
- Equity-backed stablecoins are sometimes called “algorithmic” stablecoins, to suggest they have the predictability of a well-operating computer program (on the way up) and blame the loss of billions of dollars on software rather than identifiable people (on the way down)
    - Say you have a business. That business has equity value. If that business also plugs into many counterparties, keeps a ledger of money it owes to counterparties, and allows those debts to be transferred via any mechanism, that business could theoretically function as a payments rail. The business could choose to do this via letters carried by courier, via a slow database, or via many other methods.
    - How does the business maintain confidence among its counterparties that its debts are always worth face value, even if it doesn’t actually pay those debts back in any given period? By reference to its equity value.
    - If you continue to believe that e.g. Netflix has a large equity value, and equity takes impairments before debt does, then a Netflix bond (or Netflix Dollar) should maintain its value, all else being equal. Matt Levine has a [[great explanation|notes.reading.expensive-stocks-make-for-good-bonds]] of this.
- Terra USD, which was vaporized earlier this month, was an equity-backed stablecoin. The equity was in the form of a sister token called Luna. Cryptocurrency enthusiasts sometimes like to feign ignorance about tokens being equity claims, principally as a form of regulatory arbitrage. Luna is worse-is-better equity; worse in that it has far less protections than equity, better in that it could be sold to retail without getting one put in jail (yet).
    - Why is Luna equity valuable? The argument was that Luna was an equity interest (“Utility token!” Quiet, you.) in the business that was the operation of the Terra slow database. Terra Labs and other parties would make the slow database available to software developers in return for ongoing fees, which would make Luna valuable for the same reason “sell an underwhelming database subscription with a complicated pricing model over time to developers in exchange for money” makes Oracle equity valuable.
    - Terra Labs added a feature to the slow database which would allow one to use the slow database to exchange Luna (equity) for Terra (the stablecoin) at par. If Terra traded below the $1 peg, arbitrageurs could buy it, redeem for Luna, sell the Luna (somewhere), and profit from the difference. If it traded above the peg, you could run that trade in reverse: buy cheap Luna, redeem for dear Terra, sell the Terra, now you’ve got more money than you started with.
    - Software company equity is more valuable when lots of people are doing interesting valuable things with the software.
    - So Terra Labs concocted the existence of an interesting valuable thing. They wrote a program using their slow database called Anchor. Anchor was an automated program to allow money lending.
    - There are many of these money lending program in DeFi land. Many of them use an aggressive growth hacking strategy, which is saying “If you use my program, I will give you equity in my company.” This strategy is commonly called “yield farming.” Anchor was very aggressive about this, promising 19.5% APY yields on their stablecoin. To use their program to get 19.5% yields you needed to buy into their database software, which made their database software seem to be more valuable, which caused the value of their equity to go up, which allowed them to redeem their own equity for more money to throw at user acquisition, which… created a Ponzi scheme.
    - In early May, Terra Labs announced that it was going to stop subsidizing users of its computer program. Users stopped using it, never having had any reason to use it other than collecting Terra Lab’s subsidy. This caused the perceived value of Luna equity to decline, which put pressure on the peg, which caused people to exit the pegged stablecoin, which decreased the use of the slow database and further hurt the implicit equity value of owning the slow database, which is a “death spiral.”

**Fraud-backed stablecoins**
- Tether. [Enough said](https://www.kalzumeus.com/2019/10/28/tether-and-bitfinex/).
- Tether pretend to be a money market style stablecoin, but just lie about it. Cover redemptions with other people’s money that you misappropriate. Spread the wealth around to co-conspirators both directly and by driving up the price of assets you mutually depend on.