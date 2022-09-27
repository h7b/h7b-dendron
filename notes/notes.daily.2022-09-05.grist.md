---
id: yzl5595o0mep27qtbgszsns
title: Grist
desc: 'Grist: flexibility of a spreadsheet with the robustness of a database'
updated: 1662508175723
created: 1662416683931
tags: cat.tut
---
# Grist

## Overview

[Grist](https://www.getgrist.com/) is an alternative that aim to dethrone [Airtable](https://www.airtable.com/), and claim to be better than a spreadsheet.
- [Pricing plan](https://www.getgrist.com/pricing/) starts at USD 8/month. With limited free tier for individuals
- Grist also has as a free version to self-host, which is called [Grist Core](https://github.com/gristlabs/grist-core/)

## My thoughts

This [Grist v. Airtalbe](https://www.getgrist.com/blog/grist-v-airtable/) article is not up-to-date, but still represent the general idea of the service provided by Grist.

![grist-v-airtable](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-09-06_002806_qBnXmVcnJ.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1662416939993){max-width: 300px, display: block, margin: 0 auto}

At the moment (2022-09-06), the free plan of Grist is now limited at 5k records per documents. A record is a row in a table. This limit applies to all rows across all tables in one document. [^1]

[^1]: https://www2.getgrist.com/pricing

Grist has the widget which can be embedded into a website. Airtable is also available to be integrated into a webpage, but their loading time is much slower. [^2]

[^2]: https://support.getgrist.com/embedding/#embedding-grist

A Grist document can be exported (with all raw data and their relationship) as one `.grist` file, which is a sqlite database file. It can be read by any software that support sqlite or be imported back to Grist. In the world of spreadsheets, it helps for Grist documents to have a complete, standalone, downloadable, email-able representation.

Widgets in Grist (like dashboards) are exactly what NocoDB, Airtable, Baserow lack.

A column in Grist supports many data types. You can see the thumbnail of an attached image in the cell. [^3]

[^3]: https://support.getgrist.com/col-types/

The grist-core also inherit the soft limit at ~100k records from its Saas version, that helps things don't get sluggish. That number is based on experience with Grist running with the CPU and memory resources Grist give it in their hosted service. Though, when you self-host, you have an option to increase your server's performance to surpass this limit. [^4]

[^4]: https://community.getgrist.com/t/grist-as-database-backend-headless-cms-alternatives/586/6

## Related

- [Grist | Documentation](https://support.getgrist.com/)
- [Grist Feedback | Many-to-Any Relationships](https://community.getgrist.com/t/many-to-any-relationships/650/2)
    - a discussion in the community forum of Grist
    - it represents a solution to a [Configure, price and quote](https://en.wikipedia.org/wiki/Configure,_price_and_quote) software builder
    - it shows how to imitate the behavior of "conditional drop down list" in Grist
