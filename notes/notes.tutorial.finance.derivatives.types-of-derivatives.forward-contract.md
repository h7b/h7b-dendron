---
id: au3tyt1mlxzlhxpss3fm8wy
title: Forward Contract
desc: ''
updated: 1650592971796
created: 1650583344030
---
# Forward Contract

A forward contract is an **over-the-counter derivative** contract in which two parties agree that 
- one party, the buyer, will purchase an underlying asset 
- from the other party, the seller, 
- at a later date and at a fixed price they agree upon when the contract is signed.

In addition to agreeing on the price at which the underlying asset will be sold at a later date, the two parties also agree on several other matters, such as 
- the specific identity of the underlying, 
- the number of units of the underlying that will be delivered,
- and where the future delivery will occur.

Forward contracts—and indeed all derivatives—take (derive)
their payoffs from the performance of the underlying asset. To illustrate the payoff of a forward contract, start with the assumption that we are at time $t = 0$ and that the forward contract expires at a later date, time $t = T$ [^1]. The spot price of the underlying asset at time $0$ is $S_0$ and at time T is $S_T$. Of course, when we initiate the contract at time $0$, we do not know what $S_T$ will ultimately be. Remember that the two parties, the buyer and the seller, are going long and short, respectively.

[^1]: Such notations as $t = 0$ and $t = T$ are commonly used in explaining derivatives. <br> To indicate that $t = 0$ simply means that we initiate a contract at an imaginary time designated like a counter starting at zero. <br> To indicate that the contract expires at $t = T$ simply means that at some future time, designated as $T$, the contract expires. <br> Time $T$ could be a certain number of days from now or a fraction of a year later or $T$ years later. For simplicity, just now assume that $t = 0$ and $t = T$ are two dates—the initiation and the expiration—of the contract.
- At time $t = 0$, the long and the short agree that the short will deliver the asset to the long at time $T$ for a price of $F_0(T)$. The notation $F_0(T)$ denotes that this value is established at time $0$ and applies to a contract expiring at time $T$. $F_0(T)$ is the **forward price**.
- So, let us assume that the buyer enters into the forward contract with the seller for a price of $F_0(T)$, with delivery of one unit of the underlying asset to occur at time $T$. Now, let us roll forward to time $T$, when the price of the underlying is $S_T$. The long is obligated to pay $F_0(T)$, for which he receives an asset worth $S_T$.
- If $S_T > F_0(T)$, it is clear that the transaction has worked out well for the long. Thus, the contract effectively pays off $S_T ‒ F_0(T)$ to the long, which is the value of the contract at expiration.
- The short has the mirror image of the long. He is required to deliver the asset worth $S_T$ and accept a smaller amount, $F_0(T)$. The contract has a payoff for him of $F_0(T) ‒ S_T$, which is negative.

Forward contracts need not specifically settle by delivery of the underlying asset. They can settle by an exchange of cash. These contracts—called **non-deliverable forwards** (NDFs), **cash-settled forwards**, or **contracts for differences** (CFDs)—have the same economic effect as do their delivery-based counterparts.

Exchange-traded variants of forward contracts are called [[futures contracts or just futures|notes.tutorial.finance.derivatives.types-of-derivatives.futures-contract]].