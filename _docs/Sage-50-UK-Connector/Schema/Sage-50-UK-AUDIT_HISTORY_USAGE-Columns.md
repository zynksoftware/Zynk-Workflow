---
slug: sage-50-uk-audit-history-usage-columns
title: Sage 50 UK AUDIT_HISTORY_USAGE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TYPE | VARCHAR | 2 | 2 | Transaction type |  |
| USAGE_NUMBER | INTEGER | 4 | 10 | Usage number |  |
| SPLIT_NUMBER | INTEGER | 4 | 10 | Split number |  |
| SPLIT_CROSSREF | INTEGER | 4 | 10 | Cross reference split number |  |
| REFERENCE | VARCHAR | 30 | 30 | Payment reference |  |
| DETAILS | VARCHAR | 60 | 60 | Details |  |
| USER_NAME | VARCHAR | 32 | 32 | User name |  |
| DATE | DATE | 2 | 10 | Date |  |
| AMOUNT | DOUBLE | 8 | 15 | Amount Paid (Base currency) |  |
| FOREIGN_AMOUNT | DOUBLE | 8 | 15 | Amount Paid (Foreign Currency) |  |
| DELETED_FLAG | SMALLINT | 2 | 5 | Transaction deleted flag |  |
| CIS_VAT | DOUBLE | 8 | 15 | CIS VAT value |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
