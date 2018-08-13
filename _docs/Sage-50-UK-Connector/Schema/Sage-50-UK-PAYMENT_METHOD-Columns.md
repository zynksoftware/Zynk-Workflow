---
slug: sage-50-uk-payment-method-columns
title: Sage 50 UK PAYMENT_METHOD Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique number of this payment method | 1 |
| DESCRIPTION | VARCHAR | 30 | 30 | A human-readable description of this payment method e.g. 'BACS' | BACS/SEPA |
| ONLINE | SMALLINT | 2 | 5 | Is this an online payment method? | 1 |
| READONLY | SMALLINT | 2 | 5 | Is the user prevented from editing the name of this payment method? | 1 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
