---
slug: exporting-stock-from-prosku
redirect_from: "/article/exporting-stock-from-prosku"
title: Exporting Stock From ProSKU
---
This task will export stock details from ProSKU for an individual item to an XML file. 

## Settings
### Connection
_Required_  
The ProSKU connection to use. See the [Connecting to ProSKU](connecting-to-prosku) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the products to.

### Product Code
_Required_  
The product code of the item that stock records should be downloaded for.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<APIResponse>
  <product-code>01-00228</product-code>
  <available type="integer">1</available>
  <unavailabale type="integer">0</unavailabale>
  <unchecked type="integer">0</unchecked>
  <expected type="integer">1</expected>
  <onorder type="integer">10</onorder>
</APIResponse>
```
