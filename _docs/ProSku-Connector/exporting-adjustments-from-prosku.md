---
slug: exporting-adjustments-from-prosku
redirect_from: "/article/exporting-adjustments-from-prosku"
title: Exporting Adjustments From ProSKU
---
This task will export Adjustment details from ProSKU to an XML file. 

## Settings
### Export Date
_Required_  
Adjustments created or modified beyond this date will be exported.

### Connection
_Required_  
The ProSKU connection to use. See the [Connecting to ProSKU](connecting-to-prosku) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the despatches to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<APIResponse>
  <total_adjustments>2</total_adjustments>
  <last_change>10/07/2017 14:39:52</last_change>
  <Adjustments>
    <Adjustment>
      <product_code>1000-0000-0107</product_code>
      <changes>
        <change>
          <type_of_change>Creation</type_of_change>
          <adjusted_quantity>50.0</adjusted_quantity>
          <reason>Warm</reason>
          <updated_at>19/06/2017 09:51:36</updated_at>
          <customer_stock_status>Dry</customer_stock_status>
        </change>
      </changes>
      <stock_report>
        <available>0</available>
        <unavailabale>50</unavailabale>
        <unchecked>0</unchecked>
        <expected>0</expected>
        <onorder>0</onorder>
      </stock_report>
    </Adjustment>
    <Adjustment>
      <product_code>01-00228</product_code>
      <changes>
        <change>
          <type_of_change>Updated</type_of_change>
        </change>
      </changes>
      <stock_report>
        <available>13</available>
        <unavailabale>0</unavailabale>
        <unchecked>0</unchecked>
        <expected>1</expected>
        <onorder>10</onorder>
      </stock_report>
    </Adjustment>
  </Adjustments>
</APIResponse>
```
