---
id: 3bh6unip7ggu8rz8lk0ss1i
title: Q6
desc: Okxe Data Analyst
updated: 1663452377677
created: 1663281056793
---
# Q6 Business Question

## Question

Please propose your ideas on how to increase the MAU for OKXE. Your ideas should not be limited to data-related initiatives, but can also involve business programs or product changes.

## Answer

To increase the MAU, we need to understand 
- why your customers use your app
- what they’re looking to achieve

Paraphrasing into the marketing language, we need to know
- What goals are my users achieving within my app and web properties
- What steps are they taking to achieve those goals
- Where do those steps fall in terms of a conversion funnel or customer journey
- What are different ways of measuring active usage that are important to your marketing goals
    - why do we need different ways of measuring?
    - Because it’s impossible to create a single one-size-fits all definition of active, as several groups of users will have varying levels and types of engagement with your app.
    - Example of some common stats to track
        - Response to offers, deals, and promotions
        - Willingness to share feedback
        - Frequency of log-ins, by type of device and/or platform
        - Engagement with content (reads, reads to the end of a page, clicking links within text, pageviews per session, total time reading)
        - Sharing of content

Before proposing ideas on how to change, let's see what okxe is offering to its customer.

[okxe](https://www.okxe.vn/) is a dedicated marketplace platform for motorbike reselling. Current implemented features by okxe:
- search by bike category, brand
- have authorized/verified reselling partner program
- have a whistle-blower and escrow service called "Trạm Dịch Vụ OKXE"
- each product has clarified tags which describe the released year and the distance traveled by the vehicle
- cross-sell financial services: installment plan, bike insurance
- act as a market maker (via the collection program of used bikes), which create the liquidity, increase the transparency and reduce the hindrance of bike reselling market
- integrated chat feature in the main app.

In my opinion, okxe is doing great with their current offer on business side. However, I see some feasible enhancements on its product's UX, which possibly help to retain users.
- As a frequent user of many marketplace websites, what do I expect to see on the front page of this kind of website?
    - a big button (visually differentiated color palette) where I can click to propose my offer to sell
    - a big search box to buy, in which I can quickly
        - choose the category of bike
        - select the location of offers
        - set a dynamic price range
        - and see the total number of available product coming from my search query 
    - see what are my most 3 recent search queries
- On desktop version of website, there are so many wasted displaying spaces
    - a top ad-banner occupied 50% of the 1st loading frame
    - a news section listing article from blog is not necessary, and should not be promoted on the main website
- as a privacy-focused user, I'm not comfortable sharing my current location with any apps. The search box should at least has a filter option for location. The current way of hiding all search filter options under a separate modal which requires one more click to open is not good enough.
- I guess that the main website shares the code base with its mobile app. That may be the reason why the interactions become sluggish on both platforms (desktop and tablet/mobile). Long loading time when transitioning between products. Long loading time for product's photos. Scrolling is randomly lagged on mobile web version.

Within the data-related perspective, in order to increase the MAU, we should
- audit how customers have used our products via reporting by sessions and frequency of events
- know which are the risk of churning, for example via the trend line of number of actions per user per week
- know which leads have higher probability of converting into customers, via defining a Lead Scores
- know who are the power users of our product, again via the sessionized event-related data
- increase the gross merchandise volume, which is the total sales of merchandise transacting through our marketplace in a specific period

## Related

- [braze | What’s the Best Way to Define an Active User?](https://www.braze.com/resources/articles/best-way-define-active-user_id)
- [braze | Every Mobile Customer Is Unique—And So Are Their Customer Journeys](https://www.braze.com/resources/articles/mobile-customer-journey)
- [popsql | Finding Customers at Risk of Churning](https://popsql.com/sql-templates/support/finding-customers-at-risk-of-churning)
- [popsql | Creating Lead Scores in SQL](https://popsql.com/sql-templates/sales/creating-lead-scores-in-sql)