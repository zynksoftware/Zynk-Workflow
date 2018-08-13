---
slug: sage-50-uk-audit-vat-columns
title: Sage 50 UK AUDIT_VAT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Transaction number | 56 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | CP |
| DATE | DATE | 2 | 10 | Transaction date | 30/01/2016 00:00:00 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales/Purchase/Bank Account Reference | 1230 |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal Code | 7500 |
| BANK_CODE | VARCHAR | 8 | 8 | Bank Account Reference | 1230 |
| INV_REF | VARCHAR | 30 | 30 | Invoice Reference Number | 1 |
| USER_NAME | VARCHAR | 32 | 32 | User name | MANAGER |
| DETAILS | VARCHAR | 60 | 60 | Details | Photocopying |
| EXTRA_REF | VARCHAR | 60 | 60 | Extra Reference |  |
| DISPUTED | SMALLINT | 2 | 5 | Disputed flag | 0 |
| STMT_TEXT | VARCHAR | 60 | 60 | Text for summary statements |  |
| BANK_FLAG | VARCHAR | 1 | 1 | Bank reconciled flag - y/n/- | - |
| VAT_FLAG | VARCHAR | 1 | 1 | VAT reconciled flag - y/n/- | R |
| PAID_FLAG | VARCHAR | 1 | 1 | Transaction paid flag - y/n | Y |
| PAID_STATUS | VARCHAR | 2 | 2 | Transaction disputed/paid status - */p/d*/dp/ |  |
| DEPT_NUMBER | SMALLINT | 4 | 5 | Department number | 2 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Purchasing |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) | T0 |
| DELETED_FLAG | SMALLINT | 2 | 5 | Transaction deleted flag | 0 |
| RTD_FLAG | VARCHAR | 1 | 1 | RTD reconciled flag | N |
| AMOUNT | DOUBLE | 8 | 15 | Amount on VAT return | 2.5 |
| AMOUNT_INVOICE | DOUBLE | 8 | 15 | Amount from invoices on VAT return | 0 |
| AMOUNT_CREDIT | DOUBLE | 8 | 15 | Amount from credits on VAT return | 0 |
| AMOUNT_BANK | DOUBLE | 8 | 15 | Amount from bank/cash transactions on VAT return | 2.5 |
| AMOUNT_JOURNAL | DOUBLE | 8 | 15 | Amount from journals on VAT return | 0 |
| VAT_BOX | SMALLINT | 2 | 5 | Box on VAT return | 7 |
| VAT_TRAN | SMALLINT | 2 | 5 | Type of transaction on VAT reports | 2 |
| VAT_TRAN_NAME | VARCHAR | 63 | 63 | Transaction description on VAT reports | Payments |
| VAT_INCLUDE | SMALLINT | 2 | 5 | Flag if included in VAT return | 1 |
| SPLIT_NUMBER | INTEGER | 4 | 10 | Split number | 56 |
| HEADER_NUMBER | INTEGER | 4 | 10 | Header number | 56 |
| VAT_FLAG_CODE | TINYINT | 1 | 3 | VAT reconciled flag - 0/1 | 1 |
| DATE_FLAG | SMALLINT | 2 | 5 | Transaction date within report criteria | 0 |
| DATE_ENTERED | DATE | 2 | 10 |  | 13/09/2016 00:00:00 |
| VAT_RECONCILED_DATE | DATE | 2 | 10 | VAT Reconciled Date | 31/03/2015 00:00:00 |
| DISPUTE_CODE | SMALLINT | 2 | 5 | Dispute Reason Code | 0 |
| FUND_ID | INTEGER | 4 | 10 | Fund ID | 0 |
| VAT_LEDGER_RETURN_ID | INTEGER | 4 | 10 | VAT Ledger Return ID | 1 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
