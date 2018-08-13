---
slug: sage-50-uk-vat-details-columns
title: Sage 50 UK VAT_DETAILS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| VAT_BOX | INTEGER | 4 | 10 | VAT Box |  |
| VAT_BOX_NAME | VARCHAR | 63 | 63 | Box description on VAT reports |  |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) |  |
| TRANSACTION_ID | INTEGER | 4 | 10 | Autonumber unique ID for transaction - the transaction number exposed to users |  |
| TRANSACTION_TYPE | VARCHAR | 3 | 3 | Transaction type |  |
| ACCOUNT | VARCHAR | 8 | 8 | Account Reference |  |
| NOMINAL | VARCHAR | 8 | 8 | Nominal Code |  |
| REF | VARCHAR | 30 | 30 | Transaction reference |  |
| DATE | DATE | 2 | 10 | Transaction date |  |
| DETAILS | VARCHAR | 60 | 60 | Transaction details |  |
| AMOUNT | DOUBLE | 8 | 15 | Value |  |
| VAT_FLAG_CODE | VARCHAR | 1 | 1 | VAT reconciled flag |  |
| VAT_TRAN_NAME | VARCHAR | 63 | 63 | Transaction description on VAT reports |  |
