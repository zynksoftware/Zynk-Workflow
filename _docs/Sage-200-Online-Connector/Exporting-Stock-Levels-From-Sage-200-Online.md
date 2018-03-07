---
slug: exporting-stock-levels-from-sage-200-online
redirect_from: "/article/exporting-stock-levels-from-sage-200-online"
title: Exporting Stock Levels From Sage 200 Online
---
This task will download stock levels from Sage 200 Online in [Sage 200 Online Stock Level XML](sage-200-online-stock-level-xml) format.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified or All Records' setting is set to 'Modified', only records modified after this date will be downloaded. The date will update automatically each time the task runs, to ensure that only records modified since the task last ran will be downloaded.

### Export Settings > Export Modified or All Records
_Required_  
Used to choose which records should be included in the download. The available options are:

* __All__ - All records will be downloaded, regardless of whether or not they have been updated since the task last ran.
* __Modified__ - Only records created or updated since the task last ran will be downloaded.

### Filter
_Optional_  
Allows a filter to be set to limit the data that is returned. For example, you can return sales levels where the quantity is less than 10 using: `quantity_in_stock lt 10`

Sage 200 Online uses the OData protocol, and expects the filter to be specified in this format. You can find more information on OData filters [here](http://www.odata.org/getting-started/basic-tutorial/#queryData).

### Output File
_Required_  
The name of the file to save the downloaded records to.

### Page Size
_Required_  
The number of records to include in each page of results downloaded from Sage. Increasing this value will speed up the download, but will use more memory. Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<WarehouseHoldings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <WarehouseHolding>
    <id>15596</id>
    <warehouse_id>1</warehouse_id>
    <product_id>15536</product_id>
    <reorder_level>0.00000</reorder_level>
    <minimum_level>0.00000</minimum_level>
    <maximum_level>0.00000</maximum_level>
    <confirmed_qty_in_stock>148.00000</confirmed_qty_in_stock>
    <unconfirmed_qty_in_stock>0.00000</unconfirmed_qty_in_stock>
    <quantity_in_stock>148.00000</quantity_in_stock>
    <quantity_allocated_stock>0.00000</quantity_allocated_stock>
    <quantity_allocated_sop>4.00000</quantity_allocated_sop>
    <quantity_allocated_bom>0.00000</quantity_allocated_bom>
    <quantity_allocated>4.00000</quantity_allocated>
    <warehouse>
      <id>1</id>
      <name>HOME</name>
      <date_time_updated>2015-10-30T22:33:16.18</date_time_updated>
    </warehouse>
    <product>
      <id>15536</id>
      <date_time_updated>2016-05-17T14:25:51.82</date_time_updated>
      <code>TEST001</code>
      <name>Test Product</name>
      <description />
      <barcode />
      <allow_sales_order>true</allow_sales_order>
      <product_group_id>14910</product_group_id>
      <tax_code_id>2</tax_code_id>
    </product>
    <date_time_updated>2016-05-17T14:25:51.897</date_time_updated>
  </WarehouseHolding>
</WarehouseHoldings>
```
