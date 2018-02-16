---
slug: updating-gl-batches-to-connectwise-accounting-interface
redirect_from: "/article/951-updating-gl-batches-to-connectwise-accounting-interface"
title: Updating GL Batches to ConnectWise Accounting Interface
---


This task will update a ConnectWise GL Batch in the Accounting Interface with the GL Entry ID's specified in the task. The GL Batch ID to update is determined by a Workflow [Variable](variables) with name CONNECTWISE.BATCHID. The value of this variable is automatically inserted/updated by Zynk when [Downloading GL Batches From ConnectWise Accounting Interface](downloading-gl-batches-from-connectwise-accounting-interface). If you would like to manually specify the GL Batch ID to update then you would use a [Set Variable](set-variable) task with a Variable Key value of CONNECTWISE.BATCHID. This task is typically used for integrations with accounting systems, as once a transaction's GLEntryRecID has been added to a GL Batch, the transaction will no longer be downloaded by Zynk when [Downloading GL Batches From ConnectWise Accounting Interface](downloading-gl-batches-from-connectwise-accounting-interface), preventing data from being duplicated in the accounting system being integrated.


## Settings

### Connection
_Required_
The ConnectWise Company to Update the GL Batch on.	  The ConnectWise user's security role must have Edit Level access to the Accounting Interface in order to use this task.	  Click the link if you require more information on how to create/manage this type of connection.

### GL Entry IDs
_Required_
A comma separated list of GLEntryRecIDs to add to the GL Batch.	  GLEntryRecID's are exposed when 	[Downloading GL Batches From ConnectWise Accounting Interface](downloading-gl-batches-from-connectwise-accounting-interface).

### Output File
_Required_
An absolute or relative file path on the local computer or network to save the result of the Update GL Batch. This will be defaulted to the current working directory\connectwise\_accounting\_interface\_post\_batch.xml.

## Examples

Sample Successful Response:

```xml
<?xml version="1.0" encoding="utf-8"?>
    <PsaData>Batch update was successful</PsaData>
```

Sample Unsuccessful Response (this response is received from ConnectWise if the GL Entry IDs are empty, i.e. there was nothing to update the Batch with):

```xml
<?xml version="1.0" encoding="utf-8"?>
    <PsaError>System.Exception: Cannot find GLEntryRecIDList to update
       at App.services.system_io.GLEntry.GLEntry_GeneralLedger.updateBatch()
       at App.services.system_io.GLEntry.GLEntry_GeneralLedger.Page_Load(Object sender, EventArgs e)</PsaError>
```