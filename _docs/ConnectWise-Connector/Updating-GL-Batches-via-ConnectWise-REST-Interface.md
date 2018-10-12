---
slug: updating-gl-batches-via-connectwise-rest-interface
title: Updating GL Batches via ConnectWise REST Interface
---
This task will update a ConnectWise GL Batch in the Accounting Interface with the GL Entry ID's specified in the task. The GL Batch ID to update is determined by a Workflow [Variable](variables) with name CONNECTWISE.BATCHID. The value of this variable is automatically inserted/updated by Zynk when [Exporting GL Batches from ConnectWise REST Interface](exporting-gl-batches-from-connectwise-rest-interface). If you would like to manually specify the GL Batch ID to update then you would use a [Set Variable](set-variable) task with a Variable Key value of CONNECTWISE.BATCHID. This task is typically used for integrations with accounting systems, as once a transaction's GLEntryRecID has been added to a GL Batch, the transaction will no longer be downloaded by Zynk when [Exporting GL Batches from ConnectWise REST Interface](exporting-gl-batches-from-connectwise-rest-interface), preventing data from being duplicated in the accounting system being integrated.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### GL Entry IDs
_Required_
A comma separated list of `glEntryIds` to add to the GL Batch. The `glEntryIds` are returned in the output file of the [Export GL Batch](exporting-gl-batches-from-connectwise-rest-interface) task.

### Output File
_Required_
An absolute or relative file path on the local computer or network to save the result of the Update GL Batch. This will be defaulted to the current working directory\connectwise\_accounting\_interface\_update\_batch.xml.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
There are currently no examples for this task.
