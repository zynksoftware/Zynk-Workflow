---
slug: sage-50-uk-cis-settings-columns
title: Sage 50 UK CIS_SETTINGS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| IS_CONTRACTOR | SMALLINT | 2 | 5 | Is the current company a contractor in the Construction Industry Scheme? | 0 |
| IS_SUBCONTRACTOR | SMALLINT | 2 | 5 | Is the current company a subcontractor in the Construction Industry Scheme? | 0 |
| UNIQUE_TAX_REFERENCE | VARCHAR | 10 | 10 | Unique Tax Reference |  |
| ACCOUNTS_OFFICE_REFERENCE_NUMBER | VARCHAR | 13 | 13 | Accounts office reference number |  |
| IS_INACTIVE | SMALLINT | 2 | 5 | The user has declared in an earlier monthly return that they will be inactive in CIS for 6 months | 0 |
| NEXT_PERIOD_END | DATE | 2 | 10 | The day ending the next period in which we're due to submit a monthly return. |  |
| STANDARD_RATE | DOUBLE | 8 | 15 | The higher rate of tax deductions, used for registered subcontractors whose tax record isn't good enough to qualify for gross pa | 20 |
| HIGHER_RATE | DOUBLE | 8 | 15 | The higher rate of tax deductions, used for unregistered subcontractors | 30 |
| CONTROL_NOMINAL | VARCHAR | 8 | 8 | Default nominal used to handle PC postings |  |
| LABOUR_NOMINAL | VARCHAR | 8 | 8 | Nominal for labour charges |  |
| MATERIALS_NOMINAL | VARCHAR | 8 | 8 | Nominal for material charges |  |
| OTHER_TAXABLE_NOMINAL | VARCHAR | 8 | 8 | Nominal for other taxable transactions |  |
| OTHER_NONTAXABLE_NOMINAL | VARCHAR | 8 | 8 | Nominal for other non-taxable transactions |  |
| TAX_LIABILITY_NOMINAL | VARCHAR | 8 | 8 | Nominal for tax liability charges |  |
| CITB_LEVY_NOMINAL | VARCHAR | 8 | 8 | Nominal for CITB Levy |  |
| IS_ENABLED | SMALLINT | 2 | 5 | Is CIS Info enabled in the current company? | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
