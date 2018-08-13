---
slug: sage-50-uk-remittance-columns
title: Sage 50 UK REMITTANCE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| URN | VARCHAR | 8 | 8 | Remittance Unique Reference Number |  |
| BANK_CODE | VARCHAR | 8 | 8 | Bank Account Reference |  |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Supplier Account Reference |  |
| NAME | VARCHAR | 60 | 60 | Account Name |  |
| ADDRESS_1 | VARCHAR | 60 | 60 | Account Address Line1 |  |
| ADDRESS_2 | VARCHAR | 60 | 60 | Account Address Line2 |  |
| ADDRESS_3 | VARCHAR | 60 | 60 | Account Address Line3 |  |
| ADDRESS_4 | VARCHAR | 60 | 60 | Account Address Line4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Account Address Line5 |  |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Account Address Line1 |  |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Account Address Line2 |  |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Account Address Line3 |  |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Account Address Line4 |  |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Account Address Line5 |  |
| TELEPHONE | VARCHAR | 30 | 30 | Telephone Number |  |
| FAX | VARCHAR | 30 | 30 | Fax Number |  |
| CHEQUE | VARCHAR | 30 | 30 | Cheque Reference |  |
| DATE | DATE | 2 | 10 | Remittance Date |  |
| TYPE | VARCHAR | 2 | 2 | Transaction Type |  |
| INVOICE_DATE | DATE | 2 | 10 | Invoice Date |  |
| INV_REF | VARCHAR | 30 | 30 | Invoice Reference |  |
| EXTRA_REF | VARCHAR | 60 | 60 | Extra Reference |  |
| DETAILS | VARCHAR | 60 | 60 | Details |  |
| TAX_CODE | VARCHAR | 3 | 3 | Tax Code |  |
| NET_AMOUNT | DOUBLE | 8 | 15 | Invoice Net Amount |  |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Invoice Tax Amount |  |
| GROSS_AMOUNT | DOUBLE | 8 | 15 | Invoice Gross Amount |  |
| PAYMENT | DOUBLE | 8 | 15 | Payment on this remittance |  |
| FOREIGN_RATE | DOUBLE | 8 | 15 | Foreign Exchange Rate |  |
| CURRENCY | TINYINT | 1 | 3 | Currency |  |
| PRINTED_FLAG | SMALLINT | 2 | 5 | Printed flag |  |
| PAID_FLAG | SMALLINT | 2 | 5 | Paid flag |  |
| LAST_LINE | SMALLINT | 2 | 5 | Last Line flag |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
