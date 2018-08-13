---
slug: sage-50-uk-calendar-event-label-columns
title: Sage 50 UK CALENDAR_EVENT_LABEL Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique identifier of this calendar event label (an internal number) | 1 |
| NAME | VARCHAR | 30 | 30 | The name of the label, as shown to the user | None |
| COLOR | INTEGER | 4 | 10 | The colour in which we'll display the event in the calendar | 16777215 |
| READ_ONLY | SMALLINT | 2 | 5 | Should we prevent the user editing the name of this label? | 1 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
