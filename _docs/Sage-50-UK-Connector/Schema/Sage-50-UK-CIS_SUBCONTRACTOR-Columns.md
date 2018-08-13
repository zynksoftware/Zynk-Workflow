---
slug: sage-50-uk-cis-subcontractor-columns
title: Sage 50 UK CIS_SUBCONTRACTOR Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| SUPPLIER_REFN | VARCHAR | 8 | 8 | The reference of the supplier to which these CIS details apply. |  |
| COMPANY_TYPE | VARCHAR | 11 | 11 | The type of company the subcontractor is. |  |
| COMPANY_TYPE_CODE | TINYINT | 1 | 3 | The type of company the subcontractor is. |  |
| UNIQUE_TAX_REFERENCE | VARCHAR | 10 | 10 | The UTR for the company under the Construction Industry Scheme |  |
| TRADING_NAME | VARCHAR | 56 | 56 | The trading name of the subcontractor |  |
| LEGAL_NAME | VARCHAR | 56 | 56 | The name of the subcontractor for legal purposes |  |
| USE_LEGAL_NAME | SMALLINT | 2 | 5 | Should the subcontractor's legal name be used in reports, or should we stick with the trading name? |  |
| FIRST_NAME | VARCHAR | 35 | 35 | The first name or initial of the partner. |  |
| MIDDLE_NAME | VARCHAR | 35 | 35 | The middle name of the partner. |  |
| LAST_NAME | VARCHAR | 35 | 35 | The last name (surname) of the partner. |  |
| PARTNERSHIP_UNIQUE_TAX_REFERENCE | VARCHAR | 10 | 10 | The unique tax reference of the partnership with which we're dealing. |  |
| PARTNERSHIP_NAME | VARCHAR | 56 | 56 | The name of the partnership with whom we're dealing, assuming the subcontractor is a partnership. |  |
| COMPANY_REGISTRATION_NAME | VARCHAR | 8 | 8 | The registration number of this subcontractor at Companies House. |  |
| NATIONAL_INSURANCE_NUMBER | VARCHAR | 9 | 9 | The partner's national insurance number (NINO) |  |
| VERIFICATION_REFERENCE_NUMBER | VARCHAR | 13 | 13 | The reference number supplied by HMRC when this subcontractor was last verified. |  |
| VERIFICATION_STATUS | VARCHAR | 17 | 17 |  |  |
| VERIFICATION_STATUS_CODE | TINYINT | 1 | 3 |  |  |
| LAST_VERIFIED | DATE | 2 | 10 | The date on which the subcontractor's licence was last verified with HMRC |  |
| PAYMENT_FREQUENCY | VARCHAR | 7 | 7 | The frequency with which payments are made to this subcontractor |  |
| PAYMENT_FREQUENCY_CODE | TINYINT | 1 | 3 | The frequency with which payments are made to this subcontractor |  |
| EMAIL_STATEMENTS | SMALLINT | 2 | 5 | Has the user agreed to send monthly statements to this subcontractor by email? |  |
| PAY_THIRD_PARTY | SMALLINT | 2 | 5 | Have we agreed to make payments for this subcontractor to a third party instead e.g. a debt factor? |  |
| THIRD_PARTY | VARCHAR | 8 | 8 | The account reference of a third party to whom we make payments for this subcontractor. |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. |  |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. |  |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. |  |
