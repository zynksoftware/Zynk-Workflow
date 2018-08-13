---
slug: sage-50-uk-vat-return-receipt-columns
title: Sage 50 UK VAT_RETURN_RECEIPT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique ID of this receipt |  |
| RECEIPT_TYPE | TINYINT | 1 | 3 | The type of VAT return receipt |  |
| VAT_AMOUNT | DOUBLE | 8 | 15 | The net vat amount contained in the receipt |  |
| PERIOD_START | DATE | 2 | 10 | The start of the vat return receipt acknowledged in the receipt |  |
| PERIOD_END | DATE | 2 | 10 | The end of the vat return period acknowledged in the receipt |  |
| CURRENCY_SYMBOL | VARCHAR | 3 | 3 | Confirmation of the currency used for the vat return |  |
| DUE_DATE | DATE | 2 | 10 | The date payment is due |  |
| HMRC_REFERENCE | VARCHAR | 32 | 32 | The vat declaration reference assigned to this vat return by HMRC |  |
| RECEIPT_TIMESTAMP | VARCHAR | 30 | 30 | The time the vat return was received by HMRC |  |
| PAYMENT_DATE | DATE | 2 | 10 | The date payment will be taken by HMRC, if a direct debit scheme is active |  |
| DIRECTDEBIT_STATUS | VARCHAR | 63 | 63 | The direct debit instruction status returned by HMRC |  |
| NARRATIVE | LONG VARCHAR | 16 | 16 | The narrative for this record |  |
| EXTRAINFO | LONG VARCHAR | 16 | 16 | The extra info for this record |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
