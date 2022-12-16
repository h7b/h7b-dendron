---
id: 4aotslw3br0wz51gtts37oz
title: Web Scraping with Automa
desc: 'Web Scraping with Automa'
updated: 1671152284016
created: 1670953457793
tags: cat.tut
---
# Web Scraping with Automa

Originated from the interest of the performance of [[notes.daily.2022-09-19.investment-fund-vn]], I started to research how to crawl historical NAV data of multiple investment funds domiciled in Vietnam. It leads to the path of learning on [[notes.tutorial.web-browser-automation]]. This note covers my experience playing browser automation with [Automa](https://www.automa.site/).

## What is Automa?

[Automa](https://www.automa.site/) is a browser extension (available for Chromium-based and Firefox) that automate browser operations, from auto-fill forms, doing a repetitive task, taking a screenshot, to scraping data of the website.

This extension has a similar UX as [n8n](https://n8n.io/) or [zapier](https://zapier.com/). It visualizes the workflow with block and arrows.

The workflow can be imported/exported locally via `.json` file. Or it can also be hosted publicly in the [Marketplace](https://www.automa.site/marketplace)

![demo](https://www.automa.site/images/workflow-page.png){max-width: 300px, display: block, margin: 0 auto}

## Situation of data to be crawled

I need to download all the published `.xls` file of `Net Asset Value Daily report` from [the website of fund DCBC](https://dragoncapital.com.vn/en/investor-relations/announcement/?report_type=bao-cao-nav&fund_code=DCBC).

This is the manual workflow that I want to automate.
- Click on the row "2022 - DCBC - NAV REPORT", then a list of 10 "NAV daily report" will be displayed ![table-list-body](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-12-13_212331_wMqdBppai.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1670963391609){max-width: 300px, display: block, margin: 0 auto}
- Click on the 1st child element of this unordered list (e.g. "DCBC Net Asset Value as of Day 12/12/2022") ![ul](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-12-13_212405_Ly5mcZDkS.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1670963391450){max-width: 300px, display: block, margin: 0 auto}
- Switch active tab to the recently opened tab, and click on the link to download `.xls` file ![click-to-download](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-12-13_212459_3yjW32gbB.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1670963391579){max-width: 300px, display: block, margin: 0 auto}
- Delay 500ms, and Close this tab
- Then repeat the task to all other 9 child elements in the unordered list.

## What did I achieve using Automata?

### dcbc v5:

- The manual workflow depicted previously can be automated Automa like in this photo. ![automa-dcbc-v5](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-12-13_230625_LhfgSK3mk.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1670969229454){max-width: 300px, display: block, margin: 0 auto}
- [Click here](https://app.box.com/s/tu3lshyfkl12qpexshhltvlpas2wpc45) to download the `.json` file of Automa workflow.

### dcbc v6:

- use [Attribute Value](https://docs.automa.site/blocks/attribute-value.html) to retrieve the `href` value which is the URL of `.xls` file, save it to [Table](https://docs.automa.site/workflow/table.html#workflow-table)
- use [Get Text](https://docs.automa.site/blocks/get-text.html) to retrieve the text content (here is filename), save it to [Table](https://docs.automa.site/workflow/table.html#workflow-table)
- use [Export Data](https://docs.automa.site/blocks/export-data.html) to export the [Table](https://docs.automa.site/workflow/table.html#workflow-table) as `.csv` file to download later
- [Click here](https://app.box.com/s/4fnfgu26lcuujla0qy8dyvv1c7i4sdb2) to download the `.json` file of Automa workflow.

![automa-dcbc-v6](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-12-13_234218_xvMS4j1GI.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1670971359515){max-width: 300px, display: block, margin: 0 auto}

### dcbc v7:

- in the previous version, my workflow can download only 10 files within the 1st page. Now I want to retrieve all published daily reports. At this moment, the [website of fund DCBC](https://dragoncapital.com.vn/en/investor-relations/announcement/?report_type=bao-cao-nav&fund_code=DCBC) has 24 pages of daily NAV reports, dated from 2022-01-03 to 2022-12-12. This means the [Loop Elements](https://docs.automa.site/blocks/loop-elements.html) need to be iterated ~240 times (10 files x 24 pages), which can be achieved using the feature "Load more elements" in [Loop Elements](https://docs.automa.site/blocks/loop-elements.html)
- Retrieving all 240 files' url of year 2022 has a runtime 16m23s
- [Click here](https://app.box.com/s/7xz8wkw3t0djc7wvijwn0drk539x9exc) to download the `.json` file of Automa workflow.

### dcbc v8
- Instead of looping the elements and then opening the daily nav page in new tab to retrieve the download url as in v7. My friend suggests trying to retrieve all the URLs first and then loop through these URLs.
- I expected that the runtime of this version should be much shorter than v7. Surprisingly, the runtime of v8 is worse, at 23m29s
- [Click here](https://app.box.com/s/mcekp1p3ey4wtse57rsdre26mn1n1urx) to download the `.json` file of Automa workflow.

![automa-dcbc-v8](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-12-16_001603_EZHdQFXQM.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1671146216258){max-width: 300px, display: block, margin: 0 auto}