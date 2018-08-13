---
slug: sage-50-uk-cis-return-columns
title: Sage 50 UK CIS_RETURN Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| RETURN_ID | INTEGER | 4 | 10 | The unique number of this CIS return (an internal number) |  |
| CONTRACTOR_UTR | VARCHAR | 10 | 10 | The unique tax reference of the user's company as a contractor in the Construction Industry Scheme. |  |
| ACCOUNTS_OFFICE_REFERENCE_NUMBER | VARCHAR | 13 | 13 | The reference number of the user's company at the Accounts Office |  |
| MONTH_ENDING | DATE | 2 | 10 | The date ending the month to which this CIS return applies. |  |
| EMPLOYMENT_STATUS_DECLARATION | TINYINT | 1 | 3 | Can you confirm that the employment status of each individual included on this return has been considered and payments have not |  |
| SUBCONTRACTOR_VERIFICATION_DECLARATION | TINYINT | 1 | 3 | Can you confirm that every subcontractor included on this return has either been verified with HM Revenue & Customs, or has been |  |
| INACTIVITY_INDICATOR | SMALLINT | 2 | 5 | Please indicate if you do not anticipate paying subcontractors in the next six months. |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
