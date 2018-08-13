---
slug: sage-50-uk-bank-statement-columns
title: Sage 50 UK BANK_STATEMENT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Bank Account Reference |  |
| STATEMENT_REF | VARCHAR | 30 | 30 | Statement Reference |  |
| CLOSING_BALANCE | DOUBLE | 8 | 15 | Closing Balance |  |
| OPENING_BALANCE | DOUBLE | 8 | 15 | Opening Balance |  |
| AMOUNT_IN | DOUBLE | 8 | 15 | Total paid in during this statement |  |
| AMOUNT_OUT | DOUBLE | 8 | 15 | Total paid out during this statement |  |
| INTEREST | DOUBLE | 8 | 15 | Interest Amount |  |
| INTEREST_ID | INTEGER | 4 | 10 | Interest Row ID |  |
| INTEREST_NOM_CODE | VARCHAR | 8 | 8 | Nominal Code for Interest |  |
| CHARGES | DOUBLE | 8 | 15 | Charges Amount |  |
| CHARGES_ID | INTEGER | 4 | 10 | Charges Row ID |  |
| CHARGES_NOM_CODE | VARCHAR | 8 | 8 | Nominal Code for Charges |  |
| STATEMENT_DATE | DATE | 2 | 10 | Statement Date |  |
| INTEREST_DATE | DATE | 2 | 10 | Interest Date |  |
| CHARGES_DATE | DATE | 2 | 10 | Charges Date |  |
| RECONCILIATION_DATE | DATE | 2 | 10 | Reconciliation Date |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
