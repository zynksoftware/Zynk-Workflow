---
slug: uploading-product-attributes-to-magento
redirect_from: "/article/271-uploading-product-attributes-to-magento"
title: Importing Product Attributes to Magento
---
This task will import attributes to existing products in Magento. The input file should be in Magento XML format.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output failed product attribute imports to.

### Input File
_Required_  
The XML file containing the product attributes to import to Magento.

### Success File
_Required_  
The XML file to output successful product attribute imports to.

### Attribute Set
_Required_  
The ID or name of the attribute set to import attributes to. This must already exist in Magento, the task will not create attribute sets. 

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).