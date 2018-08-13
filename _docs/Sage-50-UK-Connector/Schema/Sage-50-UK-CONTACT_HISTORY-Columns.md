---
slug: sage-50-uk-contact-history-columns
title: Sage 50 UK CONTACT_HISTORY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique identifier of this record (an internal number) | 1 |
| SAL_PUR | VARCHAR | 1 | 1 | C = Customer / S= Supplier | C |
| REFN | VARCHAR | 8 | 8 | Account reference | A1D001 |
| MAJOR_TYPE | INTEGER | 4 | 10 | One of eContactHistoryMajorContactType values i.e Telephone, LetterFaxEmail or Meeting | 2 |
| CONTACT_TYPE | INTEGER | 4 | 10 | Sub contact type.  Options depend on Major contact type | 6 |
| CONTACT_DATE | DATE | 2 | 10 | Date of the contact | 12/08/2015 00:00:00 |
| CONTACT | VARCHAR | 30 | 30 | name of the person from other company | Jim Thomas |
| TELEPHONE | VARCHAR | 30 | 30 | Other companies phone number | 01742 876 234 |
| STYLE | INTEGER | 2 | 10 | type of letter 0 = other  1= statement  2= reminder  3 = warning  4 = legal | 1 |
| LOCATION | INTEGER | 2 | 10 | Meeting Location  0 = our office 1= customer's office 2 = other | 1095565312 |
| USERNAME | VARCHAR | 32 | 32 | logon name of person that made the contact | MANAGER |
| OUTCOME | INTEGER | 4 | 10 | 1 of 15 possible comments for the outcome of the contact | 17 |
| PROMISED_PAYMENT | DOUBLE | 8 | 15 | amount promised to be paid | 0 |
| PROMISED_PAYMENT_DATE | DATE | 2 | 10 | date the promised payment is due |  |
| FOLLOW_UP_DATE | DATE | 2 | 10 | Date for the next contact |  |
| OFFSET | INTEGER | 4 | 10 | where memo is in file | 0 |
| BALANCE | DOUBLE | 8 | 15 | The SalPur balance on the creation of this comms history | 0 |
| START | TIME | 4 | 8 | The Start time of a telephone call | 00:00:00 |
| END | TIME | 4 | 8 | The End time of a telephone call | 00:00:00 |
| DURATION | TIME | 4 | 8 | The duration time of a telephone call | 00:00:00 |
| FOLLOW_UP_EVENT_ID | INTEGER | 4 | 10 | The unique ID of the follow up calendar event | 0 |
| SUBJECT | VARCHAR | 60 | 60 | The subject of this Comms entry. | A4 Stat with Tear Off Remit Adv, Grouped &  O/S Items Only |
| ADDRESS1 | VARCHAR | 60 | 60 | Communication Address Line1 | 67a Station Road |
| ADDRESS2 | VARCHAR | 60 | 60 | Communication Address Line2 |  |
| ADDRESS3 | VARCHAR | 60 | 60 | Communication Address Line3 | Blackpool |
| ADDRESS4 | VARCHAR | 60 | 60 | Communication Address Line4 | Lancashire |
| ADDRESS5 | VARCHAR | 60 | 60 | Communication Address Line5 | BP12 7HT |
| FOLLOW_UP_TIME | TIME | 4 | 8 | Time of the follow up activity | 00:00:00 |
| NOTES1 | VARCHAR | 60 | 60 | Communication Notes Line1 | Notes have been moved to memo tab |
| NOTES2 | VARCHAR | 60 | 60 | Communication Notes Line2 |  |
| NOTES3 | VARCHAR | 60 | 60 | Communication Notes Line3 |  |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:53 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
