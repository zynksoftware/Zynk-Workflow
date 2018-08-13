---
slug: sage-50-uk-project-status-columns
title: Sage 50 UK PROJECT_STATUS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| STATUS_ID | INTEGER | 4 | 10 | Unique ID Number | 1 |
| REFERENCE | VARCHAR | 15 | 15 | Project Status Reference | ACTIVE |
| NAME | VARCHAR | 30 | 30 | Project Status Name | Active |
| IS_DEFAULT | SMALLINT | 2 | 5 | Is Default Project Status | 1 |
| ALLOW_POSTING | SMALLINT | 2 | 5 | Allow transaction postings | 1 |
| ALLOW_DELETE | SMALLINT | 2 | 5 | Allow project deletion | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
