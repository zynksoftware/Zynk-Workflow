---
slug: log-database
title: Log Database
---
This article will outline detailed information regarding the log database that Zynk uses. Typically, this is stored in the default data directory (C:\ProgramData\Zynk Software\Zynk\2.0\Data), although if you have specified a bespoke data directory in Tools -> Options the database file will be located in that directory.

You can configure the archive of historical data in this database via your workflow. By default, this is set to retain the previous 90 days of workflow and application history.

Please note, if you lower this to save disk space and our support team cannot locate error logs it's highly unlikely we will be able to support you.

You can interrogate your database using the free-to-use Zynk extension [Zynk Log Manager (ZLM)](zynk-log-manager-zlm).

## Tables
### Log
The log table will store both application and workflow level log messages. 

###### Columns
Please see below a list of available columns on the log table: -
* __WorkflowId__ This field is the GUID related to the workflow that caused the error. This field is blank when the log message does not originate from a workflow.
* __TaskId__ This field is the GUId related to the task that caused the error. This field is blank when the log message does not originate from a task.
* __LogType__ This field indicates the type log that has been registered. For example, error messages have the LogType 'Error' or debug message have the LogType 'Debug'.
* __Date__ This field will give the date and time that the log message was registered.
* __JobNumber__ This field will give you the job that the log message is related to. This field is blank when the log message does not originate from a job.
* __Id__ This field is populated with a uniquely generated identifier.
* __Message__ This field will tell you the message that was logged by Zynk Workflow.

###### Relationships
Please see below a list of relationships between the log table and the other tables in the log database: -
* __Log.WorkflowId -> Job.WorkflowId__
* __Log.JobNumber -> Job.Id__
* __Log.JobNumber -> JobItem.JobNumber__
* __Log.TaskId -> JobItem.TaskId__

### Job
The job table will store workflow level errors as the each message will relate to a single run of the workflow and the log messages associated with it.

The job table is linked to the job item table which stores each individual task result and the log messages associated with it. 

These two tables are linked by the Id column from the job table and the JobNumber column from the job item table.

###### Columns
Please see below a list of available columns on the job table: -
* __WorkflowId__ This field is the unique identifier that is used to match a job to a workflow.
* __StartDate__ This field indicates the date and time that a workflow run began.
* __EndDate__ This field indicates the date and time that a workflow run ended.
* __Result__ This field will give you the final outcome of a workflow event. For example, a successfully completed workflow would return the result 'Success'.
* __Id__ This field is the unique identifier that is used to match a job item table entry to a job table entry.
* __RunType__ This field will indicate the way in which the workflow was run. For example, a scheduled workflow will be have the RunType set to '2'.
* __ArchivePath__ This field will detail where the archive for the workflow run is stored - if an Archive Workflow Data task was completed within that workflow.

###### Relationships
Please see below a list of relationships between the job table and the other tables in the log database: -
* __Job.WorkflowId -> Log.WorkflowId__
* __Job.Id -> Log.JobNumber__
* __Job.Id -> JobItem.JobNumber__

### Job Item
The job item table will store task level log messages.

The job item table is linked to the job table which stores each workflow result.

These two tables are linked by the Id column from the job table and the JobNumber column from the job item table.

###### Columns
Please see below a list of available columns on the job item table: -
* __JobNumber__ This field is the unique identifier of the job table entry that the job item table entry is related to.
* __TaskName__ This field will indicate the full name of the task associated with this job item.
* __StartDate__ This field indicates the date and time that a task run began.
* __EndDate__ This field indicates the date and time that a task run ended.
* __Result__ The result field will give you the final outcome of the task. For example, a task that has errored and cannot continue will be marked as 'Fail' or a task that completes successfully will be marked as 'Success'.
* __InCount__ The InCount will give you an exact total of the amount of records passed into the task. For example, if you have a file containing 10 sales orders you are importing into Sage 50, the InCount for your Import Sales Orders task will be 10.
* __OutCount__ The OutCount will give you an exact total of the amount of records passed out of the task. For example, if you run an Export Stock Records task and 10 products are exported, the OutCount will be set to 10. The OutCount can also indicate how many records have been imported successfully.
* __ErrorCount__ The ErrorCount will indicate how many records have failed to be processed. For example, if you try to import 5 sales orders into Sage and 1 fails. Your Import Sales Orders task will have an InCount of 5, an OutCount of 4 and an ErrorCount of 1.

###### Relationships
Please see below a list of relationships between the job item table and the other tables in the log database: -
* __JobItem.TaskId -> Log.TaskId__
* __JobItem.JobNumber -> Log.JobNumber__
* __JobItem.JobNumber -> Job.Id__
