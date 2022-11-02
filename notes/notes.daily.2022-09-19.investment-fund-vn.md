---
id: yrx5ic5g0xjxt8o7cixwh74
title: Investment funds for individual in Vietnam
desc: Investment funds for individual in Vietnam
updated: 1667340929134
created: 1663748243722
tags: topic.investment
---
# Investment options for individual in Vietnam

## Objectives

Find a simple investment vehicle for Vietnamese individual with the most affordable price/performance ratio.

## Methodology

- compare the performance of each financial instrument
    - the performance is defined by the return ratio of NAV/fund certificate with respect to their fee
- compare the fund's fundamental stats (e.g. P/E, P/B, ROE, ...) vs their benchmark
- establish the correlation between these financial instrument based on the holdings in their portfolio. This correlation matrix is expected to match the benchmark index of each financial instrument.

### List of investment vehicles

Here is the list of financial options issued in Vietnam, in which that I have interest.
- ETF
    - [[notes.daily.2022-09-19.investment-fund-vn.fuevfvnd]]
    - [[notes.daily.2022-09-19.investment-fund-vn.e1vfvn30]]
    - [[notes.daily.2022-09-19.investment-fund-vn.fuessv30]]
    - [[notes.daily.2022-09-19.investment-fund-vn.fuemav30]]
    - [[notes.daily.2022-09-19.investment-fund-vn.fuevn100]]
    - [[notes.daily.2022-09-19.investment-fund-vn.fuedcmid]]
    - [[notes.daily.2022-09-19.investment-fund-vn.fuessvfl]]
- Open-end fund
    - [[notes.daily.2022-09-19.investment-fund-vn.veof]]
    - [[notes.daily.2022-09-19.investment-fund-vn.vesaf]]
    - [[notes.daily.2022-09-19.investment-fund-vn.vff]]
    - [[notes.daily.2022-09-19.investment-fund-vn.dcbc]]
    - [[notes.daily.2022-09-19.investment-fund-vn.dcds]]
    - [[notes.daily.2022-09-19.investment-fund-vn.dcbf]]
    - [[notes.daily.2022-09-19.investment-fund-vn.ssi-vlgf]]
    - [[notes.daily.2022-09-19.investment-fund-vn.ssi-sca]]
    - [[notes.daily.2022-09-19.investment-fund-vn.ssibf]]
    - [[notes.daily.2022-09-19.investment-fund-vn.vcbf-bcf]]
    - [[notes.daily.2022-09-19.investment-fund-vn.vcbf-mgf]]
    - [[notes.daily.2022-09-19.investment-fund-vn.vcbf-fif]]

## Current issues

- historical end-of-day (EOD) price data of open-end fund are hard to be collected
    - the `.xls`/`.pdf` files of NAV change are published only on the website of each fund. They need to be web-scraped  
    - then extract the NAV value at the end of each day 
- historical EOD price data of ETF and index are downloaded manually via [investing.com](https://www.investing.com/)
    - enhance: use [investiny](https://github.com/alvarobartt/investiny) package instead of download manually

## Data model

![[notes.daily.2022-09-19.investment-fund-vn.data-model#overview]]

## Related

- [stag | Danh sách các quỹ mở trên thị trường Việt Nam](https://stag.vn/mutual-funds)
- [haxj | Performance dashboard of open-ended funds in Vietnam](https://haxj.github.io/posts/vietnam-funds/)
- [[notes.daily.2022-09-19.etf-vn]]