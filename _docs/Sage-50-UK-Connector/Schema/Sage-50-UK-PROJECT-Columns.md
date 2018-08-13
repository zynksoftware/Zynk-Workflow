---
slug: sage-50-uk-project-columns
title: Sage 50 UK PROJECT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| REFERENCE | VARCHAR | 12 | 12 | Project Reference | PROJ001 |
| NAME | VARCHAR | 60 | 60 | Project Name | SDE New Office Installation |
| DESCRIPTION | VARCHAR | 255 | 255 | Description | Install 4 PCs as requested (PC Combo Pack5) |
| STATUS_ID | INTEGER | 4 | 10 | Project Status ID | 1 |
| START_DATE | DATE | 2 | 10 | Start Date | 29/04/2017 00:00:00 |
| END_DATE | DATE | 2 | 10 | End Date | 29/04/2017 00:00:00 |
| CUSTOMER_REF | VARCHAR | 8 | 8 | Customer Account Reference | SDE001 |
| ORDER_NUMBER | VARCHAR | 60 | 60 | Default Order Number | 93028 |
| ANALYSIS_1 | VARCHAR | 30 | 30 | Analysis 1 | Malcolm |
| ANALYSIS_2 | VARCHAR | 30 | 30 | Analysis 2 | Business |
| ANALYSIS_3 | VARCHAR | 30 | 30 | Analysis 3 | Yes |
| ADDRESS_1 | VARCHAR | 60 | 60 | Site Address 1 |  |
| ADDRESS_2 | VARCHAR | 60 | 60 | Site Address 2 |  |
| ADDRESS_3 | VARCHAR | 60 | 60 | Site Address 3 |  |
| ADDRESS_4 | VARCHAR | 60 | 60 | Site Address 4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Site Address 5 |  |
| CONTACT_NAME | VARCHAR | 30 | 30 | Site Contact |  |
| TELEPHONE | VARCHAR | 30 | 30 | Site Telephone |  |
| FAX | VARCHAR | 30 | 30 | Site Fax |  |
| E_MAIL | VARCHAR | 255 | 255 | Site E-mail |  |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country Code | GB |
| TOTAL_BILLED | DOUBLE | 8 | 15 | Total Billed | 14100 |
| BILLED_NET | DOUBLE | 8 | 15 | Billed Net | 12000 |
| BILLED_TAX | DOUBLE | 8 | 15 | Billed Tax | 2100 |
| OUTSTANDING_TO_BILL | DOUBLE | 8 | 15 | Outstanding to Bill | -8000 |
| PRICE_QUOTED | DOUBLE | 8 | 15 | Price Quoted | 4000 |
| PROFIT_TO_DATE | DOUBLE | 8 | 15 | Profit To Date | 9284.65 |
| TOTAL_COST | DOUBLE | 8 | 15 | Total Cost | 2715.35 |
| TOTAL_BUDGET | DOUBLE | 8 | 15 | Total Budget | 3718 |
| VARIANCE | DOUBLE | 8 | 15 | Variance | 1002.65 |
| LAST_BILLED_DATE | DATE | 2 | 10 | Last Billed Date | 11/08/2008 00:00:00 |
| LAST_COST_DATE | DATE | 2 | 10 | Last Billed Date | 29/04/2005 00:00:00 |
| PROJECT_ID | INTEGER | 4 | 10 | Unique ID Number | 1 |
| PARENT_PROJECT_NO | INTEGER | 4 | 10 | Parent Project ID Number | 0 |
| CHILD_POSITION | INTEGER | 4 | 10 | Child Position (relative to other siblings) | 0 |
| COMMITTED_COST | DOUBLE | 8 | 15 | Committed Cost | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
