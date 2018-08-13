---
slug: sage-50-uk-calendar-event-columns
title: Sage 50 UK CALENDAR_EVENT Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique identifier of this calendar event (an internal number) | 1 |
| OCCURRENCE_TYPE | TINYINT | 1 | 3 | How was this event generated, in terms of recurrence? | 0 |
| RECURRENCE_PATTERN_ID | INTEGER | 4 | 10 | The unique identifier of a recurrence pattern associated with this event (a foreign key) | 0 |
| IS_DELETED_OCCURRENCE | SMALLINT | 2 | 5 | Does this event represent an occurrence a recurring event that's been deleted? | 0 |
| ORIGINAL_START_TIME | DOUBLE | 8 | 15 | The start time of the master event for this recurrence exception | 0 |
| ORIGINAL_END_TIME | DOUBLE | 8 | 15 | The end time of the master event for this recurrence exception | 0 |
| IS_ALL_DAY_EVENT | SMALLINT | 2 | 5 | Is this event an all-day event? | 1 |
| HAS_REMINDER | SMALLINT | 2 | 5 | Is the reminder enabled for this event? | 1 |
| REMINDER_MINUTES_BEFORE_START | INTEGER | 4 | 10 | The number of minutes before the start of the event that the user should alerted to it | 15 |
| NEXTREMINDERTIME | DOUBLE | 8 | 15 | The date and time at which the next reminder is to be shown. | 0 |
| CREATION_TIME | DOUBLE | 8 | 15 | The date and time at which this event was first created | 0 |
| LAST_MODIFICATION_TIME | DOUBLE | 8 | 15 | The date and time at which this event was last modified | 0 |
| START_TIME | DOUBLE | 8 | 15 | The date and time at which this event begins | 39702 |
| END_TIME | DOUBLE | 8 | 15 | The date and time at which this event ends | 39702.0069444444 |
| BUSY_STATUS | TINYINT | 1 | 3 | How will the user be occupied for the duration of this event? | 0 |
| IMPORTANCE | TINYINT | 1 | 3 | How important is this event? | 0 |
| LABEL_ID | INTEGER | 4 | 10 | The unique identifier of the label applied to this event | 6 |
| SUBJECT | VARCHAR | 255 | 255 | The subject/title of the event | Promised Payment from ABS001 for £750.00 |
| LOCATION | VARCHAR | 60 | 60 | A string in which the user can enter the location of the event |  |
| USERNAME | VARCHAR | 32 | 32 | The name of the user who created the event |  |
| OFFSET | INTEGER | 4 | 10 | Where memo is in file | 10 |
| ACCOUNT | VARCHAR | 8 | 8 | The unique identifier of the customer or supplier linked to the event | ABS001 |
| ACCOUNTTYPE | INTEGER | 9 | 10 | Denotes if the reference stored in the account field is a customer or supplier | 0 |
| CONTACT | VARCHAR | 12 | 12 | The name of the contact at the customer or supplier linked to the event |  |
| IS_COMPLETED | SMALLINT | 2 | 5 | Is this event flagged as complete? | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
