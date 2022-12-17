---
id: 5n5rd1uc1zcnjhmkidppdpe
title: Web Browser Automation
desc: 'Web Browser Automation'
updated: 1671217215340
created: 1653787126743
---
# Web browser automation tools

## Open source Tools

### [Scrapy](https://scrapy.org/)
![[notes.tutorial.python.packages.scrapy#scrapy,1:#*]]

### [Playwright](https://playwright.dev/)
![[notes.tutorial.web-browser-automation.playwright#playwright,1:#*]]

### [Puppeteer](https://pptr.dev/)
![[notes.tutorial.web-browser-automation.puppeteer#puppeteer,1:#*]]

### [Selenium](https://www.selenium.dev/documentation/overview/)
![[notes.tutorial.web-browser-automation.selenium#selenium,1:#*]]

### [Automa](https://www.automa.site/)
- Automa is a browser extension for browser automation. From auto-fill forms, doing a repetitive task, taking a screenshot, to scraping data of the website

### [PageProbe](https://addons.mozilla.org/en-US/firefox/addon/pageprobe/)
- extension for Firefox only
- Unlimited number of trackers. Fully local solution - does not require an account
- Create automatic monitors for detecting and scanning changes on web pages

### [Headless Recorder](https://github.com/checkly/headless-recorder)
- extension for Chromium only
- open-source extension to record browser interaction and generating Puppeteer & Playwright scripts

## Commercial tools

### [Rocketride](https://www.rocketride.io/)
- [Pricing](https://www.rocketride.io/#pricing) starts at USD 9/month. Free for 500 local runs, 30 cloud runs
- The task runner uses [Playwright](https://playwright.dev/)
- Typical things to automate: Web scraping, Fill out forms, Download files, Periodically check for changes, Automate actions
- [Hacker News discussion](https://news.ycombinator.com/item?id=32352291)

### [Browserflow](https://browserflow.app/)
- [Pricing](https://browserflow.app/pricing) starts at USD 49/month. Free for desktop runs, but 1 minute per run
- Automatically perform actions on websites as if you were doing them

### [visualping](https://visualping.io/)
- [Pricing](https://visualping.io/pricing/) starts at USD 14/month. Free for limited use
- Website change detection and alerts

### [Distill.io](https://distill.io/)
- [Pricing](https://distill.io/pricing) starts at USD 15/month. Free for limited use
- automated tracking website updates

### [ScrapFly](https://scrapfly.io/)
- [Pricing](https://scrapfly.io/pricing) starts at USD 15/month. Free for 1000 API calls / month

### [ScrapingBee](https://www.scrapingbee.com/)
- [Pricing](https://www.scrapingbee.com/#pricing) starts at USD 49/month. Free for 1000 API calls

### [ScraperAPI](https://www.scraperapi.com/)
- [Pricing](https://www.scraperapi.com/pricing/) starts at USD 29/month. Free for 1000 web pages per month.

### [Morph.io](https://morph.io/)
- Free to use. But can [subscribe as a supporter](https://morph.io/supporters/new), starting at USD 14/month.

### [Scraping Fish](https://scrapingfish.com/)
- [Pricing](https://scrapingfish.com/#pricing) starts at USD 0.002 per each API calls.

### [Crawly - Web Crawler by Diffbot](https://crawly.diffbot.com/)
- Turn websites into data. Crawly spiders and extracts complete structured data from an entire website.

### [Browse AI](https://www.browse.ai/)
- Train a robot to scrape any website in 2 mins with no-code
- [Pricing](https://www.browse.ai/pricing) starts at USD 49/month. Limited free plan available

### [Scrape Owl](https://scrapeowl.com/)
- Simple and powerful web scraping API that manages proxies, headless browsers, and HTML parsing. Simply specify the website and the element you want
- [Pricing](https://scrapeowl.com/pricing) starts at USD 29/month

### [Web Automation](https://webautomation.io/)
- the largest marketplace to find ready-made no code web scrapers. With only a few clicks and a few seconds you can start extracting data from your favourite site without coding or building from scratch
- [Pricing](https://webautomation.io/pricing/) starts at USD 49/month

### [EasyScrape](https://www.easyscrape.xyz/)
- With EasyScrape you can scrape the articles from any webpage with just one click. You can upload a text file containing a list of URLs or a single URL or a keyword, articles will be scraped from those URLs with just a click.

### [Scrape All](https://scrapeall.io/)
- Automated web data scraper. Extract any kind of web data without codding skills requirements
- [Pricing](https://scrapeall.io/pricing-2/) starts at USD 10 / 3K credits

### [ProxyScrape](https://proxyscrape.com/home)
- Scrape websites without limits, with up to 60 000 datacenter proxies

### [APIFY](https://apify.com/)
- web scraping and automation platform
- [Pricing](https://apify.com/pricing) starts at USD 49/month. Limited free plan available

### [Zyte](https://www.zyte.com/) (formerly Scrapinghub)
- [Pricing](https://www.zyte.com/pricing/#scrapy-cloud) is not clear at the moment (2022-05-09)

### [Price2Spy](https://www.price2spy.com/en/)
- Scraping tools for e-commerce (pricing bot)
- [Pricing](https://www.price2spy.com/en/pricing/basic.html) starts at USD 24/month

### [Bright Data](https://brightdata.com/)
- complicated pricing page
- [Demo video](https://www.youtube.com/watch?v=DKjXYEj9uEY)

## Related resources

- [Web scraping with Python open knowledge](https://github.com/reanalytics-databoutique/webscraping-open-project)

### Tutorials

- [ScrapFly | Web Scraping With Python Tutorial](https://scrapfly.io/blog/web-scraping-with-python/)
- [ScrapFly | How to Scrape Without Getting Blocked Tutorial](https://scrapfly.io/blog/how-to-scrape-without-getting-blocked-tutorial/)
- [ScrapFly | Parsing HTML with Xpath](https://scrapfly.io/blog/parsing-html-with-xpath/)
- [ScrapFly | Parsing HTML with CSS Selectors](https://scrapfly.io/blog/parsing-html-with-css/)
- [ScrapingBee | Web Scraping with Python: Everything you need to know (2022)](https://www.scrapingbee.com/blog/web-scraping-101-with-python/)
- [ScrapingBee | Web Scraping using Selenium and Python](https://www.scrapingbee.com/blog/selenium-python/)
- [ScrapingBee | Using Parsel to Extract Text from HTML in Python](https://www.scrapingbee.com/blog/parsel-python/)
    - While libraries like Beautiful Soup, Scrapy, and Selenium might be overkill, Parsel is a great option for simple web scraping. Parsel’s simple methods and Selectors provide all of the functionality required for basic scraping scripts, whereas other libraries contain a slew of features that you’ll never use in a simple scraping script—such as browser automation, telnet console, logging, and emails, which aren’t required when all you want to do is extract content from a static website.
- [ScrapingBee | Easy web scraping with Scrapy](https://www.scrapingbee.com/blog/web-scraping-with-scrapy/)
- [Python BeautifulSoup Tutorial: Web Scraping In 20 Lines Of Code](https://www.kashifaziz.me/web-scraping-python-beautifulsoup.html/)
- [Batch Downloading With Python](https://thesoloadmin.com/batch-downloading-with-python/)
- [enable clicking on the "show more" button on medium blog site via selenium](https://shantoroy.com/webscrapping/click-button-show-more-on-medium-dot-com-via-selenium/)
- [Dataquest [YouTube] | Web Scraping Beginner Tutorial: BeautifulSoup, Playwright, And Python](https://www.youtube.com/watch?v=SJ7xnhSLwi0)
- [realpython | Python Web Scraping Learning Path](https://realpython.com/learning-paths/python-web-scraping/)