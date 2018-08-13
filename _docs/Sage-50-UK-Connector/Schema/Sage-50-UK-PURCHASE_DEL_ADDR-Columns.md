---
slug: sage-50-uk-purchase-del-addr-columns
title: Sage 50 UK PURCHASE_DEL_ADDR Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| REFERENCE | VARCHAR | 12 | 12 | Delivery address reference | CON001  0001 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account reference | CON001 |
| ADDRESS_REF | INTEGER | 4 | 10 | Address reference number | 1 |
| DESCRIPTION | VARCHAR | 60 | 60 | Description | Head Office |
| NAME | VARCHAR | 60 | 60 | Name | Concept Stationery Supplies |
| ADDRESS_1 | VARCHAR | 60 | 60 | Address Line 1 | 66 New Street |
| ADDRESS_2 | VARCHAR | 60 | 60 | Address Line 2 | Ridgeway |
| ADDRESS_3 | VARCHAR | 60 | 60 | Address Line 3 | Newcastle Upon Tyne |
| ADDRESS_4 | VARCHAR | 60 | 60 | Address Line 4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Address Line 5 | NE1 4GF |
| TELEPHONE | VARCHAR | 30 | 30 | Telephone Number | 0191 643 4343 |
| FAX | VARCHAR | 30 | 30 | Fax Number | 0191 643 4344 |
| E_MAIL | VARCHAR | 255 | 255 | E-mail Address | markramsey@conceptss.co.uk |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact Name | Mark Ramsey |
| TAX_CODE | SMALLINT | 2 | 5 | Tax code | 1 |
| COUNTRY_CODE | VARCHAR | 2 | 2 | Country Code | GB |
| VAT_REG_NUMBER | VARCHAR | 20 | 20 | Vat Registration number |  |
| TELEPHONE_2 | VARCHAR | 30 | 30 | Other Telephone Number |  |
| ADDRESS_TYPE_NAME | VARCHAR | 60 | 60 | Address Type | Delivery |
| ADDRESS_TYPE | TINYINT | 1 | 3 | Address Type | 0 |
| CONTACT_ROLE | VARCHAR | 30 | 30 | Contact Role |  |
| NOTES | VARCHAR | 200 | 200 | Notes |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 06/02/2013 10:15:02 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
