---
slug: sage-50-uk-intrastat-columns
title: Sage 50 UK INTRASTAT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ORDER_NUMBER | VARCHAR | 7 | 7 | Order Number |  |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Trader Account Reference |  |
| STOCK_CODE | VARCHAR | 30 | 30 | Product Code |  |
| DESCRIPTION | VARCHAR | 60 | 60 | Description |  |
| DATE | DATE | 2 | 10 | Date Goods Received |  |
| NOTC | VARCHAR | 3 | 3 | Nature of Transaction Code |  |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country Code |  |
| COMMODITY_CODE | VARCHAR | 8 | 8 | Commodity Code |  |
| DELIVERY_STATUS | VARCHAR | 8 | 8 | Delivery Status |  |
| DELIVERY_TERMS | VARCHAR | 3 | 3 | Delivery Terms |  |
| QUANTITY | DOUBLE | 8 | 15 | Quantity |  |
| QTY_ORDERED | DOUBLE | 8 | 15 | Quantity Ordered |  |
| QTY_DELIVERED | DOUBLE | 8 | 15 | Quantity Already Delivered |  |
| QTY_TO_CONFIRM | DOUBLE | 8 | 15 | Quantity To Confirm |  |
| UNIT | DOUBLE | 8 | 15 | Units |  |
| NET_MASS | DOUBLE | 8 | 15 | Net Mass |  |
| GOODS_VALUE | DOUBLE | 8 | 15 | Goods Value |  |
| COUNTRY_OF_ORIGIN | VARCHAR | 2 | 2 | Country Of Origin |  |
| TRANSPORT | VARCHAR | 1 | 1 | Presumed Mode of Transport |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
