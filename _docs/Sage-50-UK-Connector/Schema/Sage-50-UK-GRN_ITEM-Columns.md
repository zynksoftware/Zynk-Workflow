---
slug: sage-50-uk-grn-item-columns
title: Sage 50 UK GRN_ITEM Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| GRN_NUMBER | INTEGER | 4 | 10 | GRN Number | 2 |
| ITEM_NUMBER | INTEGER | 4 | 10 | Item number within GRN | 1 |
| ORDER_NUMBER | INTEGER | 4 | 10 | Purchase Order Number | 37 |
| ORDER_ITEM | SMALLINT | 2 | 5 | Item number within Purchase Order | 0 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Purchase Account Reference | MCN001 |
| SUPPLIER_GRN_NUMBER | VARCHAR | 20 | 20 | Supplier's GRN Number |  |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock Code | PC004 |
| DESCRIPTION | VARCHAR | 60 | 60 | Stock Description | PC Combo Pack 4 |
| DATE | DATE | 2 | 10 | Date Goods Received | 30/08/2006 00:00:00 |
| QTY_RECEIVED | DOUBLE | 8 | 15 | Quantity Received | 1 |
| QTY_ON_ORDER | DOUBLE | 8 | 15 | Quantity on order | 1 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
