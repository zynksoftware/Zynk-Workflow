---
slug: sage-50-uk-update-ledger-columns
title: Sage 50 UK UPDATE_LEDGER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| INVOICE_NUMBER | INTEGER | 4 | 10 | Invoice number |  |
| TRAN_NUMBER | INTEGER | 4 | 10 | Item number |  |
| TYPE | VARCHAR | 2 | 2 | Transaction type |  |
| DATE | VARCHAR | 10 | 10 | Remittance Date |  |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales Account Reference |  |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal Code |  |
| DESCRIPTION | VARCHAR | 60 | 60 | Description |  |
| ERROR | VARCHAR | 259 | 259 | Update error message |  |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock code |  |
| QUANTITY | DOUBLE | 8 | 15 | Quantity |  |
| NET_AMOUNT | DOUBLE | 8 | 15 | Net amount |  |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount |  |
| GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount |  |
| CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) |  |
