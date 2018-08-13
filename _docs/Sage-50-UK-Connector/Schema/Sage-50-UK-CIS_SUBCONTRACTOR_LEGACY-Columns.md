---
slug: sage-50-uk-cis-subcontractor-legacy-columns
title: Sage 50 UK CIS_SUBCONTRACTOR_LEGACY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| SUPPLER_REFN | VARCHAR | 8 | 8 | The account reference of the subcontractor to whom this data applies. |  |
| CIS_TYPE | VARCHAR | 35 | 35 | The types of CIS scheme under which the subcontractor was registered before the 2007 reform. |  |
| CIS_TYPE_CODE | TINYINT | 1 | 3 | The types of CIS scheme under which the subcontractor was registered before the 2007 reform. |  |
| CIS_NUMBER | VARCHAR | 13 | 13 | The CIS number of a subcontractor; used prior to the 2007 reform of CIS. |  |
| CARD_TYPE | VARCHAR | 35 | 35 | The type of card or registration certificate held by the subcontractor in the old CIS scheme. |  |
| CARD_TYPE_CODE | TINYINT | 1 | 3 | The type of card or registration certificate held by the subcontractor in the old CIS scheme. |  |
| VALID_FROM | DATE | 2 | 10 |  |  |
| VALID_TO | DATE | 2 | 10 |  |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
