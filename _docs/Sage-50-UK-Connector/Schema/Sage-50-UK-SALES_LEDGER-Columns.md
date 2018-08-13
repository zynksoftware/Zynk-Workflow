---
slug: sage-50-uk-sales-ledger-columns
title: Sage 50 UK SALES_LEDGER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account Reference | A1D001 |
| NAME | VARCHAR | 60 | 60 | Account Name | A1 Design Services |
| ADDRESS_1 | VARCHAR | 60 | 60 | Account Address Line1 | 67a Station Road |
| ADDRESS_2 | VARCHAR | 60 | 60 | Account Address Line2 |  |
| ADDRESS_3 | VARCHAR | 60 | 60 | Account Address Line3 | Blackpool |
| ADDRESS_4 | VARCHAR | 60 | 60 | Account Address Line4 | Lancashire |
| ADDRESS_5 | VARCHAR | 60 | 60 | Account Address Line5 | BP12 7HT |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Account Address Line1 | 67a Station Road |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Account Address Line2 | Blackpool |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Account Address Line3 | Lancashire |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Account Address Line4 | BP12 7HT |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Account Address Line5 |  |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact Name | Ian Cairns |
| TELEPHONE | VARCHAR | 30 | 30 | Telephone Number | 01742 876 234 |
| TELEPHONE_2 | VARCHAR | 30 | 30 | Telephone Number (2) | 01742 876 235 |
| FAX | VARCHAR | 30 | 30 | Fax Number | 01742 876 236 |
| E_MAIL | VARCHAR | 255 | 255 | E-Mail Address | newbusinessadvice@sage.com |
| E_MAIL2 | VARCHAR | 255 | 255 | E-Mail Address (2) |  |
| E_MAIL3 | VARCHAR | 255 | 255 | E-Mail Address (3) |  |
| DIRECT_DEBITS_EMAIL | VARCHAR | 255 | 255 | Direct Debit Email | newbusinessadvice@sage.com |
| WEB_ADDRESS | VARCHAR | 255 | 255 | World Wide Web Address | www.sage.co.uk |
| TRADE_CONTACT | VARCHAR | 30 | 30 | Trade Contact | Malcolm Leverret |
| DEL_NAME | VARCHAR | 60 | 60 | Delivery Name | A1 Design Services |
| DEL_ADDRESS_1 | VARCHAR | 60 | 60 | Delivery Address Line1 | 67a Station Road |
| DEL_ADDRESS_2 | VARCHAR | 60 | 60 | Delivery Address Line2 |  |
| DEL_ADDRESS_3 | VARCHAR | 60 | 60 | Delivery Address Line3 | Blackpool |
| DEL_ADDRESS_4 | VARCHAR | 60 | 60 | Delivery Address Line4 | Lancashire |
| DEL_ADDRESS_5 | VARCHAR | 60 | 60 | Delivery Address Line5 | BP12 7HT |
| DEL_CONTACT_NAME | VARCHAR | 30 | 30 | Delivery Contact Name | Jim Thomas |
| DEL_TELEPHONE | VARCHAR | 30 | 30 | Delivery Telephone Number | 01742 876 234 |
| DEL_FAX | VARCHAR | 30 | 30 | Delivery Fax Number | 01742 876 235 |
| ANALYSIS_1 | VARCHAR | 30 | 30 | Analysis 1 | Trade |
| ANALYSIS_2 | VARCHAR | 30 | 30 | Analysis 2 | George |
| ANALYSIS_3 | VARCHAR | 30 | 30 | Analysis 3 | Lancashire |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department Number | 0 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department Name | Default |
| STATUS_NUMBER | SMALLINT | 2 | 5 | Status Number | 0 |
| STATUS_TEXT | VARCHAR | 60 | 60 | Status Text | Open |
| DEF_TAX_CODE | VARCHAR | 3 | 3 | Default tax code (T0 to T99) | T1 |
| DEF_NOM_CODE | VARCHAR | 8 | 8 | Default Nominal Code | 4000 |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | VAT Registration Number | GB238 3839 38 |
| CURRENCY | TINYINT | 1 | 3 | Currency | 1 |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country Code | GB |
| DISCOUNT_TYPE | TINYINT | 1 | 3 | Discount Type (inv total/stock record) | 0 |
| DISCOUNT_RATE | DOUBLE | 8 | 15 | Discount Rate | 0 |
| PRICING_REF | VARCHAR | 8 | 8 | Default Price List | TRADEA |
| SETTLEMENT_DISC_RATE | DOUBLE | 8 | 15 | Settlement Discount Rate | 2.5 |
| SETTLEMENT_DUE_DAYS | SMALLINT | 2 | 5 | Settlement Due Days | 15 |
| PAYMENT_DUE_DAYS | SMALLINT | 2 | 5 | Payment Due Days | 30 |
| PAYMENT_DUE_FROM | SMALLINT | 2 | 5 | Payment due from option | 0 |
| PAYMENT_DUE_FROM_TEXT | VARCHAR | 60 | 60 | Payment due from option text | Days after invoice date |
| CREDIT_LIMIT | DOUBLE | 8 | 15 | Credit Limit | 1000 |
| ACCOUNT_ON_HOLD | TINYINT | 1 | 3 | Account On Hold | 0 |
| TERMS | VARCHAR | 30 | 30 | Terms | 30 days nett |
| RESTRICT_MAIL | SMALLINT | 2 | 5 | Mail On Hold | 1 |
| TERMS_AGREED | SMALLINT | 2 | 5 | Terms Agreed Flag | 1 |
| DATE_ACCOUNT_OPENED | DATE | 2 | 10 | Date Account Opened | 02/01/2017 00:00:00 |
| DATE_NEXT_CREDIT | DATE | 2 | 10 | Date of Next Credit Review | 01/02/2018 00:00:00 |
| DATE_LAST_CREDIT | DATE | 2 | 10 | Date of Last Credit Review | 04/12/2017 00:00:00 |
| CREDIT_POSITION | VARCHAR | 19 | 19 | Credit Position | Good |
| CREDIT_POS_CODE | SMALLINT | 2 | 5 | Credit Position Code | 0 |
| CAN_CHARGE | SMALLINT | 2 | 5 | Can Apply Credit Charges to this Account | 1 |
| USE_BACS | SMALLINT | 2 | 5 | Flag to Use BACS Reference | 0 |
| BACS_REF | VARCHAR | 60 | 60 | BACS Reference for Electronic Transfer |  |
| BUREAU_CODE | SMALLINT | 2 | 5 | Credit Bureau code | 2 |
| CREDIT_REF | VARCHAR | 60 | 60 | Credit Reference | TS3811 |
| DATE_CREDIT_APPLIED | DATE | 2 | 10 | Date of Credit Application | 02/01/2017 00:00:00 |
| DATE_CREDIT_RECEIVED | DATE | 2 | 10 | Date Credit Application Received | 02/01/2017 00:00:00 |
| OVERRIDE_TAX_CODE | TINYINT | 1 | 3 | Override stock tax code in invoicing | 0 |
| LAST_PAYMENT_DATE | DATE | 2 | 10 | Date of Last Payment | 27/04/2017 00:00:00 |
| FIRST_INV_DATE | DATE | 2 | 10 | Date of First Invoice | 02/01/2017 00:00:00 |
| AVERAGE_PAY_DAYS | DOUBLE | 8 | 15 | Average Time To Pay | 0 |
| LAST_INV_DATE | DATE | 2 | 10 | Last Invoice Date | 15/03/2017 00:00:00 |
| BALANCE | DOUBLE | 8 | 15 | Balance | 0 |
| FOREIGN_BALANCE | DOUBLE | 8 | 15 | Foreign Balance | 0 |
| TURNOVER_MTD | DOUBLE | 8 | 15 | Turnover Month To Date | 5220.54 |
| TURNOVER_YTD | DOUBLE | 8 | 15 | Turnover Year To Date | 5220.54 |
| PRIOR_YEAR | DOUBLE | 8 | 15 | Turnover Last Year | 0 |
| BANK_NAME | VARCHAR | 60 | 60 | Bank Name |  |
| BANK_ADDRESS_1 | VARCHAR | 60 | 60 | Bank Address Line1 |  |
| BANK_ADDRESS_2 | VARCHAR | 60 | 60 | Bank Address Line2 |  |
| BANK_ADDRESS_3 | VARCHAR | 60 | 60 | Bank Address Line3 |  |
| BANK_ADDRESS_4 | VARCHAR | 60 | 60 | Bank Address Line4 |  |
| BANK_ADDRESS_5 | VARCHAR | 60 | 60 | Bank Address Line5 |  |
| BANK_SORT_CODE | VARCHAR | 10 | 10 | Bank Sort Code |  |
| BANK_ACCOUNT_NAME | VARCHAR | 60 | 60 | Bank Account Name |  |
| BANK_ACCOUNT_NUMBER | VARCHAR | 60 | 60 | Bank Account Number |  |
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
| GIFT_AID | SMALLINT | 2 | 5 | Gift Aid is enabled | 0 |
| INVOICE_BF | DOUBLE | 8 | 15 | Invoices Brought Forward | 0 |
| INVOICE_MTH1 | DOUBLE | 8 | 15 | Invoices Month 1 | 1432.17 |
| INVOICE_MTH2 | DOUBLE | 8 | 15 | Invoices Month 2 | 3511.88 |
| INVOICE_MTH3 | DOUBLE | 8 | 15 | Invoices Month 3 | 1173.07 |
| INVOICE_MTH4 | DOUBLE | 8 | 15 | Invoices Month 4 | 0 |
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
| PAYMENT_MTH1 | DOUBLE | 8 | 15 | Payments Month 1 | 1432.17 |
| PAYMENT_MTH2 | DOUBLE | 8 | 15 | Payments Month 2 | 0 |
| PAYMENT_MTH3 | DOUBLE | 8 | 15 | Payments Month 3 | 3511.88 |
| PAYMENT_MTH4 | DOUBLE | 8 | 15 | Payments Month 4 | 1173.07 |
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
| PROMISED_PAYMENT | DOUBLE | 8 | 15 | Latest amount promised to be paid. | 500 |
| PROMISED_PAYMENT_DATE | DATE | 2 | 10 | Date on which the last promise to pay was made. | 25/09/2008 00:00:00 |
| REPORT_PASSWORD | VARCHAR | 31 | 31 | Password used to encrypt secure PDFs |  |
| LETTERS_VIA_EMAIL | SMALLINT | 2 | 5 | Send letters via email? | 0 |
| PAYMENT_METHOD_ID | INTEGER | 4 | 10 | Unique ID of the payment method used by this account | 3 |
| DECLARATION_VALID_FROM | DATE | 2 | 10 | Donor Declaration Valid From |  |
| INACTIVE_FLAG | TINYINT | 1 | 3 | Inactive Flag - Yes/No | 0 |
| MANDATEID | VARCHAR | 37 | 37 | Mandate ID |  |
| STATUS | TINYINT | 1 | 3 | Mandate status | 0 |
| STATUS_DESCRIPTION | VARCHAR | 25 | 25 | Mandate status description |  |
| LAST_REFRESHED_DATE |  | 16 | 0 | Date mandate last refreshed |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
