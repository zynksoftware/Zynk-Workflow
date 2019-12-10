---
slug: retry-settings
title: retry-settings
---

You can configure the retry settings on each Peopelvox import task to optionally retry records until they are successfully imported into Peoplevox. This is useful when faced with intermittent connectivity problems with Peoplevox.

Any records that fail for reasons given in the Errors collection will be written to a file and placed in a directory of your choice. Every time that import task runs the files from that folder will be retried until they are successful. You can also optionally choose to clean the retry folder if a record is still unsuccessful after a certain number of days.

## Retry Settings

### Archive
_Optional_
Optionally archive the files stored in the retry folder.

### Archive Days
_Optional_
If Archive is set to true, then archive the files stored in the retry folder after this many days.

### Errors
_Optional_
Attempt to import sales orders again that have for the errors listed here. Please note, you don't have to give the full error, if you provide an excerpt from the error that is sufficient.

### Folder
_Optional_
The folder to place your the files to retry. 

### Retry
_Optional_
Set the Retry task setting to true to enable the settings you have configured.