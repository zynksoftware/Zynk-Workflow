---
slug: updating-order-statuses-in-ekm
title: Updating Order Statuses in EKM
---
This task will update the status of orders in EKM.

## Settings
### Connection
_Required_  
The EKM connection to use. See the [Connecting to EKM](connecting-to-ekm) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any records which fail to import into EKM. Defaults to 'ekm_import_order_status_updates_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the records to import into EKM. Defaults to 'ekm_import_order_status_updates.xml'.

### Success File
_Required_  
The name of the XML file to save any records which successfully imported into EKM. Defaults to 'ekm_import_order_status_updates_success.xml'.

### Email Customers
_Required_  
When set to true this will send an email to the customer informing them of the change to their order.

### Prevent Reprocessing
_Required_  
When set to true this will prevent the task from processing a record with the same `<ExternalId>` value as a previously imported record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <Id>1</Id>
    <ExternalId>1234</ExternalId>
    <OrderNumber>1/311019/48</OrderNumber>
    <Status>PROCESSING</Status>
  </Order>
</Orders>
```