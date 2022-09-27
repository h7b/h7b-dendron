---
id: kOJzZYotr90UM6tJVWKez
title: Usage Metrics
desc: ''
updated: 1653347605376
created: 1641774705630
---
# How do you evaluate and define success of BI team?

ref: 
- [powerbi.tips | Standardizing KPI’s around a Business Intelligence Team](https://powerbi.tips/2021/05/standardizing-kpis-around-a-business-intelligence-team/), 
- [powerbi.tips | Custom usage metrics reporting](https://powerbi.tips/2017/11/custom-usage-metrics-reporting/)

## Monitor how often your dashboard or report is being viewed

![report-usage-metrics](https://powerbi.tips/wp-content/uploads/2017/11/Final-Report.png){max-width: 300px, display: block, margin: 0 auto}

## Evaluating Performance of Power BI team

3 elements of success
- Adoption
    -  we are defining adoption as the maturity, growth, and reliance an organization has on their data via Power BI
- Value / Time
    - the ability to validate and choose to work on impactful and value-added reports is essential
    - are the reports that are being developed and deployed providing the expected insights and information to an organization?
- Data Quality
    - If users cannot trust the data in Power BI reports, that both reverts adoption and users will find other means to get their data
    - BI teams must be able to monitor how up-to-date published reports are, and ensure that the content that is available is current and accurate

Example KPI for each success
- Adoption
  - Rolling 14 Days / 30 Days Report Views
    - shows your top reports on a 2 week and month period, and compare with the previous 14 / 30 day period
    ![rolling-30-day-report-view](https://powerbi.tips/wp-content/uploads/2021/05/image-4.png){max-width: 300px, display: block, margin: 0 auto}
  - Active Users (Weekly, Monthly)
  - User Distribution by Report
    - for your top report, try to track the 20% users, and how much of total views they make up for an entire user base
    - By this, you can identify power users who are hoarding the majority of views for a given report
  - CSAT Scores, Feedback
    - customer satisfaction score survey
    ![survey-feedback](https://powerbi.tips/wp-content/uploads/2021/05/image-1.png){max-width: 300px, display: block, margin: 0 auto}
- Value / Time
  - New Reports Launched
    - track newly published reports
    - this is not a growth target
    - For example, a consistent small number may show a backlog. However, to high of a number may be saturating the overall experience for users
  - New Report Usage
    - keep an eye on the immediate interest from consumers for these newly published reports
  - Report Lifespan
    - the ability to understand the durability and longevity of reports is essential
    -  Are the reports being built showing value to consumers, not just once, but giving them a reason to return to the report on a consistent basis?
- Data Quality
  - Days Since Report Views
    - flagging unused report becomes an actionable KPI
    - Reports with consistent low `Days Since Views` should be treated with extra care if any updates are needed. Reports that have not been viewed in over 2 weeks may indicate loss of interest
    - Depending on the report, a BI Team can decide either to re-promote a report or assess if a report is not providing the value it should
    - tracking `Days Since Views` by User can provide value. 
      - Users who are "top customers" (i.e. those who have low `Days Since Views`) tell Authors who to reach out to or who knows what can enhance reports in the future
      - Users with high `Days Since Views` provide the ability for push-back for requests for new builds. For example, any colleague that may be requesting the most report builds but do not return to their reports give support to Project Managers that this may not be worth the value
    ![days-since-report-view](https://powerbi.tips/wp-content/uploads/2021/05/image-2.png){max-width: 300px, display: block, margin: 0 auto}
  - Reports Retired
    - any Report with over 45 `Days Since Views` should be strongly considered to be retired/archived   
    - The importance of keeping track of this KPI is all about quality for the consumer experience. This grows the trust and reliance on using Power BI for users