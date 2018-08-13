---
slug: sage-50-uk-category-columns
title: Sage 50 UK CATEGORY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| CHART | INTEGER | 4 | 10 | Chart number | 1 |
| CATEGORY | INTEGER | 4 | 10 | Category number | 1 |
| FLAG_ASSET_LIABILITY | SMALLINT | 2 | 5 | Asset or Liability flag | 0 |
| NAME | VARCHAR | 60 | 60 | Name | Product Sales |
| LOW | VARCHAR | 8 | 8 | Low nominal code | 4000 |
| HIGH | VARCHAR | 8 | 8 | High nominal code | 4099 |
| SORT_ORDER | INTEGER | 4 | 10 | Sort Order | 1 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
