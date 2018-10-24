---
slug: export-jobs-from-my-mobile-workers
title: Export Jobs from My Mobile Workers
---
The My Mobile Workers platform will allow their users to create jobs that contain a set of items required for completion. For example, if you were fitting a new lightswitch you would require the switch, screwdrivers and wiring.

There are two separate API calls that can be used in this task. If you have _Get Jobs By Statuses in Activity History_ set to true you can find the My Mobile Workers documentation available [here](https://docs.mymobileworkers.com/index.php?title=Get_Jobs_By_Current_Status). Alternatively, if you have the same setting set to false then you can find the My Mobile Workers documentation available [here](https://docs.mymobileworkers.com/index.php?title=Get_Jobs_By_Activity_Status).

This task will export jobs from My Mobile Workers in an XML format based on the settings you configure.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

### Date Modified
_Required_
Used when exporting modified records. The records modified on or after this date will be exported.

### DownloadAll
_Required_
Set to true to export all records and ignore the _Date Modified_ setting.

### Get Jobs By Statuses in Activity History
_Required_
download jobs based on the status changes during the completion of a job on the device. List of Job Statuses is available from the [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses)

### Job Status
_Optional_
Jobs with this status will be exported. List of Job Statuses is available from [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses)