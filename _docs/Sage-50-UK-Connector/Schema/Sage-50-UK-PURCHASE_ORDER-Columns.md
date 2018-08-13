---
slug: sage-50-uk-purchase-order-columns
title: Sage 50 UK PURCHASE_ORDER Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ORDER_NUMBER | INTEGER | 4 | 10 | Order number | 1 |
| ORDER_OR_QUOTE | VARCHAR | 60 | 60 | Order/Quote label | Purchase Order |
| ORDER_DATE | DATE | 2 | 10 | Order Date | 05/01/2016 00:00:00 |
| DELIVERY_DATE | DATE | 2 | 10 | Delivery date |  |
| ORDER_STATUS_CODE | TINYINT | 1 | 3 | Order status code | 0 |
| ORDER_STATUS | VARCHAR | 60 | 60 | Order status description |  |
| DELIVERY_STATUS_CODE | TINYINT | 1 | 3 | Delivery status code | 2 |
| DELIVERY_STATUS | VARCHAR | 60 | 60 | Delivery status description | Complete |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account reference | WIS002 |
| NAME | VARCHAR | 60 | 60 | Name | Wiseman Paper Products |
| ADDRESS_1 | VARCHAR | 60 | 60 | Address line 1 | Wiseman House |
| ADDRESS_2 | VARCHAR | 60 | 60 | Address line 2 | Freddicks Way, Bell Estate |
| ADDRESS_3 | VARCHAR | 60 | 60 | Address line 3 | Newcastle Upon Tyne |
| ADDRESS_4 | VARCHAR | 60 | 60 | Address line 4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Address line 5 | NE1 2ED |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Address line 1 | Wiseman House |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Address line 2 | Freddicks Way, Bell Estate |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Address line 3 | Newcastle Upon Tyne |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Address line 4 | NE1 2ED |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Address line 5 |  |
| DEL_NAME | VARCHAR | 60 | 60 | Delivery name | Wiseman Paper Products |
| DEL_ADDRESS_1 | VARCHAR | 60 | 60 | Delivery address line 1 | Sage House |
| DEL_ADDRESS_2 | VARCHAR | 60 | 60 | Delivery address line 2 | Benton Park Road |
| DEL_ADDRESS_3 | VARCHAR | 60 | 60 | Delivery address line 3 | Newcastle Upon Tyne |
| DEL_ADDRESS_4 | VARCHAR | 60 | 60 | Delivery address line 4 |  |
| DEL_ADDRESS_5 | VARCHAR | 60 | 60 | Delivery address line 5 | NE7 7LZ |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | VAT Registration Number |  |
| REFERENCE | VARCHAR | 7 | 7 | Reference |  |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact name | Kathy Jordan |
| TAKEN_BY | VARCHAR | 60 | 60 | Order taken by |  |
| SUPP_ORDER_NUMBER | VARCHAR | 60 | 60 | Supplier's order number |  |
| SUPP_TEL_NUMBER | VARCHAR | 30 | 30 | Supplier's telephone number | 0191 987 3897 |
| NOTES_1 | VARCHAR | 60 | 60 | Notes 1 |  |
| NOTES_2 | VARCHAR | 60 | 60 | Notes 2 |  |
| NOTES_3 | VARCHAR | 60 | 60 | Notes 3 |  |
| SUPP_DISC_RATE | DOUBLE | 8 | 15 | Supplier Discount | 10 |
| FOREIGN_ITEMS_NET | DOUBLE | 8 | 15 | Net amount (goods but not carriage) | 527.4 |
| FOREIGN_ITEMS_TAX | DOUBLE | 8 | 15 | Tax amount (goods but not carriage) | 89.99 |
| FOREIGN_ITEMS_GROSS | DOUBLE | 8 | 15 | Gross amount (goods but not carriage) | 617.39 |
| ITEMS_NET | DOUBLE | 8 | 15 | Net amount (goods but not carriage) | 527.4 |
| ITEMS_TAX | DOUBLE | 8 | 15 | Tax amount (goods but not carriage) | 89.99 |
| ITEMS_GROSS | DOUBLE | 8 | 15 | Gross amount (goods but not carriage) | 617.39 |
| TAX_RATE_1 | DOUBLE | 8 | 15 | Highest tax rate | 20 |
| TAX_RATE_2 | DOUBLE | 8 | 15 | Second highest tax rate | 0 |
| TAX_RATE_3 | DOUBLE | 8 | 15 | Third highest tax rate | 0 |
| TAX_RATE_4 | DOUBLE | 8 | 15 | Fourth highest tax rate | 0 |
| TAX_RATE_5 | DOUBLE | 8 | 15 | Fifth highest tax rate | 0 |
| NET_AMOUNT_1 | DOUBLE | 8 | 15 | Net amount at highest tax rate | 527.4 |
| NET_AMOUNT_2 | DOUBLE | 8 | 15 | Net amount at second highest tax rate | 0 |
| NET_AMOUNT_3 | DOUBLE | 8 | 15 | Net amount at third highest tax rate | 0 |
| NET_AMOUNT_4 | DOUBLE | 8 | 15 | Net amount at fourth highest tax rate | 0 |
| NET_AMOUNT_5 | DOUBLE | 8 | 15 | Net amount at fifth highest tax rate | 0 |
| TAX_AMOUNT_1 | DOUBLE | 8 | 15 | Tax amount at highest tax rate | 89.99 |
| TAX_AMOUNT_2 | DOUBLE | 8 | 15 | Tax amount at second highest tax rate | 0 |
| TAX_AMOUNT_3 | DOUBLE | 8 | 15 | Tax amount at third highest tax rate | 0 |
| TAX_AMOUNT_4 | DOUBLE | 8 | 15 | Tax amount at fourth highest tax rate | 0 |
| TAX_AMOUNT_5 | DOUBLE | 8 | 15 | Tax amount at fifth highest tax rate | 0 |
| COURIER_NUMBER | SMALLINT | 2 | 5 | Courier Number | 1 |
| COURIER_NAME | VARCHAR | 60 | 60 | Courier Name | UKMail |
| CONSIGNMENT | VARCHAR | 30 | 30 | Consignment Reference |  |
| CARR_NOM_CODE | VARCHAR | 8 | 8 | Carriage nominal code |  |
| CARR_TAX_CODE | VARCHAR | 3 | 3 | Carriage tax code (T0 to T99) | T1 |
| CARR_DEPT_NUMBER | SMALLINT | 2 | 5 | Carriage department number | 2 |
| CARR_DEPT_NAME | VARCHAR | 60 | 60 | Carriage department name | Purchasing |
| FOREIGN_CARR_NET | DOUBLE | 8 | 15 | Carriage net amount | 0 |
| FOREIGN_CARR_TAX | DOUBLE | 8 | 15 | Carriage tax amount | 0 |
| FOREIGN_CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) | 0 |
| CARR_NET | DOUBLE | 8 | 15 | Carriage net amount | 0 |
| CARR_TAX | DOUBLE | 8 | 15 | Carriage tax amount | 0 |
| CARR_GROSS | DOUBLE | 8 | 15 | Carriage gross amount (carriage net + carriage tax) | 0 |
| FOREIGN_INVOICE_NET | DOUBLE | 8 | 15 | Invoice net amount (goods and carriage net) | 527.4 |
| FOREIGN_INVOICE_TAX | DOUBLE | 8 | 15 | Invoice tax amount (goods and carriage tax) | 89.99 |
| FOREIGN_INVOICE_GROSS | DOUBLE | 8 | 15 | Invoice gross amount (goods and carriage gross) | 617.39 |
| INVOICE_NET | DOUBLE | 8 | 15 | Invoice net amount (goods and carriage net) | 527.4 |
| INVOICE_TAX | DOUBLE | 8 | 15 | Invoice tax amount (goods and carriage tax) | 89.99 |
| INVOICE_GROSS | DOUBLE | 8 | 15 | Invoice gross amount (goods and carriage gross) | 617.39 |
| CURRENCY | TINYINT | 1 | 3 | Which foreign currency | 1 |
| CURRENCY_TYPE | TINYINT | 1 | 3 | Foreign or Euro currency | 0 |
| EURO_GROSS | DOUBLE | 8 | 15 | Gross amount in Euros | 0 |
| EURO_RATE | DOUBLE | 8 | 15 | Euro exchange rate | 0 |
| FOREIGN_RATE | DOUBLE | 8 | 15 | Foreign exchange rate | 1 |
| SETTLEMENT_DUE_DAYS | SMALLINT | 2 | 5 | Settlement days | 30 |
| SETTLEMENT_DISC_RATE | DOUBLE | 8 | 15 | Settlement discount % rate | 2.5 |
| FOREIGN_SETTLEMENT_DISC_AMOUNT | DOUBLE | 8 | 15 | Settlement discount amount (reduction) | 13.19 |
| FOREIGN_SETTLEMENT_TOTAL | DOUBLE | 8 | 15 | Invoice total after settlement discount | 601.96 |
| SETTLEMENT_DISC_AMOUNT | DOUBLE | 8 | 15 | Settlement discount amount (reduction) | 13.19 |
| SETTLEMENT_TOTAL | DOUBLE | 8 | 15 | Invoice total after settlement discount | 601.96 |
| PAYMENT_REF | VARCHAR | 30 | 30 | Payment reference |  |
| PRINTED | VARCHAR | 1 | 1 | Printed flag - y or blank |  |
| PRINTED_CODE | TINYINT | 1 | 3 | Printed flag - 1/0 | 0 |
| POSTED | VARCHAR | 1 | 1 | Posted flag - y or blank |  |
| POSTED_CODE | TINYINT | 1 | 3 | Posted flag - 1/0 | 0 |
| QUOTE_STATUS_ID | TINYINT | 1 | 3 | Quote status Id | 0 |
| RECURRING_REF | VARCHAR | 11 | 11 | Recurring entry reference |  |
| DUNS_NUMBER | VARCHAR | 9 | 9 | DUNS Number |  |
| PAYMENT_TYPE | TINYINT | 1 | 3 | Payment Type: 0 - Already received. 3 - SR. 4 - SA. | 0 |
| BANK_REF | VARCHAR | 8 | 8 | Bank account used for payment | 1200 |
| GDN_NUMBER | INTEGER | 4 | 10 | GDN Reference | 0 |
| PROJECT_ID | INTEGER | 4 | 10 | ID of linked Project | 0 |
| ANALYSIS_1 | VARCHAR | 30 | 30 | Analysis 1 |  |
| ANALYSIS_2 | VARCHAR | 30 | 30 | Analysis 2 |  |
| ANALYSIS_3 | VARCHAR | 30 | 30 | Analysis 3 |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
