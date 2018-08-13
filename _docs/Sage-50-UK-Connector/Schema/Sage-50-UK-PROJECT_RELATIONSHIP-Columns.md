---
slug: sage-50-uk-project-relationship-columns
title: Sage 50 UK PROJECT_RELATIONSHIP Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ANCESTOR_ID | INTEGER | 4 | 10 | Ancestor Project Number | 1 |
| DESCENDENT_ID | INTEGER | 4 | 10 | Descendent Project Number | 1 |
| GENERATION_GAP | INTEGER | 4 | 10 | Number of generations between ancestor and descendent | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 04/08/2017 14:18:55 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:55 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
