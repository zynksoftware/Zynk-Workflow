---
slug: export-invoices-from-my-mobile-workers
title: Export Invoices from My Mobile Workers
---
The My Mobile Workers platform will allow their users to create an invoice for a job that has been completed and requires payment. For example, if a trades person finishes fitting a floor on site they will notify the company via the mobile app and they can raise an invoice.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Get_Invoices_Updated_Since).

This task will export invoices from My Mobile Workers in an XML format based on the settings you configure.

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

### Get Detailed Job Information Associated with Invoice
_Required_
Set to true to download detailed job information with each invoice. By default the My Mobile Workers invoice only contains the related job's number and external id.

### Job Status
_Optional_
Invoices with Jobs with this status will be exported. List of Job Statuses is available from the [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses)