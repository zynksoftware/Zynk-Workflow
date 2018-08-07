---
slug: exporting-persons-from-webcrm
title: Exporting Persons From webCRM
---
This task will export persons from webCRM in [webCRM Person XML](webcrm-person-xml) format to a file.

## Settings
### webCRM Connection
_Required_  
The connection to webCRM to use. See the [Connecting to webCRM](connecting-to-webcrm) article if you require more information on how to create/manage connections.

### Export Settings > Export Date
_Required_  
When the 'Export Type' setting is set to 'Modified' or 'New', only records modified or created after this date will be downloaded. The date will update automatically each time the task runs.

### Export Settings > Export Type
_Required_  
Used to choose which records should be included in the download. The available options are:

* __All__ - All records will be downloaded, regardless of whether or not they have been updated since the task last ran.
* __Modified__ - Only records created or updated since the task last ran will be downloaded.
* __New__ - Only records created since the task last ran will be downloaded.

### Export Settings > Where Clauses
_Optional_
Allows filters to be added to the export to limit the data returned.  The Field Name needs to exist from the source table in webCRM e.g. Status on the Delivery table, this can be specified with or without the table name prepended.

### Include Field Metadata
_Required_
Set to true to include names of custom fields in the output XML.

### Page Size
_Required_
Used to control the number of records that will be downloaded in each page from webCRM, defaults to `25`.

### Output File
_Required_  
The name of the file to save the downloaded records to.