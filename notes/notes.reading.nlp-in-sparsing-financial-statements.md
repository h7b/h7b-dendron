---
id: LrQYunYjzxQaNFWM
title: NLP in Sparsing Financial Statements
desc: ''
updated: 1640701418057
created: 1626869623004
---
# Interesting projects that use Natural Language Processing (NLP) to sparse info from financial statements

## [Bedrock AI](https://bedrock-ai.com/)

- Interesting dicussion of their product in [Hacker News](https://news.ycombinator.com/item?id=27893182)
- They use machine learning (NLP) to extract hard-to-find information and assess risk in public company reports (SEC filings). Their platform is used by investors to improve portfolio returns and mitigate downside risks.
- Context: Most public company data is unstructured and textual. Because relevant information is hard to find, a lot of corporate data is radically underused, to the detriment of investors. For example, their research shows it can take 12-18 months for corporate malfeasance to be incorporated into stock price after clear warning signs appear in financial text. Hard-to-find information that they extract includes accounting and governance choices, product defects, regulatory issues, customer/market reliance and much more.
- Their competitors: [AlphaSense](https://www.alpha-sense.com/), [Sentieo](Sentieo), [InsiderScore](https://www.insiderscore.com/), [footnoted](https://footnoted.com/)

## [Elect.us](https://eclect.us/)
- side project on Hacker News
- summarize SEC filings and display the clusters that have a high correlation with non standard price deviation in the next 20 days

## [Last10k](https://last10k.com/)
- Parse SEC filings for readable information
- This is a side project, appeared in [Hacker News](https://news.ycombinator.com/item?id=16407806)

## [Quantale](https://quantale.io/)
- a web-based Bloomberg Terminal alternative and they monitor SEC filings in real-time to show them to users
- they provide not only Financial and newsmedia data but also real-time data from SEC, Reddit, and Twitter.
- some of their current features
Along with that, additional features include:
    - Top trending stocks from the internet in real-time
    - Sentiment of the discussions using a pytorch model.
    - Ability to save posts(reddit, twitter, news headline, sec filings)
    - Ability to create watchlist to watch and monitor a group of tickers like SPACs.
- Similar tools: [Gbear.trade](https://gbear.trade/), [HypeEquity](https://app.hypeequity.com/monitor), [Gamestonk Terminal](https://gamestonkterminal.netlify.app/)

> Note: How can we adapt these business model to Vietnam financial market? Since even HOSE didn't implement a standard for filings like EDGAR system of SEC. AFAIK, HOSE use pdf format for filings
