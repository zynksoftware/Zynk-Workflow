---
slug: sage-50-uk-audit-usage-columns
title: Sage 50 UK AUDIT_USAGE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TYPE | VARCHAR | 2 | 2 | Transaction type | PP |
| USAGE_NUMBER | INTEGER | 4 | 10 | Usage number | 1 |
| SPLIT_NUMBER | INTEGER | 4 | 10 | Split number | 86 |
| SPLIT_CROSSREF | INTEGER | 4 | 10 | Cross reference split number | 255 |
| REFERENCE | VARCHAR | 30 | 30 | Payment reference |  (BACS) |
| DETAILS | VARCHAR | 60 | 60 | Details | 117.50 from PP 255 |
| USER_NAME | VARCHAR | 32 | 32 | User name | MANAGER |
| DATE | DATE | 2 | 10 | Date | 29/01/2018 00:00:00 |
| AMOUNT | DOUBLE | 8 | 15 | Amount Paid (Base currency) | 117.5 |
| FOREIGN_AMOUNT | DOUBLE | 8 | 15 | Amount Paid (Foreign Currency) | 117.5 |
| DELETED_FLAG | SMALLINT | 2 | 5 | Transaction deleted flag | 0 |
| CIS_VAT | DOUBLE | 8 | 15 | CIS VAT value | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
