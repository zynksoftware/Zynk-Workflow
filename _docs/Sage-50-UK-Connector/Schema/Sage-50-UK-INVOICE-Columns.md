---
slug: sage-50-uk-invoice-columns
title: Sage 50 UK INVOICE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| INVOICE_NUMBER | INTEGER | 4 | 10 | Invoice number | 1 |
| INVOICE_TYPE_CODE | TINYINT | 1 | 3 | Invoice type code | 0 |
| INVOICE_TYPE | VARCHAR | 60 | 60 | Invoice type description | Product Invoice |
| INVOICE_OR_CREDIT | VARCHAR | 60 | 60 | Invoice/Credit/Quote/Proforma label | Invoice |
| INVOICE_DATE | DATE | 2 | 10 | Invoice Date | 02/01/2016 00:00:00 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account reference | A1D001 |
| NAME | VARCHAR | 60 | 60 | Name | A1 Design Services |
| ADDRESS_1 | VARCHAR | 60 | 60 | Address line 1 | 67a Station Road |
| ADDRESS_2 | VARCHAR | 60 | 60 | Address line 2 |  |
| ADDRESS_3 | VARCHAR | 60 | 60 | Address line 3 | Blackpool |
| ADDRESS_4 | VARCHAR | 60 | 60 | Address line 4 | Lancashire |
| ADDRESS_5 | VARCHAR | 60 | 60 | Address line 5 | BP12 7HT |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Address line 1 | 67a Station Road |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Address line 2 | Blackpool |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Address line 3 | Lancashire |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Address line 4 | BP12 7HT |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Address line 5 |  |
| DEL_NAME | VARCHAR | 60 | 60 | Delivery name | A1 Design Services |
| DEL_ADDRESS_1 | VARCHAR | 60 | 60 | Delivery address line 1 | 67a Station Road |
| DEL_ADDRESS_2 | VARCHAR | 60 | 60 | Delivery address line 2 |  |
| DEL_ADDRESS_3 | VARCHAR | 60 | 60 | Delivery address line 3 | Blackpool |
| DEL_ADDRESS_4 | VARCHAR | 60 | 60 | Delivery address line 4 | Lancashire |
| DEL_ADDRESS_5 | VARCHAR | 60 | 60 | Delivery address line 5 | BP12 7HT |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | VAT Registration Number |  |
| ORDER_NUMBER | VARCHAR | 7 | 7 | Corresponding order number |  |
| ORDER_NUMBER_NUMERIC | INTEGER | 4 | 10 | Numeric verison of ORDER_NUMBER (NB Not always the corresponding order number) | 0 |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact name | Jim Thomas |
| TAKEN_BY | VARCHAR | 60 | 60 | Order taken by | George |
| CUST_ORDER_NUMBER | VARCHAR | 60 | 60 | Customer's order number | 7667 |
| CUST_TEL_NUMBER | VARCHAR | 30 | 30 | Customer's telephone number | 01742 876 234 |
| NOTES_1 | VARCHAR | 60 | 60 | Notes 1 | Please notify our head office |
| NOTES_2 | VARCHAR | 60 | 60 | Notes 2 | as soon as possible with any |
| NOTES_3 | VARCHAR | 60 | 60 | Notes 3 | delivery descrepencies. |
| CUST_DISC_RATE | DOUBLE | 8 | 15 | Customer Discount | 0 |
| FOREIGN_ITEMS_NET | DOUBLE | 8 | 15 | Net amount (goods but not carriage) | 1123.04 |
| FOREIGN_ITEMS_TAX | DOUBLE | 8 | 15 | Tax amount (goods but not carriage) | 191.63 |
| FOREIGN_ITEMS_GROSS | DOUBLE | 8 | 15 | Gross amount (goods but not carriage) | 1314.67 |
| ITEMS_NET | DOUBLE | 8 | 15 | Net amount (goods but not carriage) | 1123.04 |
| ITEMS_TAX | DOUBLE | 8 | 15 | Tax amount (goods but not carriage) | 191.63 |
| ITEMS_GROSS | DOUBLE | 8 | 15 | Gross amount (goods but not carriage) | 1314.67 |
| TAX_RATE_1 | DOUBLE | 8 | 15 | Highest tax rate | 20 |
| TAX_RATE_2 | DOUBLE | 8 | 15 | Second highest tax rate | 0 |
| TAX_RATE_3 | DOUBLE | 8 | 15 | Third highest tax rate | 0 |
| TAX_RATE_4 | DOUBLE | 8 | 15 | Fourth highest tax rate | 0 |
| TAX_RATE_5 | DOUBLE | 8 | 15 | Fifth highest tax rate | 0 |
| NET_AMOUNT_1 | DOUBLE | 8 | 15 | Net amount at highest tax rate | 1123.04 |
| NET_AMOUNT_2 | DOUBLE | 8 | 15 | Net amount at second highest tax rate | 0 |
| NET_AMOUNT_3 | DOUBLE | 8 | 15 | Net amount at third highest tax rate | 0 |
| NET_AMOUNT_4 | DOUBLE | 8 | 15 | Net amount at fourth highest tax rate | 0 |
| NET_AMOUNT_5 | DOUBLE | 8 | 15 | Net amount at fifth highest tax rate | 0 |
| TAX_AMOUNT_1 | DOUBLE | 8 | 15 | Tax amount at highest tax rate | 191.63 |
| TAX_AMOUNT_2 | DOUBLE | 8 | 15 | Tax amount at second highest tax rate | 0 |
| TAX_AMOUNT_3 | DOUBLE | 8 | 15 | Tax amount at third highest tax rate | 0 |
| TAX_AMOUNT_4 | DOUBLE | 8 | 15 | Tax amount at fourth highest tax rate | 0 |
| TAX_AMOUNT_5 | DOUBLE | 8 | 15 | Tax amount at fifth highest tax rate | 0 |
| GLOBAL_NOM_CODE | VARCHAR | 8 | 8 | Global nominal code |  |
| GLOBAL_DETAILS | VARCHAR | 60 | 60 | Global details |  |
| GLOBAL_TAX_CODE | VARCHAR | 3 | 3 | Global tax code (T0 to T99) | T1 |
| GLOBAL_DEPT_NUMBER | SMALLINT | 2 | 5 | Global department number | 0 |
| GLOBAL_DEPT_NAME | VARCHAR | 60 | 60 | Global department name | Default |
| COURIER_NUMBER | SMALLINT | 2 | 5 | Courier Number | 2 |
| COURIER_NAME | VARCHAR | 60 | 60 | Courier Name | DHL |
| CONSIGNMENT | VARCHAR | 30 | 30 | Consignment Reference | 4645487 |
| CARR_NOM_CODE | VARCHAR | 8 | 8 | Carriage nominal code | 4905 |
| CARR_TAX_CODE | VARCHAR | 3 | 3 | Carriage tax code (T0 to T99) | T1 |
| CARR_DEPT_NUMBER | SMALLINT | 2 | 5 | Carriage department number | 1 |
| CARR_DEPT_NAME | VARCHAR | 60 | 60 | Carriage department name | Sales |
| FOREIGN_CARR_NET | DOUBLE | 8 | 15 | Carriage net amount | 100 |
| FOREIGN_CARR_TAX | DOUBLE | 8 | 15 | Carriage tax amount | 17.5 |
| FOREIGN_CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) | 117.5 |
| CARR_NET | DOUBLE | 8 | 15 | Carriage net amount | 100 |
| CARR_TAX | DOUBLE | 8 | 15 | Carriage tax amount | 17.5 |
| CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) | 117.5 |
| FOREIGN_INVOICE_NET | DOUBLE | 8 | 15 | Invoice net amount (goods and carriage net) | 1223.04 |
| FOREIGN_INVOICE_TAX | DOUBLE | 8 | 15 | Invoice tax amount (goods and carriage tax) | 209.13 |
| FOREIGN_INVOICE_GROSS | DOUBLE | 8 | 15 | Invoice gross amount (goods and carriage gross) | 1432.17 |
| INVOICE_NET | DOUBLE | 8 | 15 | Invoice net amount (goods and carriage net) | 1223.04 |
| INVOICE_TAX | DOUBLE | 8 | 15 | Invoice tax amount (goods and carriage tax) | 209.13 |
| INVOICE_GROSS | DOUBLE | 8 | 15 | Invoice gross amount (goods and carriage gross) | 1432.17 |
| CURRENCY | TINYINT | 1 | 3 | Which foreign currency | 1 |
| CURRENCY_TYPE | TINYINT | 1 | 3 | Foreign or Euro currency | 0 |
| EURO_GROSS | DOUBLE | 8 | 15 | Gross amount in Euros | 0 |
| EURO_RATE | DOUBLE | 8 | 15 | Euro exchange rate | 0 |
| FOREIGN_RATE | DOUBLE | 8 | 15 | Foreign exchange rate | 1 |
| SETTLEMENT_DUE_DAYS | SMALLINT | 2 | 5 | Settlement days | 15 |
| SETTLEMENT_DISC_RATE | DOUBLE | 8 | 15 | Settlement discount % rate | 2.5 |
| FOREIGN_SETTLEMENT_DISC_AMOUNT | DOUBLE | 8 | 15 | Settlement discount amount (reduction) | 28.09 |
| FOREIGN_SETTLEMENT_TOTAL | DOUBLE | 8 | 15 | Invoice total after settlement discount | 1396.37 |
| FOREIGN_AMOUNT_PREPAID | DOUBLE | 8 | 15 | Amount prepaid | 0 |
| SETTLEMENT_DISC_AMOUNT | DOUBLE | 8 | 15 | Settlement discount amount (reduction) | 28.09 |
| SETTLEMENT_TOTAL | DOUBLE | 8 | 15 | Invoice total after settlement discount | 1396.37 |
| AMOUNT_PREPAID | DOUBLE | 8 | 15 | Amount prepaid | 0 |
| PAYMENT_REF | VARCHAR | 30 | 30 | Payment reference |  |
| PRINTED | VARCHAR | 1 | 1 | Printed flag - y or blank | Y |
| PRINTED_CODE | TINYINT | 1 | 3 | Printed flag - 1/0 | 1 |
| POSTED | VARCHAR | 1 | 1 | Posted flag - y or blank | Y |
| POSTED_CODE | TINYINT | 1 | 3 | Posted flag - 1/0 | 1 |
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
| PAYMENT_TYPE | TINYINT | 1 | 3 | Payment Type: 0 - Already received. 3 - SR. 4 - SA. | 3 |
| BANK_REF | VARCHAR | 8 | 8 | Bank account used for payment | 1200 |
| GDN_NUMBER | INTEGER | 4 | 10 | GDN Reference | 0 |
| PROJECT_ID | INTEGER | 4 | 10 | ID of linked Project | 0 |
| ANALYSIS_1 | VARCHAR | 30 | 30 | Analysis 1 |  |
| ANALYSIS_2 | VARCHAR | 30 | 30 | Analysis 2 |  |
| ANALYSIS_3 | VARCHAR | 30 | 30 | Analysis 3 |  |
| PAYMENT_DUE_DATE | DATE | 2 | 10 | Invoice Payment Due Date |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
