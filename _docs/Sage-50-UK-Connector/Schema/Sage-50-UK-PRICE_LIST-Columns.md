---
slug: sage-50-uk-price-list-columns
title: Sage 50 UK PRICE_LIST Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TYPE | VARCHAR | 1 | 1 | Type: customer price list (P), supplier price list (U) | P |
| PRICING_REF | VARCHAR | 8 | 8 | Pricing Reference | PUBLIC |
| NAME | VARCHAR | 60 | 60 | Name | Public Price List |
| CURRENCY | TINYINT | 1 | 3 | Price List Currency | 1 |
| HAS_STATIC_PRICES | SMALLINT | 2 | 5 | Prices remain static | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 31/05/2013 15:39:25 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
