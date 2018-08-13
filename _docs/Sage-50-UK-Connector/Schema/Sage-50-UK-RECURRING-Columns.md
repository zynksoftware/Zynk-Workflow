---
slug: sage-50-uk-recurring-columns
title: Sage 50 UK RECURRING Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique number of this Recurring entry | 1 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | BP |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal code | 7200 |
| BANK_CODE | VARCHAR | 8 | 8 | Bank account reference | 1200 |
| REFERENCE | VARCHAR | 30 | 30 | Transaction reference | DD/STO |
| DETAILS | VARCHAR | 60 | 60 | Details | Electrcity Direct Debit |
| SUSPEND_POSTING | TINYINT | 1 | 3 | Suspend Postings flag | 0 |
| NET_AMOUNT | DOUBLE | 8 | 15 | Net amount | 150 |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax amount | 12 |
| DATE_LAST_POSTING | DATE | 2 | 10 | Last posting date | 01/05/2017 00:00:00 |
| DAY_OF_POSTING | SMALLINT | 2 | 5 | Usual day of month for posting | 1 |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department number | 0 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Default |
| REQUIRED_POSTINGS | SMALLINT | 2 | 5 | The total number of postings that this recurring entry is required to make. | 0 |
| POSTINGS_MADE | SMALLINT | 2 | 5 | The total number of postings already made. | 3 |
| POSTED_NET | DOUBLE | 8 | 15 | The total Net amount already posted | 0 |
| POSTED_TAX | DOUBLE | 8 | 15 | The total Tax amount already posted | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | SMALLINT | 2 | 5 | Flag denoting if the record has been deleted or not. | 6912 |
