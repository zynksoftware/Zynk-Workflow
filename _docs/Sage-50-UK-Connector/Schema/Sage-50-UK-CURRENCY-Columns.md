---
slug: sage-50-uk-currency-columns
title: Sage 50 UK CURRENCY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| NUMBER | SMALLINT | 2 | 5 | Currency number | 1 |
| CODE | VARCHAR | 3 | 3 | Currency code | GBP |
| SYMBOL | VARCHAR | 3 | 3 | Currency symbol | £ |
| NAME | VARCHAR | 30 | 30 | Currency name | Pound Sterling |
| EMU_MEMBER | SMALLINT | 2 | 5 | Is a member of the EMU | 0 |
| BASE_CURRENCY | SMALLINT | 2 | 5 | Is the base currency | 1 |
| RATE | DOUBLE | 8 | 15 | Exchange Rate | 1 |
| MAJOR_CURRENCY_UNIT | VARCHAR | 20 | 20 | Major currency unit | pounds |
| MINOR_CURRENCY_UNIT | VARCHAR | 20 | 20 | Minor currency unit | pence |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
