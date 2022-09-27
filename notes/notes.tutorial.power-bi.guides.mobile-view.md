---
id: LjnlDxgNeyJVDpW89YYgn
title: Build reports for the Power BI Mobile app
desc: Build reports for the Power BI Mobile app
updated: 1661680151523
created: 1641774268415
---
# Building reports for the Power BI Mobile app

ref: [powerbi.tips](https://powerbi.tips/2021/09/a-better-way-to-mobile/), [Microsoft Docs](https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-create-mobile-optimized-report-about)

Mobile users can view any Power BI report page in the Power BI mobile apps. However, reports designed for use on a computer can be difficult to read and interact with on phones.
![example](https://docs.microsoft.com/en-us/power-bi/create-reports/media/power-bi-create-mobile-optimized-report-about/power-bi-mobile-optimized-report-portrait-landscape.png){max-width: 300px, display: block, margin: 0 auto}

2 approaches:
- Use `mobile layout view` for portrait only
    ![mobile-layout](https://powerbi.tips/wp-content/uploads/2021/09/image-5.png){max-width: 300px, display: block, margin: 0 auto}
- Create a report page with custom dimensions using formatting pane, where the width of a page from 600 to 800 pixels, and take care of UI/UX of report
    ![cutom-dimension](https://powerbi.tips/wp-content/uploads/2021/09/image-7.png){max-width: 300px, display: block, margin: 0 auto}

## Related resources:

- [Microsoft Docs | Mobile layout view](https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-create-mobile-optimized-report-mobile-layout-view?tabs=powerbi-desktop)
- [Microsoft Docs | Optimize a dashboard for mobile phones - Power BI](https://docs.microsoft.com/en-us/power-bi/create-reports/service-create-dashboard-mobile-phone-view)