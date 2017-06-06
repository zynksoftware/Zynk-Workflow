---
slug: uploading-invoices-to-magento
redirect_from: "/article/714-uploading-invoices-to-magento"
title: Uploading Invoices to Magento
---
This task will create new invoices in Magento. The input file should be in Magento XML format. You can optionally provide a list of specific items and quantities to invoice, or just provide the order number and the task will automatically invoice all items.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed invoice uploads to.

### Input File
_Required_  
The XML file containing the products to upload to Magento. Note that you only need to provide values for fields you want to update.

### Success File
_Required_  
The XML file to output successful invoice uploads to. 

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0"?>
<ArrayOfInvoiceInfo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <InvoiceInfo>
    <order_increment_id>100000005</order_increment_id>
    <items> <!-- This is optional, if not provided the task will invoice all items on the order -->
      <InvoiceProduct>
        <sku>TEST001</sku>
        <name>Test Product</name>
        <qty>1.0000</qty>
      </InvoiceProduct>
      <InvoiceProduct>
        <sku>TEST002</sku>
        <name>Test Product 2</name>
        <qty>1.0000</qty>
      </InvoiceProduct>
    </items>
  </InvoiceInfo>
</ArrayOfInvoiceInfo>
```