---
slug: sage-50-uk-contact-history-contact-type-columns
title: Sage 50 UK CONTACT_HISTORY_CONTACT_TYPE Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique number of this ContactHistory Contact Type | 1 |
| CONTACT_TYPE | TINYINT | 1 | 3 | The system-defined value for the type of contact this record represents | 0 |
| DESCRIPTION | VARCHAR | 30 | 30 | A human-readable description of the type of communication made e.g. 'Telephone, Made' | Telephone, made |
| CONTACT_MAJOR_TYPE | TINYINT | 1 | 3 | The MajorContactType that this Type is associated with i.e telphone/letter/meeting | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 04/08/2017 14:18:53 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
