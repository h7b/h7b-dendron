---
id: z5whn9moyd1ntz2hj3r89h0
title: Data Model
desc: ''
updated: 1664498495222
created: 1664498364014
---
# Data model

## Overview

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