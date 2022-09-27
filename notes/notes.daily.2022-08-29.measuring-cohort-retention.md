---
id: 9v548skfxtvq4qd4h3bktml
title: Measuring Cohort Retention
desc: Measure cohort retention
updated: 1662302621030
created: 1662301449196
tags: cat.read
---
# How to measure cohort retention

ref: [lennysnewsletter](https://www.lennysnewsletter.com/p/measuring-cohort-retention)

A deep dive into the formulas, visualizations, and SQL you need to accurately measure and report on cohort retention.

It takes up to six months to nail accurate retention reporting.

Retention measures the ability of your product to keep users active over time. Retention for consumer businesses would have a different meaning than for enterprise, B2B, or B2C companies.

![retention-def](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F788ee8c2-6fc8-44fc-968b-ce92ac45c32c_2318x1112.png){max-width: 300px, display: block, margin: 0 auto}

A fundamental variable in calculating retention for most products is “active users.” I’d recommend using the main user action as the activity event.

![active-def](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4430235c-6770-46b1-b329-e83f6008f80f_2318x2316.png){max-width: 300px, display: block, margin: 0 auto}

Once your team agrees on what “active” means for your product, the next step is to segment your active users into free vs. paid. Your retention will have a different logic for each of these groups.
- A customer is defined as the person/group who is paying you
- A user is a person using the product
- In subscription products, oftentimes there are multiple users associated with a single customer. Or people are users before they are customers.

The next step in calculating retention is setting your timeline. What retention reporting type you should adopt?
- X-day retention
- Unbounded (rolling) retention 

X-day retention
- X-day (also known as N-day or bounded) tells you the percentage of users who come back on a specific day.
- is more appropriate for short-term analysis like measuring the onboarding funnel or marketing campaigns.
- This is the most conservative retention approach and will return you a lower retention percentage
- For example, for all users who join, what percentage return to your app on exactly day 14
- ![x-day-retention](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1ebda1bb-0adf-463c-b2e3-4b8b543e16c9_1456x1042.png){max-width: 300px, display: block, margin: 0 auto}

Unbounded retention
- tells you how many of your users got back on a specific day or later.
- is more useful for measuring long-term user behavior, especially if you want to segment your users into retention groups (6M, 9M, 1 year, 2 years).
- For example, for all new users who joined on a specific day, what percentage of users are using the product after 14 days (and not necessarily on day 14).
- If your goal is to match retention with your user churn, this is the way to go. The unbounded retention value for month 6 gives you the percentage of users who returned after month 6. Or unbounded retention is the inverse of churn (the higher the churn, the lower the retention, and vice versa).
- ![unbounded-Retention](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb0a226d8-6d58-4572-a70d-e5075a8d038e_1458x794.png){max-width: 300px, display: block, margin: 0 auto}

The best practice for reporting retention is `cohorts`. This chart shows how many users registered each week and how many of them were retained in each subsequent week. It is filtered to only “New Users.”
![cohorts](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F875a7a40-cabc-406c-b531-6fe972d41f35_1300x604.png){max-width: 300px, display: block, margin: 0 auto}