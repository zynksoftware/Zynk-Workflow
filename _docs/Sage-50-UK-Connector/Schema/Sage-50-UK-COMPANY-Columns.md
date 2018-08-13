---
slug: sage-50-uk-company-columns
title: Sage 50 UK COMPANY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| COMPANYID | VARCHAR | 37 | 37 | Unique Company Id | C4C463BE-B098-4A7D-A23B-D1A92B8DCB59 |
| PROTX_VENDOR | VARCHAR | 20 | 20 | Sage Pay Vendor ID |  |
| CASH_REGISTER_BANK | VARCHAR | 8 | 8 | Cash register bank nominal | 1235 |
| CASH_REGISTER_SALES_NOM | VARCHAR | 8 | 8 | Cash register sales nominal | 4000 |
| CASH_REGISTER_TAXCODE | SMALLINT | 2 | 5 | Cash register tax code nominal | 0 |
| CASH_REGISTER_DISCREPENCIES_NOM | VARCHAR | 8 | 8 | Cash register discrepencies nominal | 8206 |
| CASH_REGISTER_TAX_INCLUSIVE_FLAG | TINYINT | 1 | 3 | Cash register tax inclusive flag | 0 |
| QUOTES_TO_ORDERS | SMALLINT | 2 | 5 | Flag denoting if quotes are to be converted to Sales Orders. | 1 |
| PROTX_USERID | VARCHAR | 40 | 40 | Sage Pay User ID |  |
| PROTX_PASSWORD | VARCHAR | 40 | 40 | Sage Pay Password |  |
| PROTX_LAST_SYNC_DATE | VARCHAR | 40 | 40 | Sage Pay Last synchronize date |  |
| PROTX_ENABLED | TINYINT | 1 | 3 | Sage Pay Enabled flag | 0 |
| FLAT_RATE_VAT_PERCENT | DOUBLE | 8 | 15 | Flat Rate VAT Percent | 0 |
| NAME | VARCHAR | 60 | 60 | Company Name | Stationery & Computer Mart UK |
| ADDRESS_1 | VARCHAR | 60 | 60 | Company Address Line1 | Sage House |
| ADDRESS_2 | VARCHAR | 60 | 60 | Company Address Line2 | Benton Park Road |
| ADDRESS_3 | VARCHAR | 60 | 60 | Company Address Line3 | Newcastle Upon Tyne |
| ADDRESS_4 | VARCHAR | 60 | 60 | Company Address Line4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Company Address Line5 | NE7 7 LZ |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Company Address Line1 | Sage House |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Company Address Line2 | Benton Park Road |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Company Address Line3 | Newcastle Upon Tyne |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Company Address Line4 | NE7 7 LZ |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Company Address Line5 |  |
| L_NAME | VARCHAR | 60 | 60 | Company Name for Layouts (can be suppressed) | Stationery & Computer Mart UK |
| L_ADDRESS_1 | VARCHAR | 60 | 60 | Company Address Line1 for Layouts (can be suppressed) | Sage House |
| L_ADDRESS_2 | VARCHAR | 60 | 60 | Company Address Line2 for Layouts (can be suppressed) | Benton Park Road |
| L_ADDRESS_3 | VARCHAR | 60 | 60 | Company Address Line3 for Layouts (can be suppressed) | Newcastle Upon Tyne |
| L_ADDRESS_4 | VARCHAR | 60 | 60 | Company Address Line4 for Layouts (can be suppressed) | NE7 7 LZ |
| L_ADDRESS_5 | VARCHAR | 60 | 60 | Company Address Line5 for Layouts (can be suppressed) |  |
| TELEPHONE | VARCHAR | 30 | 30 | Telephone Number | 0191 955 3000 |
| FAX | VARCHAR | 30 | 30 | Fax Number | 0191 955 3001 |
| E_MAIL | VARCHAR | 255 | 255 | E-Mail Address | newbusinessadvice@sage.com |
| WEB_ADDRESS | VARCHAR | 255 | 255 | World Wide Web Address | http://www.sage.co.uk |
| CREDIT_REF | VARCHAR | 60 | 60 | Credit Reference Number | SM03939302J |
| DEL_NAME | VARCHAR | 60 | 60 | Delivery Name | Stationery & Computer Mart UK Ltd |
| DEL_ADDRESS_1 | VARCHAR | 60 | 60 | Delivery Address Line1 | Sage House |
| DEL_ADDRESS_2 | VARCHAR | 60 | 60 | Delivery Address Line2 | Benton Park Road |
| DEL_ADDRESS_3 | VARCHAR | 60 | 60 | Delivery Address Line3 | Newcastle Upon Tyne |
| DEL_ADDRESS_4 | VARCHAR | 60 | 60 | Delivery Address Line4 |  |
| DEL_ADDRESS_5 | VARCHAR | 60 | 60 | Delivery Address Line5 | NE7 7LZ |
| DEL_TELEPHONE | VARCHAR | 30 | 30 | Delivery Telephone Number | 0191 955 3000 |
| DEL_FAX | VARCHAR | 30 | 30 | Delivery Fax Number | 0191 955 3001 |
| DEL_E_MAIL | VARCHAR | 255 | 255 | Delivery E-Mail Address | newbusinessadvice@sage.com |
| DEL_WEB_ADDRESS | VARCHAR | 255 | 255 | Delivery World Wide Web Address |  |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | VAT Registration Number | 999999999 |
| START_MONTH | TINYINT | 1 | 3 | Start Month of Financial Year (1-12) | 1 |
| FINANCIAL_YEAR | SMALLINT | 2 | 5 | Current Financial Year | 2017 |
| DEFAULT_CHART | SMALLINT | 2 | 5 | Default Chart of Accounts | 1 |
| DEFAULT_CREDIT_BUREAU | SMALLINT | 2 | 5 | Default Credit Bureau | 1 |
| END_OF_REPORT | VARCHAR | 63 | 63 | End of report banner | End of Report |
| ADDRESS_LABEL_1 | VARCHAR | 10 | 10 | Address Label 1 | Street1 |
| ADDRESS_LABEL_2 | VARCHAR | 10 | 10 | Address Label 2 | Street2 |
| ADDRESS_LABEL_3 | VARCHAR | 10 | 10 | Address Label 3 | Town |
| ADDRESS_LABEL_4 | VARCHAR | 10 | 10 | Address Label 4 | County |
| ADDRESS_LABEL_5 | VARCHAR | 10 | 10 | Address Label 5 | Post Code |
| SALES_LABEL_1 | VARCHAR | 10 | 10 | Sales Custom Label 1 | Cust. Type |
| SALES_LABEL_2 | VARCHAR | 10 | 10 | Sales Custom Label 2 | Resp. Rep |
| SALES_LABEL_3 | VARCHAR | 10 | 10 | Sales Custom Label 3 | Region |
| PURCHASE_LABEL_1 | VARCHAR | 10 | 10 | Purchase Custom Label 1 | Region |
| PURCHASE_LABEL_2 | VARCHAR | 10 | 10 | Purchase Custom Label 2 | Supply |
| PURCHASE_LABEL_3 | VARCHAR | 10 | 10 | Purchase Custom Label 3 |  |
| STOCK_LABEL_1 | VARCHAR | 10 | 10 | Stock Label 1 | Category A |
| STOCK_LABEL_2 | VARCHAR | 10 | 10 | Stock Label 2 | Category B |
| STOCK_LABEL_3 | VARCHAR | 10 | 10 | Stock Label 3 | Category C |
| STOCKCATEGORY_LABEL | VARCHAR | 10 | 10 | Stock Category Label | Category |
| DEPARTMENTS_LABEL | VARCHAR | 10 | 10 | Departments Label | Department |
| FIXEDASSETS_LABEL | VARCHAR | 10 | 10 | Fixed Assets Label | Assets |
| STOCK_DISCOUNT_A | VARCHAR | 20 | 20 | Stock Discount A name | Discount A |
| STOCK_DISCOUNT_B | VARCHAR | 20 | 20 | Stock Discount B name | Discount B |
| STOCK_DISCOUNT_C | VARCHAR | 20 | 20 | Stock Discount C name | Discount C |
| STOCK_DISCOUNT_D | VARCHAR | 20 | 20 | Stock Discount D name | Discount D |
| STOCK_DISCOUNT_E | VARCHAR | 20 | 20 | Stock Discount E name | Discount E |
| NOM_DEBTORS | VARCHAR | 10 | 10 | Debtors Control Account | 1100 |
| NOM_CREDITORS | VARCHAR | 10 | 10 | Creditors Control Account | 2100 |
| NOM_TAX_SALES | VARCHAR | 10 | 10 | Sales Tax Control Account | 2200 |
| NOM_TAX_PURCHASE | VARCHAR | 10 | 10 | Purchase Tax Control Account | 2201 |
| NOM_DISCOUNT_SALES | VARCHAR | 10 | 10 | Sales Discount Control Account | 4009 |
| NOM_DISCOUNT_PURCHASE | VARCHAR | 10 | 10 | Purchase Discount Control Account | 5009 |
| NOM_DEFAULT_BANK | VARCHAR | 10 | 10 | Default Bank Control Account | 1200 |
| NOM_DEFAULT_SALES | VARCHAR | 10 | 10 | Default Sales Control Account | 4000 |
| NOM_RETAINED_EARNINGS | VARCHAR | 10 | 10 | Retained Earnings Control Account | 3200 |
| NOM_CREDIT_CHARGES | VARCHAR | 10 | 10 | Credit Charges Control Account | 4400 |
| NOM_BAD_DEBTS | VARCHAR | 10 | 10 | Bad Debts Control Account | 8100 |
| NOM_ACCRUALS | VARCHAR | 10 | 10 | Accruals Control Account | 2109 |
| NOM_PREPAYMENTS | VARCHAR | 10 | 10 | Prepayments Control Account | 1103 |
| NOM_MISPOSTINGS | VARCHAR | 10 | 10 | Mispostings Control Account | 9999 |
| NOM_SUSPENSE | VARCHAR | 10 | 10 | Suspense Control Account | 9998 |
| PAYMENT_DUE_SALES | SMALLINT | 2 | 5 | Default Payment Due Days for Sales | 30 |
| PAYMENT_DUE_PURCHASE | SMALLINT | 2 | 5 | Default Payment Due Days for Purchase | 30 |
| PAYMENT_DUE_FROM_SALES | SMALLINT | 2 | 5 | Payment due from option for sales | 0 |
| PAYMENT_DUE_FROM_SALES_TEXT | VARCHAR | 60 | 60 | Payment due from option text for sales | Days after invoice date |
| PAYMENT_DUE_FROM_PURCHASE | SMALLINT | 2 | 5 | Payment due from option for purchase | 0 |
| PAYMENT_DUE_FROM_PURCHASE_TEXT | VARCHAR | 60 | 60 | Payment due from option text for purchase | Days after invoice date |
| NON_VAT_TAX_CODE | SMALLINT | 2 | 5 | Default tax code for non-VAT transactions | 9 |
| VAT_CASH | TINYINT | 1 | 3 | VAT Cash Accounting Flag | 0 |
| SALES_AGE_BY_MONTH | TINYINT | 1 | 3 | Use Calendar Month Aged Periods | 1 |
| SALES_AGED_PERIOD_1 | SMALLINT | 2 | 5 | Sales Aged Period 1 (days) | 30 |
| SALES_AGED_PERIOD_2 | SMALLINT | 2 | 5 | Sales Aged Period 2 (days) | 60 |
| SALES_AGED_PERIOD_3 | SMALLINT | 2 | 5 | Sales Aged Period 3 (days) | 90 |
| SALES_AGED_PERIOD_4 | SMALLINT | 2 | 5 | Sales Aged Period 4 (days) | 120 |
| PURCHASE_AGE_BY_MONTH | TINYINT | 1 | 3 | Use Calendar Month Aged Periods | 1 |
| PURCHASE_AGED_PERIOD_1 | SMALLINT | 2 | 5 | Purchase Aged Period 1 (days) | 30 |
| PURCHASE_AGED_PERIOD_2 | SMALLINT | 2 | 5 | Purchase Aged Period 2 (days) | 60 |
| PURCHASE_AGED_PERIOD_3 | SMALLINT | 2 | 5 | Purchase Aged Period 3 (days) | 90 |
| PURCHASE_AGED_PERIOD_4 | SMALLINT | 2 | 5 | Purchase Aged Period 4 (days) | 120 |
| SALES_AMOUNT_SOLD_1 | DOUBLE | 8 | 15 | Sales Amount for Discount 1 | 100 |
| SALES_AMOUNT_SOLD_2 | DOUBLE | 8 | 15 | Sales Amount for Discount 2 | 500 |
| SALES_AMOUNT_SOLD_3 | DOUBLE | 8 | 15 | Sales Amount for Discount 3 | 1000 |
| SALES_AMOUNT_SOLD_4 | DOUBLE | 8 | 15 | Sales Amount for Discount 4 | 3000 |
| SALES_AMOUNT_SOLD_5 | DOUBLE | 8 | 15 | Sales Amount for Discount 5 | 5000 |
| SALES_AMOUNT_SOLD_6 | DOUBLE | 8 | 15 | Sales Amount for Discount 6 | 0 |
| SALES_AMOUNT_SOLD_7 | DOUBLE | 8 | 15 | Sales Amount for Discount 7 | 0 |
| SALES_AMOUNT_SOLD_8 | DOUBLE | 8 | 15 | Sales Amount for Discount 8 | 0 |
| SALES_AMOUNT_SOLD_9 | DOUBLE | 8 | 15 | Sales Amount for Discount 9 | 0 |
| SALES_AMOUNT_SOLD_10 | DOUBLE | 8 | 15 | Sales Amount for Discount 10 | 0 |
| SALES_ADD_DISC_1 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 1 | 5 |
| SALES_ADD_DISC_2 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 2 | 7 |
| SALES_ADD_DISC_3 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 3 | 15 |
| SALES_ADD_DISC_4 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 4 | 17 |
| SALES_ADD_DISC_5 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 5 | 20 |
| SALES_ADD_DISC_6 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 6 | 0 |
| SALES_ADD_DISC_7 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 7 | 0 |
| SALES_ADD_DISC_8 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 8 | 0 |
| SALES_ADD_DISC_9 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 9 | 0 |
| SALES_ADD_DISC_10 | DOUBLE | 8 | 15 | Sales Additional Discount Percentage 10 | 0 |
| ALLOW_NEGATIVE_STOCK | SMALLINT | 2 | 5 | Allow negative stock flag | 1 |
| INVOICE_DISC_UNIT_PRICE | TINYINT | 1 | 3 | Discount Unit Price Flag | 0 |
| SOP_CARRIAGE_NET | DOUBLE | 8 | 15 | SOP Default Carriage net amount | 0 |
| SOP_CARRIAGE_NOM_CODE | VARCHAR | 8 | 8 | SOP Default Carriage nominal code |  |
| SOP_CARRIAGE_TAX_CODE | INTEGER | 4 | 10 | SOP Default Carriage tax code | 0 |
| SOP_CARRIAGE_DEPT | INTEGER | 4 | 10 | SOP Default Carriage department | 0 |
| SOP_GLOBAL_DETAILS | VARCHAR | 60 | 60 | SOP Default Global details | Carriage Details |
| SOP_GLOBAL_NOM_CODE | VARCHAR | 8 | 8 | SOP Default Global nominal code |  |
| SOP_GLOBAL_TAX_CODE | INTEGER | 4 | 10 | SOP Default Global tax code | 1 |
| SOP_GLOBAL_DEPT | INTEGER | 4 | 10 | SOP Default Global department | 0 |
| POP_CARRIAGE_NET | DOUBLE | 8 | 15 | POP Default Carriage net amount | 0 |
| POP_CARRIAGE_NOM_CODE | VARCHAR | 8 | 8 | POP Default Carriage nominal code |  |
| POP_CARRIAGE_TAX_CODE | INTEGER | 4 | 10 | POP Default Carriage tax code | 0 |
| POP_CARRIAGE_DEPT | INTEGER | 4 | 10 | POP Default Carriage department | 0 |
| POP_GLOBAL_DETAILS | VARCHAR | 60 | 60 | POP Default Global details | Carriage Details |
| POP_GLOBAL_NOM_CODE | VARCHAR | 8 | 8 | POP Default Global nominal code |  |
| POP_GLOBAL_TAX_CODE | INTEGER | 4 | 10 | POP Default Global tax code | 1 |
| POP_GLOBAL_DEPT | INTEGER | 4 | 10 | POP Default Global department | 0 |
| NO_DISCOUNT_PRICE_LIST | SMALLINT | 2 | 5 | No discount if special or group price | 0 |
| QTY_DECIMAL_PLACE | SMALLINT | 2 | 5 | Number of decimal places for product quantities | 2 |
| UNIT_DECIMAL_PLACE | SMALLINT | 2 | 5 | Number of decimal places for product prices | 2 |
| BUDGETING_METHOD | SMALLINT | 2 | 5 | Method of budgeting | 3 |
| DEFAULT_BUDGETING_CHART | SMALLINT | 2 | 5 | Default chart of accounts used for budgeting | 1 |
| CHARITYTAXREF | VARCHAR | 30 | 30 | Charity Tax Reference |  |
| DUNS_NUMBER | VARCHAR | 9 | 9 | DUNS Number |  |
| CC_LETTER_1 | VARCHAR | 1023 | 1023 | Default layout for Reminder Letter | C:\Documents and Settings\All Users\Application Data\Sage\Accounts\2009\Demodata\Letters\REMIND1C.letter |
| CC_LETTER_2 | VARCHAR | 1023 | 1023 | Default layout for Warning Letter | C:\Documents and Settings\All Users\Application Data\Sage\Accounts\2009\Demodata\Letters\REMIND2C.letter |
| CC_LETTER_3 | VARCHAR | 1023 | 1023 | Default layout for Legal Letter | C:\Documents and Settings\All Users\Application Data\Sage\Accounts\2009\Demodata\Letters\REMIND3C.letter |
| CLOSED_LEDGER_DATE_ENABLED | TINYINT | 1 | 3 | Flag indicating if closed ledger control is currently enforced | 0 |
| CLOSED_LEDGER_CHECK_DATE | DATE | 2 | 10 | The date which a transaction being posted is validated against |  |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country Code | GB |
| HMRC_PAYEE_ENABLED | SMALLINT | 2 | 5 | HMRC Payee Enabled | 0 |
| HMRC_PAYEE_STATUS | TINYINT | 1 | 3 | HMRC Payee Status | 0 |
| HMRC_PAYEE_STATUS_DESCRIPTION | VARCHAR | 30 | 30 | HMRC Payee Status Description | Requires submission |
| DIRECT_DEBITS_ENABLED | SMALLINT | 2 | 5 | Direct Debits Enabled | 0 |
| DIRECT_DEBITS_LAST_SYNCED_DATE |  | 16 | 0 | Direct Debits last synced date |  |
| HOLDING_ACCOUNT | VARCHAR | 8 | 8 | Direct Debits holding bank account |  |
| NOMINATED_BANK | VARCHAR | 8 | 8 | Direct Debits nominated bank account |  |
| FEES_NOMINAL | VARCHAR | 8 | 8 | Direct Debits fees nominal account |  |
| CHARGE_DAYS | SMALLINT | 2 | 5 | Direct Debits charge days before invoice due | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:55 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
