---
slug: sage-50-uk-esubmission-settings-columns
title: Sage 50 UK ESUBMISSION_SETTINGS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| USER_ID | VARCHAR | 23 | 23 | The user ID used to logon to the government's online submission service. |  |
| EMPLOYER_REFERENCE | VARCHAR | 15 | 15 | A company's tax office details, forming an employer's reference. |    / |
| IS_AGENT | TINYINT | 1 | 3 | The contractor is submitting as an agent | 0 |
| SUB_FAMILY | TINYINT | 1 | 3 | The type (or family) of the submission.  i.e. CIS or VAT | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
