---
slug: sage-50-uk-purchase-ledger-columns
title: Sage 50 UK PURCHASE_LEDGER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account Reference | CON001 |
| NAME | VARCHAR | 60 | 60 | Account Name | Concept Stationery Supplies |
| ADDRESS_1 | VARCHAR | 60 | 60 | Account Address Line1 | 66 New Street |
| ADDRESS_2 | VARCHAR | 60 | 60 | Account Address Line2 | Ridgeway |
| ADDRESS_3 | VARCHAR | 60 | 60 | Account Address Line3 | Newcastle upon Tyne |
| ADDRESS_4 | VARCHAR | 60 | 60 | Account Address Line4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Account Address Line5 | NE1 4GF |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Account Address Line1 | 66 New Street |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Account Address Line2 | Ridgeway |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Account Address Line3 | Newcastle upon Tyne |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Account Address Line4 | NE1 4GF |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Account Address Line5 |  |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact Name | Mark Ramsay |
| TELEPHONE | VARCHAR | 30 | 30 | Telephone Number | 0191 643 4343 |
| TELEPHONE_2 | VARCHAR | 30 | 30 | Telephone Number (2) | 0191 643 4344 |
| FAX | VARCHAR | 30 | 30 | Fax Number | 0191 643 4345 |
| E_MAIL | VARCHAR | 255 | 255 | E-Mail Address | newbusinessadvice@sage.com |
| E_MAIL2 | VARCHAR | 255 | 255 | E-Mail Address (2) |  |
| E_MAIL3 | VARCHAR | 255 | 255 | E-Mail Address (3) |  |
| WEB_ADDRESS | VARCHAR | 255 | 255 | World Wide Web Address | www.sage.co.uk |
| TRADE_CONTACT | VARCHAR | 30 | 30 | Trade Contact | Anthony Thane |
| DEL_NAME | VARCHAR | 60 | 60 | Delivery Name | Concept Stationery Supplies |
| DEL_ADDRESS_1 | VARCHAR | 60 | 60 | Delivery Address Line1 | 66 New Street |
| DEL_ADDRESS_2 | VARCHAR | 60 | 60 | Delivery Address Line2 | Ridgeway |
| DEL_ADDRESS_3 | VARCHAR | 60 | 60 | Delivery Address Line3 | Newcastle Upon Tyne |
| DEL_ADDRESS_4 | VARCHAR | 60 | 60 | Delivery Address Line4 |  |
| DEL_ADDRESS_5 | VARCHAR | 60 | 60 | Delivery Address Line5 | NE1 4GF |
| DEL_CONTACT_NAME | VARCHAR | 30 | 30 | Delivery Contact Name | Mark Ramsey |
| DEL_TELEPHONE | VARCHAR | 30 | 30 | Delivery Telephone Number | 0191 643 4343 |
| DEL_FAX | VARCHAR | 30 | 30 | Delivery Fax Number | 0191 643 4344 |
| ANALYSIS_1 | VARCHAR | 30 | 30 | Analysis 1 | North East |
| ANALYSIS_2 | VARCHAR | 30 | 30 | Analysis 2 | Stationery |
| ANALYSIS_3 | VARCHAR | 30 | 30 | Analysis 3 |  |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department Number | 2 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department Name | Purchasing |
| STATUS_NUMBER | SMALLINT | 2 | 5 | Status Number | 0 |
| STATUS_TEXT | VARCHAR | 60 | 60 | Status Text | Open |
| DEF_TAX_CODE | VARCHAR | 3 | 3 | Default tax code (T0 to T99) | T1 |
| DEF_NOM_CODE | VARCHAR | 8 | 8 | Default Nominal Code | 5000 |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | VAT Registration Number | GB988 3453 23 |
| CURRENCY | TINYINT | 1 | 3 | Currency | 1 |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country Code | GB |
| DISCOUNT_RATE | DOUBLE | 8 | 15 | Discount Rate | 10 |
| SETTLEMENT_DISC_RATE | DOUBLE | 8 | 15 | Settlement Discount Rate | 2.5 |
| SETTLEMENT_DUE_DAYS | SMALLINT | 2 | 5 | Settlement Due Days | 30 |
| PAYMENT_DUE_DAYS | SMALLINT | 2 | 5 | Payment Due Days | 45 |
| PAYMENT_DUE_FROM | SMALLINT | 2 | 5 | Payment due from option | 0 |
| PAYMENT_DUE_FROM_TEXT | VARCHAR | 60 | 60 | Payment due from option text | Days after invoice date |
| CREDIT_LIMIT | DOUBLE | 8 | 15 | Credit Limit | 17000 |
| ACCOUNT_ON_HOLD | TINYINT | 1 | 3 | Account On Hold | 0 |
| TERMS | VARCHAR | 30 | 30 | Terms | 45Days Nett |
| RESTRICT_MAIL | SMALLINT | 2 | 5 | Mail On Hold | 0 |
| TERMS_AGREED | SMALLINT | 2 | 5 | Terms Agreed Flag | 1 |
| DATE_ACCOUNT_OPENED | DATE | 2 | 10 | Date Account Opened | 31/12/2011 00:00:00 |
| DATE_NEXT_CREDIT | DATE | 2 | 10 | Date of Next Credit Review |  |
| DATE_LAST_CREDIT | DATE | 2 | 10 | Date of Last Credit Review |  |
| CREDIT_POSITION | VARCHAR | 19 | 19 | Credit Position | Good |
| CREDIT_POS_CODE | SMALLINT | 2 | 5 | Credit Position Code | 0 |
| CAN_CHARGE | SMALLINT | 2 | 5 | Credit Charges can be applied by this Account | 1 |
| USE_BACS | SMALLINT | 2 | 5 | Flag to Use BACS Reference | 1 |
| USE_BSOC | SMALLINT | 2 | 5 | Flag to Use Building Society Reference | 0 |
| BACS_REF | VARCHAR | 60 | 60 | BACS Reference for Electronic Transfer |  |
| BUREAU_CODE | SMALLINT | 2 | 5 | Credit Bureau code | 1 |
| CREDIT_REF | VARCHAR | 60 | 60 | Credit Reference |  |
| DATE_CREDIT_APPLIED | DATE | 2 | 10 | Date of Credit Application |  |
| DATE_CREDIT_RECEIVED | DATE | 2 | 10 | Date Credit Application Received |  |
| OVERRIDE_TAX_CODE | TINYINT | 1 | 3 | Override stock tax code in invoicing | 0 |
| LAST_PAYMENT_DATE | DATE | 2 | 10 | Date of Last Payment | 30/03/2017 00:00:00 |
| FIRST_INV_DATE | DATE | 2 | 10 | Date of First Invoice | 31/12/2011 00:00:00 |
| LAST_INV_DATE | DATE | 2 | 10 | Last Invoice Date | 27/04/2017 00:00:00 |
| BALANCE | DOUBLE | 8 | 15 | Balance | 1644.39 |
| FOREIGN_BALANCE | DOUBLE | 8 | 15 | Foreign Balance | 1644.39 |
| TURNOVER_MTD | DOUBLE | 8 | 15 | Turnover Month To Date | 3858.18 |
| TURNOVER_YTD | DOUBLE | 8 | 15 | Turnover Year To Date | 2213.79 |
| PRIOR_YEAR | DOUBLE | 8 | 15 | Turnover Last Year | 0 |
| BANK_NAME | VARCHAR | 60 | 60 | Bank Name | HSBC Bank |
| BANK_ADDRESS_1 | VARCHAR | 60 | 60 | Bank Address Line1 | 86 New Street |
| BANK_ADDRESS_2 | VARCHAR | 60 | 60 | Bank Address Line2 | Ridgeway |
| BANK_ADDRESS_3 | VARCHAR | 60 | 60 | Bank Address Line3 | Newcastle upon Tyne |
| BANK_ADDRESS_4 | VARCHAR | 60 | 60 | Bank Address Line4 |  |
| BANK_ADDRESS_5 | VARCHAR | 60 | 60 | Bank Address Line5 | NE1 4GF |
| BANK_SORT_CODE | VARCHAR | 10 | 10 | Bank Sort Code | 88-99-99 |
| BANK_ACCOUNT_NAME | VARCHAR | 60 | 60 | Bank Account Name | Concept Stationery Supplies |
| BANK_ACCOUNT_NUMBER | VARCHAR | 60 | 60 | Bank Account Number | 99889988 |
| BANK_IBAN | VARCHAR | 60 | 60 | IBAN Number |  |
| BANK_BIC | VARCHAR | 60 | 60 | BIC/SWIFT Code |  |
| BANK_ROLLNUMBER | VARCHAR | 60 | 60 | Roll number |  |
| BANK_ADDITIONALREF1 | VARCHAR | 60 | 60 | Additional References |  |
| BANK_ADDITIONALREF2 | VARCHAR | 60 | 60 | Additional References |  |
| BANK_ADDITIONALREF3 | VARCHAR | 60 | 60 | Additional References |  |
| DONOR_TITLE | VARCHAR | 4 | 4 | Donor Title |  |
| DONOR_FORENAME | VARCHAR | 35 | 35 | Donor Forename |  |
| DONOR_SURNAME | VARCHAR | 35 | 35 | Donor Surname |  |
| DEFAULT_FUND_ID | INTEGER | 4 | 10 | Default Fund Number | 0 |
| INVOICE_BF | DOUBLE | 8 | 15 | Invoices Brought Forward | 182.13 |
| INVOICE_MTH1 | DOUBLE | 8 | 15 | Invoices Month 1 | 188.58 |
| INVOICE_MTH2 | DOUBLE | 8 | 15 | Invoices Month 2 | 758.61 |
| INVOICE_MTH3 | DOUBLE | 8 | 15 | Invoices Month 3 | 578.41 |
| INVOICE_MTH4 | DOUBLE | 8 | 15 | Invoices Month 4 | 1065.98 |
| INVOICE_MTH5 | DOUBLE | 8 | 15 | Invoices Month 5 | 0 |
| INVOICE_MTH6 | DOUBLE | 8 | 15 | Invoices Month 6 | 0 |
| INVOICE_MTH7 | DOUBLE | 8 | 15 | Invoices Month 7 | 0 |
| INVOICE_MTH8 | DOUBLE | 8 | 15 | Invoices Month 8 | 0 |
| INVOICE_MTH9 | DOUBLE | 8 | 15 | Invoices Month 9 | 0 |
| INVOICE_MTH10 | DOUBLE | 8 | 15 | Invoices Month 10 | 0 |
| INVOICE_MTH11 | DOUBLE | 8 | 15 | Invoices Month 11 | 0 |
| INVOICE_MTH12 | DOUBLE | 8 | 15 | Invoices Month 12 | 0 |
| INVOICE_CF | DOUBLE | 8 | 15 | Invoices Carry Forward | 0 |
| CREDIT_BF | DOUBLE | 8 | 15 | Credits Brought Forward | 0 |
| CREDIT_MTH1 | DOUBLE | 8 | 15 | Credits Month 1 | 0 |
| CREDIT_MTH2 | DOUBLE | 8 | 15 | Credits Month 2 | 0 |
| CREDIT_MTH3 | DOUBLE | 8 | 15 | Credits Month 3 | 0 |
| CREDIT_MTH4 | DOUBLE | 8 | 15 | Credits Month 4 | 0 |
| CREDIT_MTH5 | DOUBLE | 8 | 15 | Credits Month 5 | 0 |
| CREDIT_MTH6 | DOUBLE | 8 | 15 | Credits Month 6 | 0 |
| CREDIT_MTH7 | DOUBLE | 8 | 15 | Credits Month 7 | 0 |
| CREDIT_MTH8 | DOUBLE | 8 | 15 | Credits Month 8 | 0 |
| CREDIT_MTH9 | DOUBLE | 8 | 15 | Credits Month 9 | 0 |
| CREDIT_MTH10 | DOUBLE | 8 | 15 | Credits Month 10 | 0 |
| CREDIT_MTH11 | DOUBLE | 8 | 15 | Credits Month 11 | 0 |
| CREDIT_MTH12 | DOUBLE | 8 | 15 | Credits Month 12 | 0 |
| CREDIT_CF | DOUBLE | 8 | 15 | Credits Carry Forward | 0 |
| PAYMENT_BF | DOUBLE | 8 | 15 | Payments Brought Forward | 0 |
| PAYMENT_MTH1 | DOUBLE | 8 | 15 | Payments Month 1 | 370.71 |
| PAYMENT_MTH2 | DOUBLE | 8 | 15 | Payments Month 2 | 435.14 |
| PAYMENT_MTH3 | DOUBLE | 8 | 15 | Payments Month 3 | 323.47 |
| PAYMENT_MTH4 | DOUBLE | 8 | 15 | Payments Month 4 | 0 |
| PAYMENT_MTH5 | DOUBLE | 8 | 15 | Payments Month 5 | 0 |
| PAYMENT_MTH6 | DOUBLE | 8 | 15 | Payments Month 6 | 0 |
| PAYMENT_MTH7 | DOUBLE | 8 | 15 | Payments Month 7 | 0 |
| PAYMENT_MTH8 | DOUBLE | 8 | 15 | Payments Month 8 | 0 |
| PAYMENT_MTH9 | DOUBLE | 8 | 15 | Payments Month 9 | 0 |
| PAYMENT_MTH10 | DOUBLE | 8 | 15 | Payments Month 10 | 0 |
| PAYMENT_MTH11 | DOUBLE | 8 | 15 | Payments Month 11 | 0 |
| PAYMENT_MTH12 | DOUBLE | 8 | 15 | Payments Month 12 | 0 |
| PAYMENT_CF | DOUBLE | 8 | 15 | Payments Carry Forward | 0 |
| DUNS_NUMBER | VARCHAR | 9 | 9 | DUNS Number |  |
| PRIORITY | SMALLINT | 2 | 5 | Priority | 0 |
| PROMISED_PAYMENT | DOUBLE | 8 | 15 | Latest amount promised to be paid. | 0 |
| PROMISED_PAYMENT_DATE | DATE | 2 | 10 | Date on which the last promise to pay was made. |  |
| REPORT_PASSWORD | VARCHAR | 31 | 31 | Password used to encrypt secure PDFs |  |
| LETTERS_VIA_EMAIL | SMALLINT | 2 | 5 | Send letters via email? | 0 |
| PAYMENT_METHOD_ID | INTEGER | 4 | 10 | Unique ID of the payment method used by this account | 1 |
| DECLARATION_VALID_FROM | DATE | 2 | 10 | Donor Declaration Valid From |  |
| INACTIVE_FLAG | TINYINT | 1 | 3 | Inactive Flag - Yes/No | 0 |
| MANDATEID | VARCHAR | 37 | 37 | Mandate ID |  |
| STATUS | TINYINT | 1 | 3 | Mandate status | 0 |
| STATUS_DESCRIPTION | VARCHAR | 25 | 25 | Mandate status description |  |
| LAST_REFRESHED_DATE |  | 16 | 0 | Date mandate last refreshed |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
