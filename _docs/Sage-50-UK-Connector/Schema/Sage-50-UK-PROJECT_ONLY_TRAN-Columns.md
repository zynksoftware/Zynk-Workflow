---
slug: sage-50-uk-project-only-tran-columns
title: Sage 50 UK PROJECT_ONLY_TRAN Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| PROJECT_TRAN_ID | INTEGER | 4 | 10 | Unique ID Number | 1 |
| TYPE | VARCHAR | 2 | 2 | Transaction type | CD |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Account Reference |  |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal Code |  |
| REFERENCE | VARCHAR | 30 | 30 | Transaction Reference | Time |
| EXTRA_REF | VARCHAR | 60 | 60 | Extra Reference |  |
| DETAILS | VARCHAR | 60 | 60 | Transaction Details | Project Management Time |
| RESOURCE_ID | INTEGER | 4 | 10 | Project Resource ID | 3 |
| QUANTITY | DOUBLE | 8 | 15 | Quantity | -2.5 |
| RATE | DOUBLE | 8 | 15 | Rate | 20 |
| TAX_AMOUNT | DOUBLE | 8 | 15 | Tax Amount | 0 |
| TAX_CODE | VARCHAR | 3 | 3 | Tax Code (T0 to T99) | T0 |
| DEPT_NUMBER | INTEGER | 4 | 10 | Department Number | 0 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department Name | Default |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
