---
slug: sage-50-uk-deleted-records-columns
title: Sage 50 UK DELETED_RECORDS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| TABLE_ID | INTEGER | 4 | 10 | The unique reference of the table where the deletion was performed |  |
| FOREIGN_REF |  | 255 | 0 | Primary key from the foreign table |  |
| DELETION_DATE_TIME |  | 16 | 0 | The date and time on which the deletion took place |  |
| FOREIGN_REF_TYPE | SMALLINT | 2 | 5 | Denotes the type of data held in the Foreign Ref field |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
