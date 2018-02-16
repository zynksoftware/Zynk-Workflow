---
slug: common-quickbooks-online-settings
title: Common Quickbooks Online Settings
---
See below the common settings for Quickbooks Online export tasks:

## Settings

### Export Settings -> Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to  'New', only records created after this date will be exported.  The date will update automatically each time the task runs, to ensure  that only records created since the task last ran will be exported.

### Export Settings -> Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only records created or updated after this date will be exported. The date will update automatically each time the task runs, to ensure that only records modified since the task last ran will be exported.

### Export Settings -> Export Modified, New or All Records
_Required_  
Used to choose which records should be included in the export. The available options are:	  

- All - All records will be exported, regardless of whether or not they have been created or updated since the task last ran.
- New - Only records created since the task last ran will be exported.
- Modified - Only records created or updated since the task last ran will be exported.

### Filter
_Optional_  
Allows a filter to be set to limit the data that is returned. The following operators are supported by Quickbooks Online:	  

- Equals (e.g. `CustomerRef = '123'`)
- Greater than (e.g. `TxnDate > '2016-01-01'`)
- Greater than or equal to(e.g. `TxnDate >= '2016-01-01'`)
- Less than (e.g. `TxnDate < '2016-01-01'`)
- Less than or equal to (e.g. `TxnDate <= '2016-01-01'`)
- In (e.g. `CustomerId IN ('1', '2')`)
- Like (e.g. `GivenName LIKE 'Fred%'`)
- And (e.g. `Active = true AND GivenName LIKE 'Fred%'`)

### Page Size
_Required_  
The number of records to include in each page of results exported from Quickbooks. Increasing this value will speed up the export, but will use more memory. Defaults to 100.