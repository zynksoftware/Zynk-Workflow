---
slug: sage-50-uk-audit-split-columns
title: Sage 50 UK AUDIT_SPLIT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Transaction number | 1 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | SI |
| DATE | DATE | 2 | 10 | Transaction date | 31/12/2016 00:00:00 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales/Purchase/Bank Account Reference | COM001 |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal Code | 9998 |
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
| NET_AMOUNT | DOUBLE | 8 | 15 | Net amount (signed according to transaction type) | 150 |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount (signed according to transaction type) | 0 |
| GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount (signed according to transaction type) | 150 |
| AMOUNT_PAID | DOUBLE | 8 | 15 | Total amount paid | 150 |
| PAYMENT | DOUBLE | 8 | 15 | Amount paid (as Sales Receipt/Purchase Payment) | 0 |
| OUTSTANDING | DOUBLE | 8 | 15 | Amount outstanding (against invoice/credit) | 0 |
| FOREIGN_OUTSTANDING | DOUBLE | 8 | 15 | Amount outstanding (against invoice/credit) | 0 |
| RTD_FLAG | VARCHAR | 1 | 1 | RTD reconciled flag | - |
| FOREIGN_NET_AMOUNT | DOUBLE | 8 | 15 | Net amount in foreign currency (signed according to transaction type) | 150 |
| FOREIGN_TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount in foreign currency (signed according to transaction type) | 0 |
| FOREIGN_GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount in foreign currency (signed according to transaction type) | 150 |
| FOREIGN_AMOUNT_PAID | DOUBLE | 8 | 15 | Total amount paid in foreign currency | 150 |
| AGED_BALANCE | DOUBLE | 8 | 15 | Gross towards current balance | 0 |
| AGED_FUTURE | DOUBLE | 8 | 15 | Gross in future period | 0 |
| AGED_CURRENT | DOUBLE | 8 | 15 | Gross in current period (eg 0-29 days) | 0 |
| AGED_30 | DOUBLE | 8 | 15 | Gross in 1st period (eg 30-59 days) | 0 |
| AGED_60 | DOUBLE | 8 | 15 | Gross in 2nd period (eg 60-89 days) | 0 |
| AGED_90 | DOUBLE | 8 | 15 | Gross in 3rd period (eg 90-119 days) | 0 |
| AGED_OLDER | DOUBLE | 8 | 15 | Gross beyond 3rd period (eg 120 days and older) | 0 |
| AGED_CUM_CURRENT | DOUBLE | 8 | 15 | Gross in current period and beyond (eg all older) | 0 |
| AGED_CUM_30 | DOUBLE | 8 | 15 | Gross in 1st period and beyond (eg 30 days and older) | 0 |
| AGED_CUM_60 | DOUBLE | 8 | 15 | Gross in 2nd period and beyond (eg 60 days and older) | 0 |
| AGED_CUM_90 | DOUBLE | 8 | 15 | Gross in 3rd period and beyond (eg 90 days and older) | 0 |
| FOREIGN_AGED_BALANCE | DOUBLE | 8 | 15 | Gross (foreign currency) towards current balance | 0 |
| FOREIGN_AGED_FUTURE | DOUBLE | 8 | 15 | Gross (foreign currency) in future period | 0 |
| FOREIGN_AGED_CURRENT | DOUBLE | 8 | 15 | Gross (foreign currency) in current period (eg 0-29 days) | 0 |
| FOREIGN_AGED_30 | DOUBLE | 8 | 15 | Gross (foreign currency) in 1st period (eg 30-59 days) | 0 |
| FOREIGN_AGED_60 | DOUBLE | 8 | 15 | Gross (foreign currency) in 2nd period (eg 60-89 days) | 0 |
| FOREIGN_AGED_90 | DOUBLE | 8 | 15 | Gross (foreign currency) in 3rd period (eg 90-119 days) | 0 |
| FOREIGN_AGED_OLDER | DOUBLE | 8 | 15 | Gross (foreign currency) beyond 3rd period (eg 120 days and older) | 0 |
| FOREIGN_AGED_CUM_CURRENT | DOUBLE | 8 | 15 | Gross (foreign currency) in current period and beyond (eg all older) | 0 |
| FOREIGN_AGED_CUM_30 | DOUBLE | 8 | 15 | Gross (foreign currency) in 1st period and beyond (eg 30 days and older) | 0 |
| FOREIGN_AGED_CUM_60 | DOUBLE | 8 | 15 | Gross (foreign currency) in 2nd period and beyond (eg 60 days and older) | 0 |
| FOREIGN_AGED_CUM_90 | DOUBLE | 8 | 15 | Gross (foreign currency) in 3rd period and beyond (eg 90 days and older) | 0 |
| SPLIT_NUMBER | INTEGER | 4 | 10 | Split number | 1 |
| HEADER_NUMBER | INTEGER | 4 | 10 | Header number | 1 |
| VAT_FLAG_CODE | TINYINT | 1 | 3 | VAT reconciled flag - 0/1 | 0 |
| DATE_FLAG | SMALLINT | 2 | 5 | Transaction date within report criteria | 0 |
| DATE_ENTERED | DATE | 2 | 10 |  | 13/09/2016 00:00:00 |
| VAT_RECONCILED_DATE | DATE | 2 | 10 | VAT Reconciled Date |  |
| DISPUTE_CODE | SMALLINT | 2 | 5 | Dispute Reason Code | 0 |
| FUND_ID | INTEGER | 4 | 10 | Fund ID | 0 |
| VAT_LEDGER_RETURN_ID | INTEGER | 4 | 10 | VAT Ledger Return ID | 0 |
| GIFT_AID | SMALLINT | 2 | 5 | Donation flagged as eligible for Gift Aid status | 0 |
| SMALL_DONATION | SMALLINT | 2 | 5 | Donation flagged as eligible for tax relief under the Small Donations Scheme | 0 |
| GASDS_CLAIM_SUBMITTED | SMALLINT | 2 | 5 | Donation that has been submitted to HMRC as part of a repayment claim under the Gift Aid Small Donations Scheme | 0 |
| HAS_EXTERNAL_LINK | CHAR | 1 | 1 | Does this split have an external link. | Y |
| PROJECT_ID | SMALLINT | 4 | 5 | Project ID | 0 |
| COST_CODE_ID | INTEGER | 4 | 10 | Cost Code ID | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
