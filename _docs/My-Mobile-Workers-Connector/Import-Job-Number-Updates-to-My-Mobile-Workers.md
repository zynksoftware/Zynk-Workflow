---
slug: import-job-number-updates-to-my-mobile-workers
title: Import Job Number Updates to My Mobile Workers
---
The My Mobile Workers platform will allow you to import job numbers via the API. For example, if you create your jobs in Sage for accounting purposes you can send the Sage sales order or invoice number back to My Mobile Workers so you have an element of traceability between the two systems.

Please note, you will need to create the following custom Job statuses in My Mobile Workers in order to successfully use this task. You can create these in Settings -> Job Options -> Custom Statuses

If you are still unsure on how to complete this, your My Mobile Workers account manager will be able to provide help.

* __JOB_INVOICE_CREATED__
* __JOB_INVOICE_SENT__

There are two separate API calls that can be used in this task. If you have _Status Specific_ set to true you can find the My Mobile Workers documentation available [here](https://docs.mymobileworkers.com/index.php?title=Update_PO_Number_%26_Invoice_Number_-_status_specific). Alternatively, if you have the same setting set to false then you can find the My Mobile Workers documentation available [here](https://docs.mymobileworkers.com/index.php?title=Update_PO_Number_%26_Invoice_Number).

This task will import job numbers to My Mobile Workers in an XML format.

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

### Status Specific
_Required_
Use either the invoice_update or status (status specific) call.

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Jobs>
    <Job>
	  <job_number>YMQQ6Z</job_number>
	  <invoice_number>1234</invoice_number>
	</Job>
  </Jobs>
</MyMobileWorkersData>
```
