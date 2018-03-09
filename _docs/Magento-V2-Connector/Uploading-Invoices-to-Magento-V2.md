---
slug: uploading-invoices-to-magento-v2
redirect_from: "/article/uploading-invoices-to-magento-v2"
title: Uploading Invoices to Magento V2
---
This task will create new invoices in Magento. See below for a sample input file.

## Settings
### Connection
_Required_  
The Magento V2 connection to use. See the [Connecting to Magento V2](connecting-to-magento-v2) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to save failed invoice uploads to. The data will be written in the same format as the input file.

### Input File
_Required_  
The XML file containing the invoices to upload in Magento.

### Success File
_Required_  
The XML file to save successful invoice uploads to. The data will be written in the same format as the input file.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

## Store View Code
_Required_  
The magento store view code to perform the API calls against. Default value of 'all'.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. If no items collection is provided, all outstanding items will be invoiced.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoice>
    <external_id>98353</external_id>
    <order>
      <increment_id>000000004</increment_id>
      <external_id>185754</external_id>
      <entity_id>4</entity_id>
    </order>
    <capture>false</capture>
    <items>
      <item>
        <sku>WSH12-32-Purple</sku>
        <qty>1</qty>
      </item>
    </items>
    <notify>false</notify>
    <appendComment>false</appendComment>
    <comment>
      <comment>Invoiced by Zynk</comment>
      <is_visible_on_front>1</is_visible_on_front>
    </comment>
  </Invoice>
</ArrayOfInvoice>
```
