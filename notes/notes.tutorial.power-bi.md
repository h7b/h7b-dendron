---
id: hrGH2IsGXmxlDMVydip5h
title: Power BI
desc: Microsoft Power BI
updated: 1662163184244
created: 1640234050326
---
# Microsoft Power BI

ref: [ExcelIsFun](https://www.youtube.com/watch?v=nBu1Bqa1jjs), [fluentpro](https://fluentpro.com/blog/difference-between-power-pivot-power-query-and-power-bi)

## Different Power BI products

1. Power BI Desktop
    - Free
    - Publish to the powerbi.com
    - Can share `.pbix` file so others with the “free” Power BI Desktop can view
    - Create `Web Embed Code` you can post at Public website 
        - 2022-09-03 update: All of "Share" features now requires a Power BI Pro license [^1]
2. Power BI Pro
    - USD 10 / month / user
    - Collaborate on shared data
    - Audit and govern how data is accessed and used
    - Package content and distribute to users with apps
    - Publish to powerbi.com and have others view on any device
    - From published report viewers can download Data Model into Excel or as a `.pbix` file.
3. Power BI Premium
    - Contact Sales, USD 5k / month
    - Unlock higher limits for Power BI Pro users
    - Access interactive and paginated reports online or use Power BI Report Server for on-premises reporting

[^1]: : [Microsoft](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-publish-to-web)

## Power BI, Power Query, Power Pivot, What to use when?

Power Query and Power Pivot complement each other. Use both to shape your data in Excel so you can explore and visualize it in PivotTables, PivotCharts, and Power BI
- Power Query is the recommended tool for locating, connecting to and importing data. 
- Power Pivot: is great for modeling the data you’ve imported

|   | Power Query | Power Pivot | Desktop & PowerBI.com |
|:--|:--|:--|:--|
| Role | Import and shape data | Data modeling and calculations | Complete business intelligence tool |
| Language | M | DAX | M and DAX |
| Key strengths | - Nice easy to use interface<br>- Powerful tools to import and clean data<br>- All Excel users can benefit from this tool | - Easily handle millions of rows of data<br>- Modeling tools for efficient data storage and analysis<br>- Powerful DAX calculations going beyond standard Excel | - Incredible visualization options<br>- Simple built-in interactive options<br>- Powerful DAX calculations<br>- Simple publishing to PowerBI.com and mobile devices |

A diagram explaining how these Powerful tools are related
![power-platform](https://fluentpro.com/wp-content/uploads/2019/12/1.png){max-width: 300px, display: block, margin: 0 auto}

With respect to report usage, typical usage can be seen below.

![usage-diagram](https://i0.wp.com/whitepages.unlimitedviz.com/wp-content/uploads/2021/03/image-1.png?w=1521&ssl=1){max-width: 300px, display: block, margin: 0 auto}

| Tool | Used by | Purpose |
|:---:|:---:|:---:|
| Power BI Service | Report consumers | Consuming all types of reports: interactive, paginated and Excel |
| Excel Online | Report consumers | Consuming Excel reports from SharePoint, Teams, or the Power BI service |
| Power BI Desktop | Model builders<br>Interactive report designers | Building Power BI dataset<br>Building interactive reports |
| Power BI Report Builder | Paginated report designers | Building paginated reports |
| Excel | Analysts | Building Excel reports<br>Analyzing Power BI datasets |

## Related resources:

### Tutorials:
- [Power BI instructor-led training](https://powerbi.microsoft.com/en-us/instructor-led-training/)
- [Microsoft Learn for Power BI](https://docs.microsoft.com/en-us/learn/powerplatform/power-bi)
- [Study Guide Exam PL-300: Microsoft Power BI Data Analyst](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWREll)

### Add-on for DAX
- [DAX Formatter](https://www.daxformatter.com/) is a free tool by SQLBI that transforms raw DAX formulas into clean, beautiful and readable code.
- [DAX.do](https://dax.do/) is a free online playground to write, run and share DAX queries.
- [DAX Studio](https://daxstudio.org/) is a tool to write, execute, and analyze DAX queries in Power BI Designer, Power Pivot for Excel, and Analysis Services Tabular. It includes an Object Browser, query editing and execution, formula and measure editing, syntax highlighting and formatting, integrated tracing, and query execution breakdowns.
- [Power BI Sidetools](https://thebipower.fr/index.php/power-bi-sidetools/) is an external tool intended to increase productivity during reports development in Power BI desktop. It combine sereral tools, such as [DAX generator](https://thebipower.fr/index.php/dax-generator/), [DAX debugger](https://thebipower.fr/index.php/2021/04/05/dax-debugger/), `DAX parser`

### Add-on for Dashboard reporting:
- [[Charticulator|notes.tutorial.power-bi.charticulator]] create custom chart designs for your reports using data modeled in Power BI.
  - Free with many templates
  ![charticulator-example](https://charticulator.azureedge.net/images/gallery/les_miserables_linear.png){max-width: 300px, display: block, margin: 0 auto}
- [Zebra BI](https://zebrabi.com/) offer many report templates both free and paid
  - [Pricing](https://zebrabi.com/pricing/?product=pbi)
  - Example template
  ![zebra-bi-example](https://zebrabi.com/wp-content/uploads/2020/11/power-bi-small-multiples-zebra.png.webp){max-width: 300px, display: block, margin: 0 auto}
- [Other Level’s | Youtube](https://www.youtube.com/c/OtherLevel’s) channel, which give inspirations and tutorial on dashboard visuals
  - Individual [Pricing](https://www.other-levels.com/store) plan for each template
  ![other-level-example](https://static.wixstatic.com/media/5681ed_84800b6da34043babf63b6feb699b5b4~mv2.png/v1/fill/w_1103,h_689,al_c,q_90,usm_0.66_1.00_0.01/5681ed_84800b6da34043babf63b6feb699b5b4~mv2.webp){max-width: 300px, display: block, margin: 0 auto}
- [How to Power BI | Youtube](https://www.youtube.com/c/HowtoPowerBI/) channel, which share tutorial on how to design page navigation, clean menu and custom visual in Power BI
  ![howtopopwerbi-example](https://i.imgur.com/WSw6P3L.jpg){max-width: 300px, display: block, margin: 0 auto}
- [Entreprise DNA | Power BI Showcase](https://enterprisedna.co/power-bi-showcase), some great dashboard from which I get inspiration 
  ![entreprise-dna-showcase](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-08_011815_hI98ottixMf.jpg?updatedAt=1641601140091){max-width: 300px, display: block, margin: 0 auto}
- [inforiver](https://inforiver.com/): besides of visualization, this add-in put Power Bi on steroid with Excel-like [features](https://powerbi.microsoft.com/en-us/blog/inforiver-no-code-partner-innovation-for-end-user-self-service-inside-power-bi/), which are simulation, planning, and writeback capabilities. Beside of their own [licenses](https://inforiver.com/pricing/), Inforiver requires a PBI License if you want to publish and share the reports like any other visual. It is interesting to compare this solution vs [Causal](https://www.causal.app/)
  ![inforiver-pricing](https://powerbiblogscdn.azureedge.net/wp-content/uploads/2022/02/timeline-description-automatically-generated-2.png)
- [[Deneb|notes.tutorial.power-bi.deneb]], another library to create custom visual for Power BI