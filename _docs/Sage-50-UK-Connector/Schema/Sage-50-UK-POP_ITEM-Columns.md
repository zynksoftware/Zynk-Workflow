---
slug: sage-50-uk-pop-item-columns
title: Sage 50 UK POP_ITEM Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ORDER_NUMBER | INTEGER | 4 | 10 | Order Reference number | 1 |
| ITEM_NUMBER | SMALLINT | 2 | 5 | Item number | 1 |
| JOB_NUMBER | VARCHAR | 60 | 60 | Job number |  |
| SERVICE_FLAG | SMALLINT | 2 | 5 | Product or Service item flag | 0 |
| DESCRIPTION | VARCHAR | 60 | 60 | Description | Envelope - White (110 x 220) Plain |
| TEXT | LONG VARCHAR | 32767 | 32767 | Service item text |  |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock code | ENV001 |
| COMMENT_1 | VARCHAR | 60 | 60 | Comment 1 |  |
| COMMENT_2 | VARCHAR | 60 | 60 | Comment 2 |  |
| UNIT_OF_SALE | VARCHAR | 8 | 8 | Unit of sale | 1000 Box |
| QTY_ORDER | DOUBLE | 8 | 15 | Quantity ordered | 40 |
| QTY_ALLOCATED | DOUBLE | 8 | 15 | Quantity allocated for this order | 0 |
| QTY_DELIVERED | DOUBLE | 8 | 15 | Quantity previously delivered for this order | 40 |
| QTY_DESPATCH | DOUBLE | 8 | 15 | Quantity to despatch/despatched on this delivery | 0 |
| QTY_LAST_DESPATCH | DOUBLE | 8 | 15 | Quantity despatched on most recent delivery | 0 |
| FOREIGN_UNIT_PRICE | DOUBLE | 8 | 15 | Unit price | 6 |
| FOREIGN_DISCOUNT_AMOUNT | DOUBLE | 8 | 15 | Discount amount | 24 |
| UNIT_PRICE | DOUBLE | 8 | 15 | Unit price | 6 |
| DISCOUNT_AMOUNT | DOUBLE | 8 | 15 | Discount amount | 24 |
| DISCOUNT_RATE | DOUBLE | 8 | 15 | Discount percentage rate | 10 |
| DELIVERY_DATE | DATE | 2 | 10 | Delivery date | 07/01/2006 00:00:00 |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal code |  |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department number | 1 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Sales |
| TAX_CODE_ID | SMALLINT | 2 | 5 | Tax code | 1 |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) | T1 |
| ADD_DISC_RATE | DOUBLE | 8 | 15 | Additional discount percentage rate | 0 |
| TAX_RATE | DOUBLE | 8 | 15 | Tax rate | 17.5 |
| FULL_NET_AMOUNT | DOUBLE | 8 | 15 | Full net amount (before discount) | 240 |
| NET_AMOUNT | DOUBLE | 8 | 15 | Net amount (after discount) | 216 |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount | 36.86 |
| GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount (net after discount + tax) | 252.86 |
| FOREIGN_FULL_NET_AMOUNT | DOUBLE | 8 | 15 | Full net amount (before discount) | 240 |
| FOREIGN_NET_AMOUNT | DOUBLE | 8 | 15 | Net amount (after discount) | 216 |
| FOREIGN_TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount | 36.86 |
| FOREIGN_GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount (net after discount + tax) | 252.86 |
| THIS_RECORD | INTEGER | 4 | 10 | Record number | 2 |
| POP_ITEM_ID | INTEGER | 4 | 10 | Unique pop item identifier | 2 |
| QTY_ALLOCATED_TO_PROJECT | DOUBLE | 8 | 15 | Quantity allocated to project | 0 |
| QTY_ISSUED_TO_PROJECT | DOUBLE | 8 | 15 | Quantity issued to project | 0 |
| DUE_DATE | DATE | 2 | 10 | Due date |  |
| QTY_COMMITTED_TO_PROJECT | DOUBLE | 8 | 15 | Quantity committed to project (for committed cost calculation) | 0 |
| PROJECT_REF | VARCHAR | 12 | 12 | Reference for associated project |  |
| PROJECT_NAME | VARCHAR | 60 | 60 | Name of associated project |  |
| COST_CODE_REF | VARCHAR | 8 | 8 | Reference for associated cost code |  |
| ITEMID | INTEGER | 4 | 10 | Item ID | 2 |
| GENERATED_MESSAGE | SMALLINT | 2 | 5 | True if this message was automatically generated | 0 |
| QTY_INVOICED | DOUBLE | 8 | 15 | Qty Invoiced | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
