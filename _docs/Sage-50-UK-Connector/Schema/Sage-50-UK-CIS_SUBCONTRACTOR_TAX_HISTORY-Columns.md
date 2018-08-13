---
slug: sage-50-uk-cis-subcontractor-tax-history-columns
title: Sage 50 UK CIS_SUBCONTRACTOR_TAX_HISTORY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| SUPPLIER_REFN | VARCHAR | 8 | 8 | The account reference for the supplier/subcontractor |  |
| TAX_TREATMENT | VARCHAR | 13 | 13 | Is the subcontractor being paid gross, taxed at the standard rate, or taxed at the higher rate? |  |
| TAX_TREATMENT_CODE | TINYINT | 1 | 3 | Is the subcontractor being paid gross, taxed at the standard rate, or taxed at the higher rate? |  |
| START_DATE | DATE | 2 | 10 | The date on which this tax treatment comes into effect for the subcontractor |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
