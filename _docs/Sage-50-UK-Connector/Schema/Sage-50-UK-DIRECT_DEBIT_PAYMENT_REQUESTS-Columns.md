---
slug: sage-50-uk-direct-debit-payment-requests-columns
title: Sage 50 UK DIRECT_DEBIT_PAYMENT_REQUESTS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Transaction number |  |
| PAYMENT_REQUEST_ID | VARCHAR | 37 | 37 | Payment request guid |  |
| DIRECT_DEBIT_STATUS | TINYINT | 1 | 3 | Direct debit status |  |
| DIRECT_DEBIT_STATUS_DESCRIPTION | VARCHAR | 25 | 25 | Direct debit status |  |
| LAST_REFRESHED_DATE | DATE | 2 | 10 | Direct debit last refresh date |  |
| FAILURE_REASON | VARCHAR | 255 | 255 | Failure reason (if status is "failed") |  |
| DIRECT_DEBIT_CHARGE_DATE | DATE | 2 | 10 | Direct debit charge date for payment |  |
| DIRECT_DEBIT_REQUESTED_AMOUNT | DOUBLE | 8 | 15 | Requested amount for direct debit payment |  |
| DIRECT_DEBIT_INSTALMENT_NUMBER | SMALLINT | 2 | 5 | Instalment number when the payment is part of instalments for an invocie |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
