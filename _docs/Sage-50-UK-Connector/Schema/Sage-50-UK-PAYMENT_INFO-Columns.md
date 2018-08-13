---
slug: sage-50-uk-payment-info-columns
title: Sage 50 UK PAYMENT_INFO Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Transaction number |  |
| PAYMENT_STATUS | TINYINT | 1 | 3 | Payment Status |  |
| PAYMENT_STATUS_DESCRIPTION | VARCHAR | 30 | 30 | Payment Status Description |  |
| FOREIGN_SAGE_PAYMENTS_RATE | DOUBLE | 8 | 15 | The final exchange rate for the transaction from when it was processed by Sage Payments |  |
| FINAL_AMOUNT_BASE | DOUBLE | 8 | 15 | The amount finally paid in base currency. |  |
| FINAL_PAID_DATE | DATE | 2 | 10 | Date when the final payment was made. |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | SMALLINT | 2 | 5 | Flag denoting if the record has been deleted or not. |  |
