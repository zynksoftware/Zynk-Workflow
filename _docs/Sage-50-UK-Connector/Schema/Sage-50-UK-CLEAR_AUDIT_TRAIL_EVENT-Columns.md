---
slug: sage-50-uk-clear-audit-trail-event-columns
title: Sage 50 UK CLEAR_AUDIT_TRAIL_EVENT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| CATE_ID | INTEGER | 4 | 10 | Unique ID Number |  |
| DATE | DATE | 2 | 10 | Event Date |  |
| USER_NAME | VARCHAR | 32 | 32 | User Name |  |
| LOCATION_TYPE | VARCHAR | 1 | 1 | Location Type |  |
| LOCATION | VARCHAR | 259 | 259 | Location (data path) |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
