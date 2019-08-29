---
slug: uploading-product-categories-to-magento
redirect_from: "/article/272-uploading-product-categories-to-magento"
title: Importing Product Categories to Magento
---
This task will import product categories to Magento. The input file should be in Magento XML format.

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

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by the task. This setting will only work where an `<external_id>` element is provided in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings).