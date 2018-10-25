---
slug: import-job-status-updates-to-my-mobile-workers
title: Import Job Status Updates to My Mobile Workers
---
The My Mobile Workers platform will allow you to import job status updates via the API. For example, if you have created a sales order or invoice in Sage for accounting purposes, once that sales order is despatched or that invoice is posted you can send an status update to the related job in My Mobile Workers.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Setting_the_status_of_a_job).

This task will import job status updates to My Mobile Workers in an XML format.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

### Fail File
_Required_
The file to write failed records to.

### Input File
_Required_
The file containing the records you wish to process.

### Success File
_Required_
The file to write successful records to.

### Update Status
_Required_
The status to update jobs to. List of Job Statuses is available from [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses).

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData>
	<Jobs>
		<Job>
	  		<job_number>YMQQ6Z</job_number>
		</Job>
	</Jobs>
</MyMobileWorkersData>
```
