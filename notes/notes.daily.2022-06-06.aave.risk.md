---
id: 7niytg1n8ynvgcljzejelth
title: Aave's Risk Framework
desc: ''
updated: 1654837501682
created: 1654836666209
---
# [Aave's Risk Framework](https://docs.aave.com/risk/)

The documentation analyses the fundamental risks of the protocol and describes the processes in place to mitigate them

## [Asset Risk](https://docs.aave.com/risk/asset-risk/introduction)

- This documentation, developed by the Risk Management Team, focuses on the risk assessment for currencies supported by Aave
- The risk assessment considers market, counter-party and smart contract risks for the currencies selected for Aave protocol, aiming to contribute to higher risk standards within DeFi
- Risk factors
    - **Smart Contract risk**: focuses on the technical security of a currency based on its underlying code. If one of the supported currencies is compromised, collaterals will be affected, threatening the solvency of the protocol
    - **Counter-party risk**: assesses qualitatively how and by who the currency is governed. The counter-party risk is measured from the level of centralisation corresponding to the number of parties that control the protocol as well as the number of holders and the trust in the entity, project or processes
    - **Market risks**: are linked to the market size and fluctuations in offer and demand. These risks are particularly relevant for the assets of the protocol: the collateral. If the value of the collateral decreases, it might reach the liquidation threshold and start getting liquidated. The markets then need to hold sufficient volume for these liquidations
- Risk matrix as of 2021-09-24 ![risk-matrix](https://2799188404-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-M51Fy3ipxJS-0euJX3h%2F-MkNc-NUgQrM6fATQhcl%2F-MkNcJa1nJM3DGMNTtf7%2FScreenshot%202021-09-24%20at%2017.26.15.png?alt=media&token=78273046-2e88-407a-bc02-e4cb42f2c902){max-width: 300px, display: block, margin: 0 auto}

## [Liquidity Risk](https://docs.aave.com/risk/liquidity-risk/introduction)

- Aave is a liquidity protocol that enables borrowing different cryptoassets from the liquidity pools. Depositors receive aTokens, in exchange of cryptocurrency deposits
- The liquidity of the protocol is the availability of the capital to face business operations: borrowing amounts and redeeming aTokens. It is a key metric, as lack of liquidity will block business operations
- At any point in time, the liquidity of the protocol can be assessed through the utilisation ratio: the share of reserve that is currently borrowed for each currency
- In this section, we dive into Aave's liquidity risk by analysing the [historical availability of Aave's assets](https://docs.aave.com/risk/liquidity-risk/historical-utilization) and identify periods of lack of liquidity. Then we look at the [valuation of aTokens](https://docs.aave.com/risk/liquidity-risk/atoken-valuation), illiquid assets often suffer from illiquidity discounts due to the difficulty to find counterparties
    - The historical utilisation and aToken valuation help us assess the level of liquidity risk of the protocol. Once this risk is understood, we can put in place risk management techniques through the [borrow interest rate model](https://docs.aave.com/risk/liquidity-risk/borrow-interest-rate) and set up alternative sources of aToken liquidity.

## [Market Risk](https://docs.aave.com/risk/audits/gauntlet)

- Within decentralized finance (DeFi), borrowing protocols have four main risk factors:
    - Security risk
    - Governance risk
    - Oracle risk
    - Market risk
- There are four primary sources of market risk within the protocol:
    - Extreme downward price movement: Shocks to market prices of collateral that cause the contract to become insolvent due to under-collateralization
    - Asset illiquidity and liquidator inaction: Loss of liquidity in an external market place, leading to a liquidator being disincentivized to liquidate defaulted collateral
    - Cascading liquidations: liquidations lower external market prices which in turn lead to further liquidations (i.e. a deflationary spiral)
    - Slashing of the safety module: Insolvency of the safety module due to extreme events where multiple collateral types concurrently fail to be liquidated