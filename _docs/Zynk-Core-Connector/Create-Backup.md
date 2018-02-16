---
slug: create-backup
redirect_from: "/article/370-create-backup"
title: Create Backup
---
This task will create a backup of all your workflows and other data. You may wish to create a workflow which runs this task automatically using a schedule, to take regular backups of your Zynk data.

## Settings
### Output File
_Required_  
The Zip file to save the backup to.

### Prepend Timestamp
_Required_  
Set to True to add a timestamp to the file name. This can be used to prevent older backups being overwritten when this task is run. Defaults to False.

### Timestamp Format
_Optional_  
The format for the timestamp. Only required if the 'Prepend Timestamp' setting is set to True. Defaults to `yyyy-MM-dd HH.mm.ss`.

### Zynk Settings
See [Common Task Settings](common-task-settings)