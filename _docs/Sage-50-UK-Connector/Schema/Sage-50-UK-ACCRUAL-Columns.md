---
slug: sage-50-uk-accrual-columns
title: Sage 50 UK ACCRUAL Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| NAME | VARCHAR | 60 | 60 | Name | Telephone Accrual |
| NOMINAL_CODE_1 | VARCHAR | 8 | 8 | Expense account nominal code | 7502 |
| NOMINAL_CODE_2 | VARCHAR | 8 | 8 | Control account nominal code | 2109 |
| AMOUNT | DOUBLE | 8 | 15 | Value | 200 |
| MONTHS_TO_POST | SMALLINT | 2 | 5 | Months to post | 4 |
| MONTHS_POSTED | SMALLINT | 2 | 5 | Months posted | 4 |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department number | 0 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Default |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
