---
slug: importing-organisations-into-webcrm
title: Importing Organisations Into webCRM
---
This task will import organisations into webCRM in [webCRM Organisation XML](webcrm-organisation-xml) format from a file, and output to a success and fail file in the same format.

## Settings
### webCRM Connection
_Required_  
The connection to webCRM to use. See the [Connecting to webCRM](connecting-to-webcrm) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the file to save records that failed to import into webCRM, each record will include an Errors collection detailing why the import failed.  Defaults to `webcrm_import_organisations_fail.xml`

### Input File
_Required_  
The name of the file containing the records to import into webCRM.  Defaults to `(Output from previous task)`

### Success File
_Required_  
The name of the file to save records that were imported into webCRM, each record will include an Id field with the webCRM internal identifier.  Defaults to `webcrm_import_organisations_success.xml`

### Prevent Reprocessing
_Required_  
If true Zynk will check the Truth database to see if a record with the same ExternalId has been provided before, if so the record will be ignored.  Otherwise the record will be imported.