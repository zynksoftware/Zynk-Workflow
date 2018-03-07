---
slug: exporting-despatches-from-prosku
redirect_from: "/article/exporting-despatches-from-prosku"
title: Exporting Despatches From ProSKU
---
This task will export despatch details from ProSKU to an XML file. 

## Settings
### Export Date
_Required_  
Despatches created or modified beyond this date will be exported.

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
  <total_despatches>1</total_despatches>
  <Despatch_notes>
    <Despatch_note>
      <despatch_number>006579</despatch_number>
      <order_number>000001</order_number>
      <delivery_date>01/07/2017 11:44</delivery_date>
      <carrier_data></carrier_data>
      <additional_ref>22</additional_ref>
      <deliver_to>A1 Design Services 67a Station Road Blackpool BP12 7HT</deliver_to>
      <confirmed_at>01/07/2017 11:44:08</confirmed_at>
      <despatch_lines>
        <despatch_line>
          <product_code>LAMP001</product_code>
          <quantity>2</quantity>
        </despatch_line>
      </despatch_lines>
    </Despatch_note>
  </Despatch_notes>
</APIResponse>
```
