---
slug: sage-50-uk-tax-code-columns
title: Sage 50 UK TAX_CODE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) | T0 |
| TAX_CODE_ID | SMALLINT | 2 | 5 | Tax code number (0 to 99) | 0 |
| DESCRIPTION | VARCHAR | 60 | 60 | Tax code description | Zero rated |
| TAX_RATE | DOUBLE | 8 | 15 | Tax code rate | 0 |
| VAT_INCLUDE | TINYINT | 1 | 3 | Tax code included in VAT return | 1 |
| EURO_SALES | TINYINT | 1 | 3 | Tax code is EC Sales Tax code | 0 |
| EURO_PURCHASE | TINYINT | 1 | 3 | Tax code is EC Purchase Tax code | 0 |
| RELATED_CODE | TINYINT | 1 | 3 | Related Tax code for EC Purchase Tax code | 0 |
| RELATED_RATE | DOUBLE | 8 | 15 | Related Tax code rate for EC Purchase Tax code | 0 |
| IS_REVERSECHARGE | SMALLINT | 2 | 5 | Reverse charge items posted to this tax code | 0 |
