---
id: r1SEkbHOUE3EWKkd3cRWE
title: UBS Buy Wealthfront
desc: ''
updated: 1647565681097
created: 1643249308181
---
# Reading 2022-01-27

## Metadata

- Ref:: [Reuters](https://www.reuters.com/business/finance/ubs-buy-us-wealth-management-specialist-wealthfront-14-bln-2022-01-26/), [Hacker News](https://news.ycombinator.com/item?id=30088446)
- Title:: UBS Acquires Wealthfront for $1.4B
- Author:: Michael Shields
- Year of publication:: 2022
- Category:: News
- Topic:: #topic.investment
- Related:: 
  - [Vanguard | Target Retirement Funds](https://investor.vanguard.com/investment-products/mutual-funds/target-retirement-funds)
  - [Kubera | Track, manage, and secure all of your financial accounts in one place](https://www.kubera.com/)
  - [Tax-Loss Harvesting methodology](https://support.wealthfront.com/hc/en-us/articles/209348486-Tax-Loss-Harvesting)

## Notes from reading

> Note to self: this HN discussion is a joy to read. Since I always think that robo-advisor is the simplest way to invest for unsophisticated or average investors. The business model of robo wealth management is attractive for entrepreneur?

ref: [pyrrhotech](https://news.ycombinator.com/item?id=30089002)  
[Grizzly Bulls](https://grizzlybulls.com/), algotrading models to help tackle the challenge of when to hedge  
Managed accounts must first be set up on Interactive Brokers by the client, with a margin account + futures trading permission. Then a second user must be added with Limited Trading Authorization. Interactive Brokers has some standard forms to establish the contract. Once all that's set up, I run a parallel instance of my bot with your account in the cloud

ref: [Izrs](https://news.ycombinator.com/item?id=30090148)  
robo-advisor wealth management service providers are interesting and innovative

I'll preface by saying that I have been talking to a lot of financial planners (at top-tier institutions). They basically set you up with a good set of ETFs, hedge funds, etc. and rebalance occasionally. Sometimes they do tax-loss harvesting. They also provide a few other nice little services. But at the end of the day, their fees are over 1% unless you have an ultra high net-worth.

In comparison, Wealthfront can automate huge strategies for a fraction of the cost (0.25%). For example:

- Direct Indexing (invest in an index by buying the stocks directly instead of a fund)

- Automatic investing, rebalancing, and tax-loss harvesting (including TLHing individual stocks within an index when paired with direct indexing)

- Coordinating trades between retirement and taxable accounts for optimal tax savings

- Smart beta (a custom weighted indexing algorithm)

Yes, a financial planner can do all of this (although most don't). But when they do, they just use automated software to do it. It would be impossible to implement these strategies manually. So why even go with a financial planner when Wealthfront does the same thing, but better/cheaper?

ref:[maxclark](https://news.ycombinator.com/item?id=30091380)  
What caused me to leave?

- They aren't global portfolio aware. Bonds belong in tax advantaged accounts, then taxable. If you've maxed out your 401k/IRAs in Bonds that $ as an absolute percentage should be accounted for in your taxable portfolio construction.

- They don't let you opt out of asset classes. Aka I don't want additional REITs because I have RE exposure already.

- They overly hype tax loss harvesting. It's good to have, but a byproduct of portfolio management not the goal.

- They launched and pushed risky products as a way to increase their fees.

Once you understand what's going on under the hood this isn't complicated to manage yourself with a few ETFs/MFs.

(The direct indexing is awesome and would love to have that back)

ref: [zie](https://news.ycombinator.com/item?id=30091787)
- Edward Jones will do it for you for ~ 2%/yr, which is ridiculously high.
- Any of the big banks or brokerages will do it for less than Edward Jones.
- Almost any financial advisor will do it for about 1%/yr in fees(not ridiculously high, but not remotely cheap) or fee-based for a few hundred an hour with a 1st time setup of $4-10k, more than $10k is unreasonable.
- The robo advisors(of which their are dozens with basically identical products, generally charge 0.3%/yr, some like Vanguard include Financial Advisor services.
- At least one firm will do it for $200 first year and $100/yr after that, regardless of the balance of your accounts, and provide financial & tax planning/advice/etc included. They do require a little work on your part. I'm actively looking for more subscription based advisors like this, please PM me!
- Bogleheads.org will do it for free as long as you follow their template.

ref: [mushufasa](https://news.ycombinator.com/item?id=30090338)  
Many people who start off with Robos like Wealthfront actually leave once their net worth rises and pay more for human advisors.
If you need to invest a small/decent amount of money into stocks, Robos work wonderfully. It's a mass production angle -- good quality service at lower cost to many people; the Ford Model T of investing. Early robot just had a couple of investment options, and now there are more options but the same concept of limited choice at scale (Mustangs, Minvans, Trucks in my example)

Once you have estate planning and complicated tax issues, human advisors provide a lot of guidance to people that is hyper specific to you and your location / niche, which Robos just don't cover. Wealthfront, for example, won't arbitrate a dispute between beneficiaries of a family trust.

I think lawyers are a good comparison here. If you need some standard cookie-cutter incorporation docs, there's a bunch of websites where you can get some core documents for free or a few hundred dollars. But if you're afraid of making the wrong choice, or if you're in a situation that goes beyond the common scenarios (like M&A), then you hire a lawyer to provide you personalized advice.

ref: [matteotom](https://news.ycombinator.com/item?id=30090666)  
I know someone who's been doing wealth management for like 20 or 30 years now. Based on what they've told me, I'd separate clients roughly into 3 categories:
1. people who don't want to think about it - they pay for everything to be taken care of properly

2. people who want to be wined and dined - they end up paying to be taken out to dinner a few times a year and hear about what the firm is doing to survive bear markets and how they're taking advantage of bull markets

3. people who think they're smarter than everyone and want to direct everything - these people are probably moving to more self serve options, but plenty still want to tell a human what trades to make

Also at a certain net worth, tax and estate planning is a huge part of the work.

ref: [dnadler](https://news.ycombinator.com/item?id=30091940)  
a what-if analysis for scenarios from [Retirement calculator](https://lunchmodel.com/lmrc/scenario)

ref: [mbesto](https://news.ycombinator.com/item?id=30093079)  
boglehead here. Switched off of Wealthfront awhile back. AFAIK they wouldn't outperform a three-fund portfolio.
I actually wouldn't mind a platform that uses my brokerage as a backend and lets me do % allocations on 3~4 funds, automatically identifies rebalance opportunities and tax loss harvesting. Basically nudging me like 3~5x per year. I'd pay a flat fee to do that.

ref: [whitej125](https://news.ycombinator.com/item?id=30090127)  
Wealthfront (and this goes for the rest of Wall Street) are analog businesses.
They thrive on mass producing a fixed set of products. Those products are ETFs, Mutual Funds... or in Wealthfront's case... a rebalancing strategy based on a 1960's white paper called Modern Portfolio Theory.

Each of these players spends a ton trying to mass market these products. You have financial advisors pitching mutual funds, asset managers shilling the virtue of their shiny new ESG ETFs... and robo-advisors all promising a set-it-and-forget-it panacea. Wealthfront got commoditized. Betterment at first... but then the discount brokers came in (Vanguard, Fidelity, etc) and just had a much more effective channel (advisors!) to the end investor. If you are just selling a singular product and that product is successful, you are going to get copied and beaten by competitors with better marketing channels.

Wall Street will some day transform from an analog industry of mass production to a digital one of mass personalization. The building blocks for said transformation are slowly becoming ubiquitous (fractional shares support, commission free trading, etc). Super excited to watch this happen.

ref: [acomms](https://news.ycombinator.com/item?id=30089239)
1. These (robo-advisor) target the large majority of people with no will or interest in researching/picking/managing their own ETF investments. 
2. Robo advisers re-balance your ETF portfolio (in much the way an individual ETF would)

