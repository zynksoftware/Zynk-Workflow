---
slug: sage-50-uk-project-resource-columns
title: Sage 50 UK PROJECT_RESOURCE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| RESOURCE_ID | INTEGER | 4 | 10 | Unique ID Number | 1 |
| REFERENCE | VARCHAR | 8 | 8 | Project Resource Reference | 001 |
| NAME | VARCHAR | 30 | 30 | Project Resource Name | George |
| UNIT | VARCHAR | 30 | 30 | Project Resource Unit | Hour |
| DEFAULT_COST_CODE_ID | INTEGER | 4 | 10 | Project Resource Default Cost Code Number | 0 |
| RATE | DOUBLE | 8 | 15 | Project Resource Cost Rate | 20 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
