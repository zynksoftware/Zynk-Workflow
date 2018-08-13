---
slug: sage-50-uk-calendar-recurrence-pattern-columns
title: Sage 50 UK CALENDAR_RECURRENCE_PATTERN Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| UNIQUE_ID | INTEGER | 4 | 10 | The unique identifier of this calendar event recurrence (an internal number) | 1 |
| START_TIME | DOUBLE | 8 | 15 | The time of day at which the recurring event begins | 0.375 |
| DURATION_IN_MINUTES | INTEGER | 4 | 10 | The duration of a single instance of the recurring event e.g. a meeting that lasts 30 | 30 |
| RECURRENCE_PERIOD | TINYINT | 1 | 3 | The type of period over which the event recurs | 4 |
| DAILY_WEEKDAYS_ONLY | SMALLINT | 2 | 5 | Should the event recur on weekdays only? | 0 |
| DAILY_INTERVAL_IN_DAYS | INTEGER | 4 | 10 | The 'every N days' option for a Daily recurrence period | 0 |
| WEEKLY_INTERVAL_IN_WEEKS | INTEGER | 4 | 10 | The 'every N weeks' option for a Weekly recurrence period | 0 |
| WEEKLY_DAYS_OF_WEEK | INTEGER | 4 | 10 | The days on which the event will recur, when using the Weekly recurrence period | 0 |
| MONTHLY_INTERVAL_IN_MONTHS | INTEGER | 4 | 10 | The 'every N months' setting, when using the Monthly recurrence period | 0 |
| MONTHLY_DAY_OF_MONTH | INTEGER | 4 | 10 | The (numeric) day of the month on which the event recurs, when using the Monthly | 0 |
| MONTHLY_NTH_INTERVAL_IN_MONTHS | INTEGER | 4 | 10 | The 'every N months' setting, when using the MonthlyNth recurrence period | 1 |
| MONTHLY_NTH_DAY_OCCURRENCE | TINYINT | 1 | 3 | The Nth whateverday of every month, when using the MonthlyNth recurrence period | 1 |
| MONTHLY_NTH_DAY_OF_WEEK | SMALLINT | 2 | 5 | The Nth whateverday of every month, when using the MonthlyNth recurrence period | 2 |
| YEARLY_MONTH_OF_YEAR | INTEGER | 4 | 10 | The month in which the event recurs, when using the Yearly recurrence period | 0 |
| YEARLY_DAY_OF_MONTH | INTEGER | 4 | 10 | The Nth day of the month in which the event recurs, when using the Yearly recurrence | 0 |
| YEARLY_NTH_DAY_OCCURRENCE | TINYINT | 1 | 3 | The Nth (e.g. first, last) whateverday of the month, when using the YearlyNth recurrence | 0 |
| YEARLY_NTH_DAY_OF_WEEK | SMALLINT | 2 | 5 | The day (Monday, Tuesday, etc.) on which the event recurs, when using the YearlyNth | 0 |
| YEARLY_NTH_MONTH_OF_YEAR | INTEGER | 4 | 10 | The month in which the event recurs, when using the YearlyNth recurrence period | 0 |
| START_DATE | DATE | 2 | 10 | The date of the first event in this recurrence pattern | 05/08/2078 00:00:00 |
| END_TYPE | TINYINT | 1 | 3 | The way in which this recurrence ends | 2 |
| END_DATE | DATE | 2 | 10 | The date of the final event in this recurrence | 05/08/2078 00:00:00 |
| TOTAL_OCCURRENCES | INTEGER | 4 | 10 | The number of occurrences after which this recurrence will end | 1 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:58 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:54 |
| RECORD_DELETED | SMALLINT | 2 | 5 | Flag denoting if the record has been deleted or not. | -8192 |
