---
slug: sage-50-uk-account-status-columns
title: Sage 50 UK ACCOUNT_STATUS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| NUMBER | SMALLINT | 2 | 5 | Record Number | 1 |
| STATUS | VARCHAR | 60 | 60 | Account Status | Open |
| ON_HOLD | TINYINT | 1 | 3 | Account On Hold | 0 |
| RECORD_CREATE_DATE |  | 8 | 0 | Date and time when the record was created | 22/07/2008 16:37:55 |
| RECORD_MODIFY_DATE |  | 8 | 0 | Date and time when the record was modified | 04/08/2017 14:18:53 |
| RECORD_DELETED | SMALLINT | 2 | 5 | Flag denoting if the record has been deleted or not. | 13568 |
