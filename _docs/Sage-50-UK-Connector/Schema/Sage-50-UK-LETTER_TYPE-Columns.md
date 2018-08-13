---
slug: sage-50-uk-letter-type-columns
title: Sage 50 UK LETTER_TYPE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique identifier of this record (an internal number) | 10 |
| LETTER_TYPE | TINYINT | 1 | 3 | Which known type of document is this? | 1 |
| DESCRIPTION | VARCHAR | 30 | 30 | A brief description of this letter type | Reminder |
| USED_FOR_CUSTOMERS | SMALLINT | 2 | 5 | Used for customers? | 1 |
| USED_FOR_SUPPLIERS | SMALLINT | 2 | 5 | Used for suppliers | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
