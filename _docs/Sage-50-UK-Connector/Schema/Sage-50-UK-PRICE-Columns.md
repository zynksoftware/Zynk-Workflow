---
slug: sage-50-uk-price-columns
title: Sage 50 UK PRICE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| PRICE_ID | VARCHAR | 39 | 39 | Ref | PGUF     APPWCH |
| TYPE | VARCHAR | 1 | 1 | Type: customer price list (P), supplier price list (U), customer special price (S) | P |
| PRICING_REF | VARCHAR | 8 | 8 | Pricing Reference | GUF |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock Code | APPWCH |
| CALC_METHOD | INTEGER | 4 | 10 | Price Calculation Method | 0 |
| CALC_VALUE | DOUBLE | 8 | 15 | Value or Percentage, depending on Method | 0 |
| STORED_PRICE | DOUBLE | 8 | 15 | Price for manually recalculated price lists | 0 |
| ROUNDER_METHOD | TINYINT | 1 | 3 | Rounding Method | 0 |
| ROUNDER_DIRECTION | TINYINT | 1 | 3 | Rounding Direction | 0 |
| ROUNDER_MULTIPLE_OF | DOUBLE | 8 | 15 | Rounding Multiple | 0 |
| ROUNDER_ADJUSTMENT | DOUBLE | 8 | 15 | Rounding Adjustment | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 31/05/2013 15:39:25 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
