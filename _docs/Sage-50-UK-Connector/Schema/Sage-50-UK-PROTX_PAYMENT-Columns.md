---
slug: sage-50-uk-protx-payment-columns
title: Sage 50 UK PROTX_PAYMENT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| VENDOR_TX_CODE | VARCHAR | 63 | 63 | The id assigned to the payment by Line 50 |  |
| VPS_TX_ID | VARCHAR | 63 | 63 | The id assigned to the payment by Protx |  |
| TX_AUTH_NUMBER | VARCHAR | 63 | 63 | The id assigned to the payment by the bank |  |
| AMOUNT | DOUBLE | 8 | 15 | The amount of the payment |  |
| ACCOUNT | VARCHAR | 8 | 8 | The reference of the Customer/Supplier (if any) whose record was used for this transaction |  |
| PAYMENT_DATE | DATE | 2 | 10 | The date the payment was made through Line 50 |  |
| PAYMENT_TYPE | VARCHAR | 8 | 8 | The type of payment, |  |
| TRANSACTION_TYPE | TINYINT | 1 | 3 | The type of transaction i.e. Payment or Refund |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
