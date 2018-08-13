---
slug: sage-50-uk-stock-tran-columns
title: Sage 50 UK STOCK_TRAN Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Transaction number | 1 |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock code | BOARD001 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | AI |
| DATE | DATE | 2 | 10 | Transaction date | 31/12/2014 00:00:00 |
| REFERENCE | VARCHAR | 30 | 30 | Transaction reference | STK TAKE |
| REFERENCE_NUMERIC | INTEGER | 4 | 10 | Numeric verison of transaction reference | 0 |
| DETAILS | VARCHAR | 60 | 60 | Details | Whiteboard - Drywipe (900 x 1200) |
| QUANTITY | DOUBLE | 8 | 15 | Quantity | 2 |
| COST_PRICE | DOUBLE | 8 | 15 | Cost price | 15 |
| SALES_PRICE | DOUBLE | 8 | 15 | Sales price | 0 |
| QTY_USED | DOUBLE | 8 | 15 | Quantity used | 2 |
| ISP_REFERENCE | INTEGER | 4 | 10 | Inv/Sop/Pop Reference | 0 |
| ARTEFACT_TYPE | TINYINT | 1 | 3 | Artefact Type | 0 |
| GDN_NUMBER | INTEGER | 4 | 10 | GDN Reference | 0 |
| GRN_NUMBER | INTEGER | 4 | 10 | GRN Reference | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:50 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
