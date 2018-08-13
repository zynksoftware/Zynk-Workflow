---
slug: sage-50-uk-sales-order-columns
title: Sage 50 UK SALES_ORDER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ORDER_NUMBER | INTEGER | 4 | 10 | Order number | 1 |
| ORDER_TYPE_CODE | TINYINT | 1 | 3 | Type code | 0 |
| ORDER_OR_QUOTE | VARCHAR | 60 | 60 | Order/Quote/Proforma label | Sales Order |
| ORDER_DATE | DATE | 2 | 10 | Order Date | 02/01/2016 00:00:00 |
| DESPATCH_DATE | DATE | 2 | 10 | Despatch date |  |
| ALLOCATED_STATUS_CODE | TINYINT | 1 | 3 | Allocated status code | 0 |
| ALLOCATED_STATUS | VARCHAR | 60 | 60 | Allocated status description |  |
| DESPATCH_STATUS_CODE | TINYINT | 1 | 3 | Despatch status code | 2 |
| DESPATCH_STATUS | VARCHAR | 60 | 60 | Despatch status description | Complete |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account reference | KIN001 |
| NAME | VARCHAR | 60 | 60 | Name | Kinghorn & French |
| ADDRESS_1 | VARCHAR | 60 | 60 | Address line 1 | 98 Cathedral Gardens |
| ADDRESS_2 | VARCHAR | 60 | 60 | Address line 2 | Benfield Rd |
| ADDRESS_3 | VARCHAR | 60 | 60 | Address line 3 | Newcastle upon Tyne |
| ADDRESS_4 | VARCHAR | 60 | 60 | Address line 4 | Tyne & Wear |
| ADDRESS_5 | VARCHAR | 60 | 60 | Address line 5 | NE19 1GH |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Address line 1 | 98 Cathedral Gardens |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Address line 2 | Benfield Rd |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Address line 3 | Newcastle upon Tyne |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Address line 4 | Tyne & Wear |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Address line 5 | NE19 1GH |
| DEL_NAME | VARCHAR | 60 | 60 | Delivery name | Kinghorn & French |
| DEL_ADDRESS_1 | VARCHAR | 60 | 60 | Delivery address line 1 | 98 Cathedral Gardens |
| DEL_ADDRESS_2 | VARCHAR | 60 | 60 | Delivery address line 2 | Benfied Rd |
| DEL_ADDRESS_3 | VARCHAR | 60 | 60 | Delivery address line 3 | Newcastle upon Tyne |
| DEL_ADDRESS_4 | VARCHAR | 60 | 60 | Delivery address line 4 | Tyne & Wear |
| DEL_ADDRESS_5 | VARCHAR | 60 | 60 | Delivery address line 5 | NE19 1GH |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | VAT Registration Number |  |
| INVOICE_NUMBER | VARCHAR | 7 | 7 | Corresponding invoice number |       9 |
| INVOICE_NUMBER_NUMERIC | INTEGER | 4 | 10 | Numeric verison of INVOICE_NUMBER (NB Not always the corresponding invoice number) | 9 |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact name | John Bell |
| TAKEN_BY | VARCHAR | 60 | 60 | Order taken by |  |
| CUST_ORDER_NUMBER | VARCHAR | 60 | 60 | Customer's order number |  |
| CUST_TEL_NUMBER | VARCHAR | 30 | 30 | Customer's telephone number | 0191 676 5656 |
| NOTES_1 | VARCHAR | 60 | 60 | Notes 1 | Please notify our head office |
| NOTES_2 | VARCHAR | 60 | 60 | Notes 2 |  |
| NOTES_3 | VARCHAR | 60 | 60 | Notes 3 |  |
| CUST_DISC_RATE | DOUBLE | 8 | 15 | Customer Discount | 0 |
| FOREIGN_ITEMS_NET | DOUBLE | 8 | 15 | Net amount (goods but not carriage) | 9583.2 |
| FOREIGN_ITEMS_TAX | DOUBLE | 8 | 15 | Tax amount (goods but not carriage) | 1635.13 |
| FOREIGN_ITEMS_GROSS | DOUBLE | 8 | 15 | Gross amount (goods but not carriage) | 11218.33 |
| ITEMS_NET | DOUBLE | 8 | 15 | Net amount (goods but not carriage) | 9583.2 |
| ITEMS_TAX | DOUBLE | 8 | 15 | Tax amount (goods but not carriage) | 1635.13 |
| ITEMS_GROSS | DOUBLE | 8 | 15 | Gross amount (goods but not carriage) | 11218.33 |
| TAX_RATE_1 | DOUBLE | 8 | 15 | Highest tax rate | 20 |
| TAX_RATE_2 | DOUBLE | 8 | 15 | Second highest tax rate | 0 |
| TAX_RATE_3 | DOUBLE | 8 | 15 | Third highest tax rate | 0 |
| TAX_RATE_4 | DOUBLE | 8 | 15 | Fourth highest tax rate | 0 |
| TAX_RATE_5 | DOUBLE | 8 | 15 | Fifth highest tax rate | 0 |
| NET_AMOUNT_1 | DOUBLE | 8 | 15 | Net amount at highest tax rate | 9583.2 |
| NET_AMOUNT_2 | DOUBLE | 8 | 15 | Net amount at second highest tax rate | 0 |
| NET_AMOUNT_3 | DOUBLE | 8 | 15 | Net amount at third highest tax rate | 0 |
| NET_AMOUNT_4 | DOUBLE | 8 | 15 | Net amount at fourth highest tax rate | 0 |
| NET_AMOUNT_5 | DOUBLE | 8 | 15 | Net amount at fifth highest tax rate | 0 |
| TAX_AMOUNT_1 | DOUBLE | 8 | 15 | Tax amount at highest tax rate | 1635.13 |
| TAX_AMOUNT_2 | DOUBLE | 8 | 15 | Tax amount at second highest tax rate | 0 |
| TAX_AMOUNT_3 | DOUBLE | 8 | 15 | Tax amount at third highest tax rate | 0 |
| TAX_AMOUNT_4 | DOUBLE | 8 | 15 | Tax amount at fourth highest tax rate | 0 |
| TAX_AMOUNT_5 | DOUBLE | 8 | 15 | Tax amount at fifth highest tax rate | 0 |
| GLOBAL_NOM_CODE | VARCHAR | 8 | 8 | Global nominal code |  |
| GLOBAL_DETAILS | VARCHAR | 60 | 60 | Global details |  |
| GLOBAL_TAX_CODE | VARCHAR | 3 | 3 | Global tax code (T0 to T99) | T1 |
| GLOBAL_DEPT_NUMBER | SMALLINT | 2 | 5 | Global department number | 1 |
| GLOBAL_DEPT_NAME | VARCHAR | 60 | 60 | Global department name | Sales |
| COURIER_NUMBER | SMALLINT | 2 | 5 | Courier Number | 1 |
| COURIER_NAME | VARCHAR | 60 | 60 | Courier Name | UKMail |
| CONSIGNMENT | VARCHAR | 30 | 30 | Consignment Reference |  |
| CARR_NOM_CODE | VARCHAR | 8 | 8 | Carriage nominal code |  |
| CARR_TAX_CODE | VARCHAR | 3 | 3 | Carriage tax code (T0 to T99) | T1 |
| CARR_DEPT_NUMBER | SMALLINT | 2 | 5 | Carriage department number | 1 |
| CARR_DEPT_NAME | VARCHAR | 60 | 60 | Carriage department name | Sales |
| FOREIGN_CARR_NET | DOUBLE | 8 | 15 | Carriage net amount | 0 |
| FOREIGN_CARR_TAX | DOUBLE | 8 | 15 | Carriage tax amount | 0 |
| FOREIGN_CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) | 0 |
| CARR_NET | DOUBLE | 8 | 15 | Carriage net amount | 0 |
| CARR_TAX | DOUBLE | 8 | 15 | Carriage tax amount | 0 |
| CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) | 0 |
| FOREIGN_INVOICE_NET | DOUBLE | 8 | 15 | Invoice net amount (goods and carriage net) | 9583.2 |
| FOREIGN_INVOICE_TAX | DOUBLE | 8 | 15 | Invoice tax amount (goods and carriage tax) | 1635.13 |
| FOREIGN_INVOICE_GROSS | DOUBLE | 8 | 15 | Invoice gross amount (goods and carriage gross) | 11218.33 |
| INVOICE_NET | DOUBLE | 8 | 15 | Invoice net amount (goods and carriage net) | 9583.2 |
| INVOICE_TAX | DOUBLE | 8 | 15 | Invoice tax amount (goods and carriage tax) | 1635.13 |
| INVOICE_GROSS | DOUBLE | 8 | 15 | Invoice gross amount (goods and carriage gross) | 11218.33 |
| CURRENCY | TINYINT | 1 | 3 | Which foreign currency | 1 |
| CURRENCY_TYPE | TINYINT | 1 | 3 | Foreign or Euro currency | 0 |
| EURO_GROSS | DOUBLE | 8 | 15 | Gross amount in Euros | 0 |
| EURO_RATE | DOUBLE | 8 | 15 | Euro exchange rate | 0 |
| FOREIGN_RATE | DOUBLE | 8 | 15 | Foreign exchange rate | 1 |
| SETTLEMENT_DUE_DAYS | SMALLINT | 2 | 5 | Settlement days | 30 |
| SETTLEMENT_DISC_RATE | DOUBLE | 8 | 15 | Settlement discount % rate | 2.5 |
| FOREIGN_SETTLEMENT_DISC_AMOUNT | DOUBLE | 8 | 15 | Settlement discount amount (reduction) | 239.58 |
| FOREIGN_SETTLEMENT_TOTAL | DOUBLE | 8 | 15 | Invoice total after settlement discount | 10937.87 |
| FOREIGN_AMOUNT_PREPAID | DOUBLE | 8 | 15 | Amount prepaid | 0 |
| SETTLEMENT_DISC_AMOUNT | DOUBLE | 8 | 15 | Settlement discount amount (reduction) | 239.58 |
| SETTLEMENT_TOTAL | DOUBLE | 8 | 15 | Invoice total after settlement discount | 10937.87 |
| AMOUNT_PREPAID | DOUBLE | 8 | 15 | Amount prepaid | 0 |
| PAYMENT_REF | VARCHAR | 30 | 30 | Payment reference |  |
| PRINTED | VARCHAR | 1 | 1 | Printed flag - y or blank |  |
| PRINTED_CODE | TINYINT | 1 | 3 | Printed flag - 1/0 | 0 |
| QUOTE_EXPIRY_DATE | DATE | 2 | 10 | Quote expiry date |  |
| QUOTE_STATUS | VARCHAR | 60 | 60 | Quote status |  |
| QUOTE_STATUS_ID | TINYINT | 1 | 3 | Quote status Id | 0 |
| RECURRING_REF | VARCHAR | 11 | 11 | Recurring entry reference |  |
| DUNS_NUMBER | VARCHAR | 9 | 9 | DUNS Number |  |
| NET_VALUE_DISCOUNT_NET | DOUBLE | 8 | 15 | Net value discount value (foreign currency) | 0 |
| NET_VALUE_DISCOUNT_NET_BASE | DOUBLE | 8 | 15 | Net value discount (base currency) | 0 |
| NET_VALUE_DISCOUNT_RATE | DOUBLE | 8 | 15 | Net value discount percentage | 0 |
| NET_VALUE_DISCOUNT_DESC | VARCHAR | 60 | 60 | Net value discount description |  |
| NET_VALUE_DISCOUNT_COMMENT_1 | VARCHAR | 60 | 60 | Net value discount comment 1 |  |
| NET_VALUE_DISCOUNT_COMMENT_2 | VARCHAR | 60 | 60 | Net value discount comment 2 |  |
| PAYMENT_TYPE | TINYINT | 1 | 3 | Payment Type: 0 - Already received. 3 - SR. 4 - SA. | 4 |
| BANK_REF | VARCHAR | 8 | 8 | Bank account used for payment | 1200 |
| GDN_NUMBER | INTEGER | 4 | 10 | GDN Reference | 0 |
| PROJECT_ID | INTEGER | 4 | 10 | ID of linked Project | 0 |
| ANALYSIS_1 | VARCHAR | 30 | 30 | Analysis 1 |  |
| ANALYSIS_2 | VARCHAR | 30 | 30 | Analysis 2 |  |
| ANALYSIS_3 | VARCHAR | 30 | 30 | Analysis 3 |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
