---
slug: exporting-receipts-from-prosku
redirect_from: "/article/exporting-receipts-from-prosku"
title: Exporting Receipts From ProSKU
---
This task will export receipts details from ProSKU to an XML file. 

## Settings
### Export Date
_Required_  
Receipts created or modified beyond this date will be exported.

### Connection
_Required_  
The ProSKU connection to use. See the [Connecting to ProSKU](connecting-to-prosku) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the receipts to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<APIResponse>
  <total_receipts>1</total_receipts>
  <receipts>
    <receipt>
      <receipt_number>000005</receipt_number>
      <receipt_date>10/07/2017</receipt_date>
      <supplier_detail>supplier2</supplier_detail>
      <receipt_status>completed</receipt_status>
      <lines>
        <line>
          <product_code>01-00228</product_code>
          <line_id>25865</line_id>
          <quantity>12</quantity>
          <location>01A01C</location>
          <completed_at>10/07/17 14:39:52</completed_at>
        </line>
      </lines>
    </receipt>
  </receipts>
</APIResponse>
```
