---
slug: sage-50-uk-audit-journal-columns
title: Sage 50 UK AUDIT_JOURNAL Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Transaction number | 1 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | SI |
| DATE | DATE | 2 | 10 | Transaction date | 31/12/2016 00:00:00 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales/Purchase/Bank Account Reference | COM001 |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal Code | 1100 |
| BANK_CODE | VARCHAR | 8 | 8 | Bank Account Reference |  |
| INV_REF | VARCHAR | 30 | 30 | Invoice Reference Number | O/BAL |
| USER_NAME | VARCHAR | 32 | 32 | User name | MANAGER |
| DETAILS | VARCHAR | 60 | 60 | Details | Opening Balance |
| EXTRA_REF | VARCHAR | 60 | 60 | Extra Reference |  |
| DISPUTED | SMALLINT | 2 | 5 | Disputed flag | 0 |
| STMT_TEXT | VARCHAR | 60 | 60 | Text for summary statements | Goods/Services |
| BANK_FLAG | VARCHAR | 1 | 1 | Bank reconciled flag - y/n/- | - |
| VAT_FLAG | VARCHAR | 1 | 1 | VAT reconciled flag - y/n/- | - |
| PAID_FLAG | VARCHAR | 1 | 1 | Transaction paid flag - y/n | Y |
| PAID_STATUS | VARCHAR | 2 | 2 | Transaction disputed/paid status - */p/d*/dp/ |  |
| DEPT_NUMBER | SMALLINT | 4 | 5 | Department number | 0 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Default |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) | T9 |
| DELETED_FLAG | SMALLINT | 2 | 5 | Transaction deleted flag | 0 |
| AMOUNT | DOUBLE | 8 | 15 | Signed amount (credits negative) | 150 |
| FOREIGN_AMOUNT | DOUBLE | 8 | 15 | Signed amount (foreign currency, credits negative) | 150 |
| RTD_FLAG | VARCHAR | 1 | 1 | RTD reconciled flag | - |
| SPLIT_NUMBER | INTEGER | 4 | 10 | Split number | 1 |
| HEADER_NUMBER | INTEGER | 4 | 10 | Header number | 1 |
| VAT_FLAG_CODE | TINYINT | 1 | 3 | VAT reconciled flag - 0/1 | 0 |
| DATE_FLAG | SMALLINT | 2 | 5 | Transaction date within report criteria | 0 |
| DATE_ENTERED | DATE | 2 | 10 |  | 13/09/2016 00:00:00 |
| VAT_RECONCILED_DATE | DATE | 2 | 10 | VAT Reconciled Date |  |
| DISPUTE_CODE | SMALLINT | 2 | 5 | Dispute Reason Code | 0 |
| FUND_ID | INTEGER | 4 | 10 | Fund ID | 0 |
| VAT_LEDGER_RETURN_ID | INTEGER | 4 | 10 | VAT Ledger Return ID | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
