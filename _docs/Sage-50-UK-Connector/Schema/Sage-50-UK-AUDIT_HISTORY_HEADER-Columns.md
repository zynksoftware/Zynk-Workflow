---
slug: sage-50-uk-audit-history-header-columns
title: Sage 50 UK AUDIT_HISTORY_HEADER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TRAN_NUMBER | INTEGER | 4 | 10 | Item number |  |
| ITEM_COUNT | INTEGER | 4 | 10 | No of items for this header |  |
| TYPE | VARCHAR | 2 | 2 | Transaction type |  |
| DATE | DATE | 2 | 10 | Transaction date |  |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Sales/Purchase/Bank Account Reference |  |
| SALES_PURCHASE_REF | VARCHAR | 8 | 8 | Sales/Purchase Account Reference |  |
| BANK_CODE | VARCHAR | 8 | 8 | Bank Account Reference |  |
| INV_REF | VARCHAR | 8 | 8 | Invoice Reference Number |  |
| USER_NAME | VARCHAR | 32 | 32 | User name |  |
| DETAILS | VARCHAR | 60 | 60 | Details |  |
| DUE_DATE | DATE | 2 | 10 | Due date |  |
| LAST_CHARGE_DATE | DATE | 2 | 10 | Date Charges Last Applied |  |
| FINANCE_CHARGE | TINYINT | 1 | 3 | Finance Charge flag |  |
| INTEREST_RATE | DOUBLE | 8 | 15 | Interest Rate |  |
| ELECTRONIC_TRANS | SMALLINT | 2 | 5 | Electronic Transaction |  |
| DISPUTED | SMALLINT | 2 | 5 | Number of Disputed items |  |
| PAID_FLAG | VARCHAR | 1 | 1 | Transaction paid flag - y/n |  |
| PAID_STATUS | VARCHAR | 2 | 2 | Transaction disputed/paid status - */p/d*/dp |  |
| DELETED_FLAG | SMALLINT | 2 | 5 | Transaction deleted flag |  |
| NET_AMOUNT | DOUBLE | 8 | 15 | Net amount (signed according to transaction type) |  |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount (signed according to transaction type) |  |
| GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount (signed according to transaction type) |  |
| BANK_AMOUNT | DOUBLE | 8 | 15 | Gross amount (signed for use in bank statements) |  |
| AMOUNT_PAID | DOUBLE | 8 | 15 | Total amount paid (allocated against invoice/credit) |  |
| FOREIGN_NET_AMOUNT | DOUBLE | 8 | 15 | Net amount in foreign currency (signed according to transaction type) |  |
| FOREIGN_TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount in foreign currency (signed according to transaction type) |  |
| FOREIGN_GROSS_AMOUNT | DOUBLE | 8 | 15 | Gross amount in foreign currency (signed according to transaction type) |  |
| FOREIGN_AMOUNT_PAID | DOUBLE | 8 | 15 | Total amount paid in foreign currency (allocated against invoice/credit) |  |
| FOREIGN_BANK_AMOUNT | DOUBLE | 8 | 15 | Gross amount in foreign currency (signed for use in bank statements) |  |
| CURRENCY | TINYINT | 1 | 3 | Which foreign currency |  |
| CURRENCY_TYPE | TINYINT | 1 | 3 | Foreign or Euro currency |  |
| EURO_GROSS | DOUBLE | 8 | 15 | Gross amount in Euros |  |
| EURO_RATE | DOUBLE | 8 | 15 | Euro exchange rate |  |
| FOREIGN_RATE | DOUBLE | 8 | 15 | Foreign currency exchange rate |  |
| BANK_FLAG | VARCHAR | 1 | 1 | Bank reconciled flag |  |
| HEADER_NUMBER | INTEGER | 4 | 10 | Header number |  |
| DATE_ENTERED | DATE | 2 | 10 |  |  |
| DATE_BANK_RECONCILED | DATE | 2 | 10 | Bank Reconciliation date |  |
| CATE_ID | INTEGER | 4 | 10 | Clear Audit Trail Event ID |  |
| CIS_RECONCILED | SMALLINT | 2 | 5 | This transaction has been CIS reconciled |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
