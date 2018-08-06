---
slug: notifying-orders-in-visualsoft
title: Notifying Orders in Visualsoft
---
This task will notify orders (i.e. flag as downloaded) in Visualsoft. See below for a sample input file.

We recommend using this task in conjunction with the 'NotNotified' option on the [Export Orders](exporting-orders-from-visualsoft) task, to prevent orders that have been successfully processed from being exported again.

## Settings
### Connection
_Required_  
The Visualsoft connection to use. See the [Connecting to Visualsoft](connecting-to-visualsoft) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to save failed order notifications to. The data will be written in the same format as the input file.

### Input File
_Required_  
The XML file containing the orders to notify.

### Success File
_Required_  
The XML file to save successful order notifications to. The data will be written in the same format as the input file.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<WEB_ORDERS xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <WEB_ORDER>
    <ORDER>
      <ORDER_ID>2561</ORDER_ID>
    </ORDER>
  </WEB_ORDER>
</WEB_ORDERS>
```
