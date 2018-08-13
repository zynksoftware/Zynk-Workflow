---
slug: sage-50-uk-stock-comp-columns
title: Sage 50 UK STOCK_COMP Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ASSEMBLY_CODE | VARCHAR | 30 | 30 | Assembly stock code | PC001 |
| COMPONENT_CODE | VARCHAR | 30 | 30 | Component stock code | CAS003 |
| COMPONENT_CODE_INDENT | VARCHAR | 130 | 130 | Component stock code indented | CAS003 |
| COMPONENT_QTY | DOUBLE | 8 | 15 | Component quantity | 1 |
| COMPONENT_LEVEL | SMALLINT | 2 | 5 | Component build level (0 for finished assembly) | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
