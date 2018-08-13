---
slug: sage-50-uk-cis-returned-transaction-columns
title: Sage 50 UK CIS_RETURNED_TRANSACTION Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRANSACTION_ID | INTEGER | 4 | 10 | Autonumber unique ID for transaction - the transaction number exposed to users |  |
| RETURN_ID | INTEGER | 4 | 10 | The unique ID of the CIS return in which this transaction was reported |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
