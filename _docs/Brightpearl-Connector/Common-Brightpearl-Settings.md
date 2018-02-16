---
slug: common-brightpearl-settings
title: Common Brightpearl Settings
---
See below for the common Brightpearl Zynk Workflow settings.

## Settings

### Export Custom Fields
_Required_
Set to true to download the values of any custom fields that have been set up on the contacts.

### Export Details
_Required_
Set to true to export related data for each contact. This will include address, currency, price list and tax code information.

### Export Settings -> Date Created
_Required_
When the 'Export Modified, New or All Records' setting is set to 'New', only records created after this date will be exported. This date will update automatically each time the task runs.

### Export Settings -> Date Modified
_Required_
When the 'Export Modified, New or All Records' setting is set to 'New',  only records created after this date will be exported. This date will  update automatically each time the task runs. |

### Export Settings -> Export Modified, New or All
_Required_
Choose which records should be included in the export. The available options are:	  

- New - Only records created since the date specified in the 'Date Created' setting will be exported.
- Modified - Only records modified since the date specified in the 'Date Modified' setting will be exported.
- All - Records will not be filtered based on date created or modified.

### Filter
_Optional_
Specify criteria to filter the results returned e.g. 	`firstName=John&amp;lastName=Smith`.

### ID Set
_Optional_
Specify the contact ID numbers and/or ranges to export. The ID numbers must be provided in numerical order. For example, the ID set  			`1,3,5-8,10` would download the records with ID 1, 3, 5, 6, 7, 8 and 10. 	Please note that this setting overrides the Filter and Export Settings, and Contact Type settings.