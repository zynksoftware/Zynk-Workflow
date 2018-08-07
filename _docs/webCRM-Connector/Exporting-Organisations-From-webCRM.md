---
slug: exporting-organisations-from-webcrm
title: Exporting Organisations From webCRM
---
This task will export organisations from webCRM, including the related main person, in [webCRM Organisation XML](webcrm-organisation-xml) format to a file.

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

### Main Person Settings > Export Main Person
_Required_  
Set to true to include the details of the main person of the organisation in the output XML.

### Main Person Settings > Filter Field
_Required_  
The field from the Person table to use when searching for the main person, defaults to `CheckMark7`.

### Main Person Settings > Export Main Person
_Required_  
The value in the Person table to use when searching for the main person, defaults to `true`.

### Page Size
_Required_
Used to control the number of records that will be downloaded in each page from webCRM, defaults to `25`.

### Output File
_Required_  
The name of the file to save the downloaded records to.
