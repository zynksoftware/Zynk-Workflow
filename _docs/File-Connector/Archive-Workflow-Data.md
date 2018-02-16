---
slug: archive-workflow-data
redirect_from: "/article/232-archive-workflow-data"
title: Archive Workflow Data
---
This task will archive all files in the working directory for the current workflow. Note that it won't archive any files in sub-directories of the working directory. You can  adjust how many archives, or how long archives are kept, using the house keeping settings.

We recommend to use this task at the end of a workflow to backup and remove files per run.

## Settings
### Archive Folder
_Required_  
The folder archives where archives will be stored. Defaults to 'Archive' within the working directory. The directory will be created if it does not already exist.

### House Keeping Settings - Number
_Required_  
Used to set either the number of days to keep archives for, or the total number of archive to store, depending on the Type selected.

### House Keeping Settings - Type
_Required_  
Choose the type of house keeping to perform on the archives. The available options are:	  

 * NotEnabled - House keeping will be disabled. All archives will be kept
 * NumberOfArchives - If the number of archives exceeds the chosen number, the oldest archives will be deleted.
 * NumberOfDays - Any archives older than the chosen number of days will be deleted.

### Zynk Settings
See [Common Task Settings](common-task-settings)