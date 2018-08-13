---
slug: sage-50-uk-bank-columns
title: Sage 50 UK BANK Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account reference | 1200 |
| ACCOUNT_NUMBER | VARCHAR | 60 | 60 | Bank account number | 003234234 |
| ACCOUNT_NAME | VARCHAR | 60 | 60 | Bank account name | Stationery & Computer Mart UK Ltd |
| NAME | VARCHAR | 60 | 60 | Name | Lloyds Bank PLC |
| ADDRESS_1 | VARCHAR | 60 | 60 | Address line 1 | Bank Chambers |
| ADDRESS_2 | VARCHAR | 60 | 60 | Address line 2 | 23a Grey Street |
| ADDRESS_3 | VARCHAR | 60 | 60 | Address line 3 | Necastle Upon Tyne |
| ADDRESS_4 | VARCHAR | 60 | 60 | Address line 4 |  |
| ADDRESS_5 | VARCHAR | 60 | 60 | Address line 5 | NE1 3ER |
| C_ADDRESS_1 | VARCHAR | 60 | 60 | Compact Address line 1 | Bank Chambers |
| C_ADDRESS_2 | VARCHAR | 60 | 60 | Compact Address line 2 | 23a Grey Street |
| C_ADDRESS_3 | VARCHAR | 60 | 60 | Compact Address line 3 | Necastle Upon Tyne |
| C_ADDRESS_4 | VARCHAR | 60 | 60 | Compact Address line 4 | NE1 3ER |
| C_ADDRESS_5 | VARCHAR | 60 | 60 | Compact Address line 5 |  |
| TELEPHONE | VARCHAR | 30 | 30 | Telephone Number |  |
| CONTACT_NAME | VARCHAR | 30 | 30 | Contact Name |  |
| FAX | VARCHAR | 30 | 30 | Fax Number |  |
| E_MAIL | VARCHAR | 255 | 255 | E-Mail Address |  |
| WEB_ADDRESS | VARCHAR | 255 | 255 | World Wide Web Address |  |
| CURRENCY | TINYINT | 1 | 3 | Currency code | 1 |
| SORT_CODE | VARCHAR | 10 | 10 | Bank sort code | 23-34-34 |
| OVERDRAFT_LIMIT | DOUBLE | 8 | 15 | Overdraft limit | -120000 |
| NUMBER | SMALLINT | 2 | 5 | Bank Number | 12800 |
| FOREIGN_BALANCE | DOUBLE | 8 | 15 | Balance (in Account Currency) | -20091.04 |
| TYPE | VARCHAR | 60 | 60 | Bank Account Type | Cheque Account |
| IBAN | VARCHAR | 60 | 60 | The account's international bank account number |  |
| BICSWIFT | VARCHAR | 60 | 60 | BIC/SWIFT Code |  |
| LAST_REC_DATE | DATE | 2 | 10 | Last reconciled date |  |
| LAST_REC_BALANCE | DOUBLE | 8 | 15 | Last reconciled balance | 0 |
| ROLL_NUMBER | VARCHAR | 60 | 60 | Roll Number |  |
| ADDITIONAL_REF1 | VARCHAR | 60 | 60 | Additional Ref 1 |  |
| ADDITIONAL_REF2 | VARCHAR | 60 | 60 | Additional Ref 2 |  |
| ADDITIONAL_REF3 | VARCHAR | 60 | 60 | Additional Ref 3 |  |
| INACTIVE_FLAG | INTEGER | 4 | 10 | Inactive Flag - Yes/No | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:51 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
