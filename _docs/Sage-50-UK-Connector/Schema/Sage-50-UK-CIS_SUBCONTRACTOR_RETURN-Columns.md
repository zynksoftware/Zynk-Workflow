---
slug: sage-50-uk-cis-subcontractor-return-columns
title: Sage 50 UK CIS_SUBCONTRACTOR_RETURN Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| RETURN_ID | INTEGER | 4 | 10 | The unique ID of the CIS return to which this subcontractor's payment details belong. |  |
| SUPPLIER_REFN | VARCHAR | 8 | 8 | The reference of the supplier to which these CIS return details apply. |  |
| UNIQUE_TAX_REFERENCE | VARCHAR | 10 | 10 | The UTR for the subcontractor under the Construction Industry Scheme |  |
| TRADING_NAME | VARCHAR | 56 | 56 | The trading name of the subcontractor |  |
| FIRST_NAME | VARCHAR | 35 | 35 | The first name or initial of the partner. |  |
| MIDDLE_NAME | VARCHAR | 35 | 35 | The middle name of the partner. |  |
| LAST_NAME | VARCHAR | 35 | 35 | The last name (surname) of the partner. |  |
| COMPANY_REGISTRATION_NUMBER | VARCHAR | 8 | 8 | The registration number of this subcontractor at Companies House. |  |
| NATIONAL_INSURANCE_NUMBER | VARCHAR | 9 | 9 | The partner's national insurance number (NINO) |  |
| VERIFICATION_REFERENCE_NUMBER | VARCHAR | 13 | 13 | The reference number supplied by HMRC when this subcontractor was last verified. |  |
| TOTAL_PAYMENTS_MADE | DOUBLE | 8 | 15 | The total cost of payments made to this subcontractor in a given month. |  |
| COST_OF_MATERIALS | DOUBLE | 8 | 15 | The direct cost of materials used in dealings with this subcontractor in a given month. |  |
| AMOUNT_DEDUCTED | DOUBLE | 8 | 15 | The total amount of tax deducted from payments to the subcontractor during a single month. |  |
| UNMATCHED_RATE | SMALLINT | 2 | 5 | Is the subcontractor being paid at the unmatched rate at the end of the tax month? |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
