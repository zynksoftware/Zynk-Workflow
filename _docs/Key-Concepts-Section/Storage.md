---
slug: storage
redirect_from: "/article/727-storage"
title: Storage
---
Zynk uses a number of files within the the Data directory; from caches of data, application variables, to logs and truth records.

## [Log Storage](log-database)
Filename: Log.sdf   
Format: Microsoft SQL Server Compact

The log file is created when Zynk is installed, and can be re-created by Zynk by closing Zynk, moving the Log.sdf from the Data folder and re-opening Zynk.  Any previous workflow or application logs will no longer be available to be viewed within Zynk.

For more detailed information ont the log database and the data available visit the [Log Database](log-database) article.

### Workflow Logs
Zynk uses this file to record the history of each run of every workflow; the tasks that were executed when the workflow ran, and any Info, Debug, Warning and Error logs outputted from the run.  You can view workflow logs from within Zynk by opening the required workflow and choosing the History tab.  From here you choose a specific run of the workflow, and view either all log entries, or choose an individual task to limit the entries.  You can control how long log entries are kept by using the History House Keeping setting in the Properties of each workflow file.

### Application Logs
The Log.sdf also stores any errors that occur in Zynk but not within a run of a workflow e.g. errors creating schedules.  These can be viewed by choosing Tools -> Application Log from the main toolbar.

For more detailed information on the log storage please visit [here](log-database).

## [Truth Storage](truth-database)
Filename: Zynk.sdf  
Format: Microsoft SQL Server Compact

This file is created when Zynk is installed, and can be re-created by Zynk by closing Zynk, moving the Zynk.sdf from from the Data folder and re-opening Zynk.  As this files holds information about what information has been processed it is recommend not to remove.  If you are moving Zynk to a new machine this should be copied over as part of the migration to ensure there are no issues with data duplication.

The Truth storage is used by Zynk to keep a record of data that has been imported and exported, which is used by a number of tasks.  For example, when importing an Order into Sage 50 and the Prevent Duplicates setting is enabled Zynk will look for an existing record with the same Id from the XML file.  If there is an existing entry, the order will be skipped and outputted to the fail file, if there is no entry, the order will be processed, and if it is successfully imported, a new record will be created in the truth. Data in the truth can be maintained by opening the required workflow and clicking the Data tab, from here you can remove individual entries, a selection or the entire data set.

There are helper tasks within the Zynk library if granular control of this data is required:-

 * [Delete Truth Record](delete-truth-record)
 * [Export Truth Records](export-truth-records)
 * [If Truth Record Exists](if-truth-record-exists)
 * [Insert Truth Record](insert-truth-record)
 * [Update Truth Record](update-truth-record)
 * [Upsert Truth Records](upsert-truth-records)

For more detailed information ont the truth database and the data available visit the [Truth Database](truth-database) article.

## Variables
Filename: variables.xml  
Format: XML

Zynk stores global variables in this file, these are variables that can be accessed from any workflow.  You can find more information in our [Variables](variables) and [Using Global Variables](using-global-variables) articles.

## Task Caching
Filename: tasklist.xml  
Format: XML

This file is created the first time Zynk is ran and the installed connectors are read.  The file can be removed and will be re-created the next time Zynk is ran.

Zynk uses this to cache the tasks available for the current install to speed up opening time.  You can manually refresh the task list if you have installed a new connector by choosing Refresh from the context menu of the Task Library or choosing Tools -> Refresh Task Library from the main toolbar.
