---
slug: sage-50-uk-gdn-item-columns
title: Sage 50 UK GDN_ITEM Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | Unique record identifier | 1 |
| GDN_NUMBER | INTEGER | 4 | 10 | Goods Despatch Note Number | 1 |
| ITEM_NUMBER | INTEGER | 4 | 10 | Item number within Despatch Note | 1 |
| ORDER_NUMBER | INTEGER | 4 | 10 | Sales Order Number | 29 |
| ORDER_ITEM | SMALLINT | 2 | 5 | Item number within Sales Order | 0 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales Account Reference | BRI001 |
| CUSTOMER_GDN_NUMBER | VARCHAR | 20 | 20 | Customer's Goods Delivered Number |  |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock Code | BOOKS001 |
| DESCRIPTION | VARCHAR | 60 | 60 | Stock Description | A4 Ledger Book - 5 Column |
| DATE | DATE | 2 | 10 | Date Goods Received | 19/06/2009 00:00:00 |
| QTY_DESPATCHED | DOUBLE | 8 | 15 | Quantity Despatched | 5 |
| QTY_ON_ORDER | DOUBLE | 8 | 15 | Quantity on order | 20 |
| PRINTED_FLAG | TINYINT | 1 | 3 | Printed flag - 1/0 | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
