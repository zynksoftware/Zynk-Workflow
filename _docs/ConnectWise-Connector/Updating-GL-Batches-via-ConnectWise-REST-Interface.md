---
slug: updating-gl-batches-via-connectwise-rest-interface
title: Creating Accounting Batches via ConnectWise REST Interface
---
This task will create a ConnectWise GL Batch in the Accounting Interface with the GL Entry ID's specified in the task. The GL Batch ID to update is determined by a Workflow [Variable](variables) with name CONNECTWISE.BATCHID. The value of this variable is automatically inserted/updated by Zynk when [Exporting GL Batches from ConnectWise REST Interface](exporting-gl-batches-from-connectwise-rest-interface). If you would like to manually specify the GL Batch ID to update then you would use a [Set Variable](set-variable) task with a Variable Key value of CONNECTWISE.BATCHID. This task is typically used for integrations with accounting systems, as once a transaction's GLEntryRecID has been added to a GL Batch, the transaction will no longer be downloaded by Zynk when [Exporting GL Batches from ConnectWise REST Interface](exporting-gl-batches-from-connectwise-rest-interface), preventing data from being duplicated in the accounting system being integrated.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output any batches the task failed to create to. This can be an absolute or relative file path on the local computer or network. 

### Input File
_Required_  
The file containing the batches to create in ConnectWise. This can be an absolute or relative file path on the local computer or network. The file must contain data in an XML format, a sample of which is shown below. 

The `batchIdentifier` is an optional field, which will default to a timestamp value if not specified.

The `glRedId` values are returned in the output file of the [Export GL Batch](exporting-gl-batches-from-connectwise-rest-interface) task.

### Fail File
_Required_  
The XML file to output batches that were successfully created to. This can be an absolute or relative file path on the local computer or network. 

### Fail File
_Required_
The XML file to output any batches the task failed to create to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample imput file is shown below.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Batches>
  <Batch>
    <batchIdentifier>221106</batchIdentifier>
    <glRecIds>
      <glRecId>320042</glRecId>
      <glRecId>320044</glRecId>
      <glRecId>320045</glRecId>
      <glRecId>320046</glRecId>
      <glRecId>320047</glRecId>
      <glRecId>320048</glRecId>
      <glRecId>320043</glRecId>
      <glRecId>320049</glRecId>
    </glRecIds>
  </Batch>
<Batches>
```
