---
slug: sage-50-uk-vat-return-columns
title: Sage 50 UK VAT_RETURN Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| VAT_BOX | SMALLINT | 2 | 5 | Box on Vat Return |  |
| VAT_BOX_NAME | VARCHAR | 63 | 63 | Box description on VAT reports |  |
| COUNT_ALL | INTEGER | 4 | 10 | Number of transactions included |  |
| COUNT_EARLIER | INTEGER | 4 | 10 | Number of transactions in earlier period |  |
| COUNT_RECON | INTEGER | 4 | 10 | Number of transactions previously reconciled |  |
| COUNT_UNRECON | INTEGER | 4 | 10 | Number of transactions not previously reconciled |  |
| AMOUNT | DOUBLE | 8 | 15 | Amount for Box on VAT Return |  |
