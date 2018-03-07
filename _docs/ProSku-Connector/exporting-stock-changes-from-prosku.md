---
slug: exporting-stock-changes-from-prosku
redirect_from: "/article/exporting-stock-changes-from-prosku"
title: Exporting Stock Changes From ProSKU
---
This task will export any stock changes from ProSKU to an XML file. 

## Settings
### Connection
_Required_  
The ProSKU connection to use. See the [Connecting to ProSKU](connecting-to-prosku) article if you require more information on how to create/manage connections.

### Export Date
_Required_  
Stock changes beyond this date will be exported.

### Output File
_Required_  
The name of the file to export the products to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<APIResponse>
  <per_page>50</per_page>
  <current_page>1</current_page>
  <total_pages>1</total_pages>
  <total_changes>1</total_changes>
  <last_change>23/02/2018 12:00:00 GMT</last_change>
  <changes>
    <change>
      <product_code>1000-0000-0107</product_code>
      <updated_at>23/02/2018 12:00:00 GMT</updated_at>
      <stock_report>
        <available>99</available>
        <unavailable>0</unavailable>
        <unchecked>0</unchecked>
        <expected>0</expected>
        <onorder>0</onorder>
      </stock_report>
    </change>
  </changes>
</APIResponse>
```
