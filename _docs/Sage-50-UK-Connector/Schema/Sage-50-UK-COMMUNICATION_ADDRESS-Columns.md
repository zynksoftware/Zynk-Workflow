---
slug: sage-50-uk-communication-address-columns
title: Sage 50 UK COMMUNICATION_ADDRESS Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ACCOUNT_TYPE | TINYINT | 1 | 3 | Is this record for a customer or supplier? | 0 |
| ACCOUNT_REF | VARCHAR | 8 | 8 | The unique identifier of the customer or supplier whose communication address is being defined | A1D001 |
| LETTER_TYPE_ID | INTEGER | 4 | 10 | The unique identifier of the letter type record whose recipient address is being defined (an internal number) | 1 |
| ADDRESS_REF | INTEGER | 4 | 10 | The number of the customer/supplier's address record to which the letter type is sent | 5 |
| ADDRESS_ID | VARCHAR | 12 | 12 | The unique identifier of the specific customer or supplier address | A1D001  0005 |
| PREFERRED_EMAIL | SMALLINT | 2 | 5 | The index of the number of the email from the registered address to use | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 04/08/2017 14:18:54 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
