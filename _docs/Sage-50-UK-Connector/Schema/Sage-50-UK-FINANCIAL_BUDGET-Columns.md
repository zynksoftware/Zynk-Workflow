---
slug: sage-50-uk-financial-budget-columns
title: Sage 50 UK FINANCIAL_BUDGET Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ACCOUNT_REF | VARCHAR | 8 | 8 | Nominal Account Reference | 0020 |
| ANALYSIS_ID | INTEGER | 4 | 10 | The ID of the analysis entity (department, fund, etc...) | 0 |
| YEAR | SMALLINT | 2 | 5 | The year of this budget entry | 2016 |
| BUDGET | DOUBLE | 8 | 15 | The budget value for the specified period | 0 |
| PERIOD | SMALLINT | 2 | 5 | The period number for this budget | 0 |
| ACTUAL | DOUBLE | 8 | 15 | The actual value for the specified period | 50000 |
| CLEARED_ACTUAL | DOUBLE | 8 | 15 | The total cleared actual value for the specified period | 0 |
| CATEGORY | SMALLINT | 2 | 5 | The ID of the nominal category | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 11/08/2016 11:29:23 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
