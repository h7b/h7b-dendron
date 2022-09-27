---
id: f3jh8ug6k58re4fgm9maye6
title: How to Assess the Risk of Lending
desc: ''
updated: 1655276548544
created: 1655275875657
---
# Reading 2022-06-15

## Metadata

- Ref:: [Bankless](https://newsletter.banklesshq.com/p/how-to-assess-the-risk-of-lending)
- Title:: How to Assess the Risk of Lending to a Protocol
- Author:: Ryan Sean Adams
- Year of publication:: 2019
- Category:: Blog
- Topic:: #topic.cryptoasset
- Related:: 

## Notes from reading

A framework for assessing the risks of lending to a money protocol.

Understanding risk is to break it down into two main factors, **likelihood** and **consequence**.
- Likelihood - the chance that the risk actually occurs. Is it a relatively common situation, or is it a rare event that may not ever happen?
- Consequence - what happens if the event was to occur. Will it result in an insignificant or small financial loss, or a catastrophic failure leading to the loss of your entire investment.

![risk-framework](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7fb22ddc-f46e-4d55-b7bb-83754ff200e1_529x444.png){max-width: 300px, display: block, margin: 0 auto}

Risk framework:
- **Avoid**: Anything with a high likelihood and high consequence should be avoided, the risk cannot adequately be managed or insured for a reasonable price. This is “scam” territory
- **Manage**: High likelihood items with low consequence form part of day-to-day management for you to take responsibility for or pay someone to manage on your behalf. For example, optimising returns due to changing interest rates between various DeFi protocols
- **Ignore**: Low likelihood, low consequence items are mostly not worth worrying about. The time and cost of management is probably not worth the effort so it is perfectly reasonable to ignore them
- **Insure**: The remaining category is the low likelihood, high consequence items where you should insure where possible to improve your risk adjusted return. At the very least you should understand the high consequence scenarios and what might cause them

The three types of risk in a lending protocol:
- **Technical Risk**
    - The risk of the smart contracts not behaving as intended by the developers
    - Audits, extensive testing, formal verification as well as how “battle-tested” the contracts are, are factors that can reduce technical risk
    - A simple measure like funds held x time held could be a reasonable proxy for technical risk noting that even heavily battle-tested contracts have had issues in the past
- **External Risk**
    - The risk of external information influencing how the smart contracts operate to the detriment of other users
    - For example, an oracle could provide malicious data, and administrator could change a system parameter or governance procedures could be co-opted
    - This is often difficult to assess without a certain level of technical expertise but generally there have been articles written on the major platforms that describe how much control the administrators have and where the external factors are. Some platforms have started introducing time-locks on governance controls which may allow users to take funds out before any changes take place, and some platforms have no external risk at all, like Uniswap
- **Economic Incentive Failure Risk**
    - Many smart contract systems, especially in the DeFi space, rely on economic incentives to encourage network participants to perform certain actions. These incentives could fail to encourage the right behaviour or not be adequate enough leading to other users being adversely impacted
    - For example, the incentives in the [[MakerDAO|notes.daily.2022-06-06.makerdao]] smart contracts could be too aggressive and the DAI <> USD peg could break if the ETH price drops too far, too quickly

Once you understand the risks you could rate them according to a more detailed matrix and then decide how you will actually deal with the risks. Whether that be avoid, manage, ignore or insure.

![risk-matrix](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F61e1e665-b173-4f1f-a28d-185c29eae364_1178x475.png){max-width: 300px, display: block, margin: 0 auto}