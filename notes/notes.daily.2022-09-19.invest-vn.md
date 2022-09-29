---
id: yrx5ic5g0xjxt8o7cixwh74
title: Investment fund in Vietnam
desc: 'Investment fund for individual in Vietnam'
updated: 1664417058282
created: 1663748243722
tags: topic.investment
---
# Investment fund for individual in Vietnam

## Methodology

- compare the performance of each financial instrument with respect to their fee
    - the performance is defined by the return ratio of NAV/fund certificate
- compare the basis stats like P/E, P/B, ROE
- establish the correlation between these financial instrument based on the holdings in their portfolio. This correlation matrix is expected to match the benchmark index of each investment fund

## Data model

I collected the information and the historical price data manually then put into [this spreadsheet](https://docs.google.com/spreadsheets/d/1qsWWEUE87dsR_4MmEfBID_6d20Oz1e5JYLP8NiEPngo/edit?usp=sharing), which has an ER diagram as follows.

```mermaid
erDiagram
    issuer ||--|{ fund_info : issues
    fund_info o{--o| index  : tracks
    fund_info ||--|{ fund_metadata : has
    fund_info ||--|{ fund_totalExpenseRatio : has
    fund_info ||--|{ fund_fee : has
    fund_metadata }|..|{ ref_doc : "attached to"
    fund_fee }|..|{ ref_doc : "attached to"
    fund_totalExpenseRatio }|..|{ ref_doc : "attached to"
    index {
        string index_pk PK
        string index_name
        string country_name
    }
    issuer {
        string issuer_name_pk PK
        string issuer_website
    }
    fund_info {
        string fund_info_pk PK
        string fund_ticker
        string fund_name
        string fund_name_alternative
        string fund_structure
        string fund_strategy
        string fund_website
        string issuer_id FK
        string index_id FK
    }
    fund_metadata {
        string fund_metadata_pk PK
        string metadata_type
        string metadata_value
        string fund_info_id FK
        string ref_doc_id FK
        string ref_doc_note
    }
    fund_fee {
        int fund_fee_pk PK
        string fee_type
        float fee_value_in_percent
        int fee_value_in_vnd
        string fee_unit
        string fee_condition
        string fee_status
        string fund_info_id FK
        string ref_doc_id FK
        string ref_doc_note
    }
    fund_totalExpenseRatio {
        string fund_tER_pk PK
        date end_date_of_reporting_period
        float total_expense_ratio
        string fund_info_id FK
        string ref_doc_id FK
        string ref_doc_note
    }
    ref_doc {
        string ref_doc_pk PK
        string doc_url
        string doc_name
        string doc_languague
    }
```

## ETF

## [VFMVN DIAMOND ETF (FUEVFVND)](https://dragoncapital.com.vn/en/vfmvn-diamond-etf-fund-fuevfdmd/overview/)

![[notes.daily.2022-05-30.fuevfvnd#overview,1:#*]]

## [VFMVN30 ETF (E1VFVN30)](https://dragoncapital.com.vn/en/etf-vfmvn30-fund-e1vfvn30/etf-overview/)

![[notes.daily.2022-05-30.e1vfvn30#overview,1:#*]]

## [SSIAM VN30 ETF (FUESSV30)](https://www.ssi.com.vn/en/ssiam/fund-information-ssiam-vn30)

![[notes.daily.2022-05-30.fuessv30#overview,1:#*]]

## [MAFM VN30 ETF (FUEMAV30)](https://www.masvn.com/en/cate/general-information-1561)

![[notes.daily.2022-05-30.fuemav30#overview,1:#*]]

## Open-end fund