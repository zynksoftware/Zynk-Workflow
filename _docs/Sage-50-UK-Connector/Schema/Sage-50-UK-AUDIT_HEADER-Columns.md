---
slug: sage-50-uk-audit-header-columns
title: Sage 50 UK AUDIT_HEADER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Item number | 1 |
| ITEM_COUNT | INTEGER | 4 | 10 | No of items for this header | 1 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | SI |
| DATE | DATE | 2 | 10 | Transaction date | 31/12/2016 00:00:00 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales/Purchase/Bank Account Reference | COM001 |
| SALES_PURCHASE_REF | VARCHAR | 8 | 8 | Sales/Purchase Account Reference | COM001 |
| BANK_CODE | VARCHAR | 8 | 8 | Bank Account Reference |  |
| BANK_NAME | VARCHAR | 60 | 60 | Bank Account Name |  |
| INV_REF | VARCHAR | 30 | 30 | Invoice Reference Number | O/BAL |
| INV_REF_NUMERIC | INTEGER | 4 | 10 | Numeric version of INV_REF (NB not always the corresponding invoice number) | 0 |
| USER_NAME | VARCHAR | 32 | 32 | User name | MANAGER |
| DETAILS | VARCHAR | 60 | 60 | Details | Opening Balance |
| DUE_DATE | DATE | 2 | 10 | Due date | 14/02/2017 00:00:00 |
| LAST_CHARGE_DATE | DATE | 2 | 10 | Date Charges Last Applied |  |
| FINANCE_CHARGE | TINYINT | 1 | 3 | Finance Charge flag | 0 |
| INTEREST_RATE | DOUBLE | 8 | 15 | Interest Rate | 0 |
| ELECTRONIC_TRANS | SMALLINT | 2 | 5 | Electronic Transaction | 0 |
| DISPUTED | SMALLINT | 2 | 5 | Number of Disputed items | 0 |
| PAID_FLAG | VARCHAR | 1 | 1 | Transaction paid flag - y/n | Y |
| PAID_STATUS | VARCHAR | 2 | 2 | Transaction disputed/paid status - */p/d*/dp |  |
| DELETED_FLAG | SMALLINT | 2 | 5 | Transaction deleted flag | 0 |
| DATE_FLAG | SMALLINT | 2 | 5 | Transaction date within report criteria | 0 |
| DATE_BF | DATE | 2 | 10 | Report criteria date Brought forward |  |
| DATE_FROM | DATE | 2 | 10 | Report criteria date from |  |
| DATE_TO | DATE | 2 | 10 | Report criteria date to |  |
| NET_AMOUNT | DOUBLE | 8 | 15 | Net amount (signed according to transaction type) | 150 |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount (signed according to transaction type) | 0 |
| GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount (signed according to transaction type) | 150 |
| BANK_AMOUNT | DOUBLE | 8 | 15 | Gross amount (signed for use in bank statements) | -150 |
| AMOUNT_PAID | DOUBLE | 8 | 15 | Total amount paid (allocated against invoice/credit) | 150 |
| PAYMENT | DOUBLE | 8 | 15 | Amount paid (as Sales Receipt/Purchase Payment/Payment on Account) | 0 |
| OUTSTANDING | DOUBLE | 8 | 15 | Amount outstanding (against invoice/credit) | 0 |
| FOREIGN_OUTSTANDING | DOUBLE | 8 | 15 | Amount outstanding (against invoice/credit) | 0 |
| FOREIGN_NET_AMOUNT | DOUBLE | 8 | 15 | Net amount in foreign currency (signed according to transaction type) | 150 |
| FOREIGN_TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount in foreign currency (signed according to transaction type) | 0 |
| FOREIGN_GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount in foreign currency (signed according to transaction type) | 150 |
| FOREIGN_AMOUNT_PAID | DOUBLE | 8 | 15 | Total amount paid in foreign currency (allocated against invoice/credit) | 150 |
| FOREIGN_BANK_AMOUNT | DOUBLE | 8 | 15 | Gross amount in foreign currency (signed for use in bank statements) | -150 |
| CURRENCY | TINYINT | 1 | 3 | Which foreign currency | 1 |
| CURRENCY_TYPE | TINYINT | 1 | 3 | Foreign or Euro currency | 0 |
| EURO_GROSS | DOUBLE | 8 | 15 | Gross amount in Euros | 0 |
| EURO_RATE | DOUBLE | 8 | 15 | Euro exchange rate | 0 |
| FOREIGN_RATE | DOUBLE | 8 | 15 | Foreign currency exchange rate | 1 |
| IS_DISCOUNT | SMALLINT | 2 | 5 | Transaction is a discount | 0 |
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
| BANK_FLAG | VARCHAR | 1 | 1 | Bank reconciled flag | - |
| HEADER_NUMBER | INTEGER | 4 | 10 | Header number | 1 |
| DATE_ENTERED | DATE | 2 | 10 |  | 13/09/2017 00:00:00 |
| DATE_BANK_RECONCILED | DATE | 2 | 10 | Bank Reconciliation date |  |
| CIS_RECONCILED | SMALLINT | 2 | 5 | This transaction has been CIS reconciled | 0 |
| SPS_REF | VARCHAR | 63 | 63 | Sage Payment Solutions reference |  |
| DEPOSIT_DATE | DATE | 2 | 10 | Bank Deposited date | 01/02/1974 00:00:00 |
| DEPOSIT_FLAG | VARCHAR | 1 | 1 | Bank deposited flag | - |
| RECURRING_ENTRY_ID | INTEGER | 4 | 10 | Unique ID of the Recurring Entry (if applicable) that this header was generated by. | 0 |
| ISP_REFERENCE | INTEGER | 4 | 10 | Inv/Sop/Pop Reference | 0 |
| OVERRIDDEN_CLOSED_LEDGER_DATE | DATE | 2 | 10 | The financial control date that was overridden at the time of posting |  |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country the transaction applies to |  |
| TAX_ID | VARCHAR | 20 | 20 | Tax Id the transaction applies to. |  |
| REVAL_TRANSACTION_FLAG | SMALLINT | 2 | 5 | Revaluation transaction flag. | 0 |
| POSTED_BY_DIRECT_DEBIT_SETTLEMENT | SMALLINT | 2 | 5 | Transaction posted as part of a direct debit settlement flag | 0 |
| DATE_AMENDED | DATE | 2 | 10 | Date this transaction was last amended |  |
| USER_NAME_AMENDED | VARCHAR | 32 | 32 | User who last amended this transaction |  |
| RECORD_CREATE_DATE | DATE | 16 | 10 | Date and time when the record was created. | 15/04/2130 00:00:00 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:51 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
