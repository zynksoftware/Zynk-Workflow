---
slug: exporting-stock-records-from-sage-200-online
redirect_from: "/article/exporting-stock-records-from-sage-200-online"
title: Exporting Stock Records From Sage 200 Online
---
This task will download stock records from Sage 200 Online in [Sage 200 Online Stock Record XML](sage-200-online-stock-record-xml) format.

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
Allows a filter to be set to limit the data that is returned. For example, you can return the stock record with product code 'PRINTER001' using: `code eq 'PRINTER001'`

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
<Products xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Product>
    <id>15536</id>
    <date_time_updated>2016-05-17T14:25:51.82</date_time_updated>
    <code>TEST001</code>
    <name>Test Product</name>
    <description />
    <barcode />
    <allow_sales_order>true</allow_sales_order>
    <product_group_id>14910</product_group_id>
    <tax_code_id>2</tax_code_id>
    <product_group>
      <id>14910</id>
      <date_time_updated>2015-10-30T22:33:22.773</date_time_updated>
      <code>GROUP01</code>
      <description>Default Product Group</description>
      <product_type>EnumStockItemTypeStock</product_type>
      <can_levels_go_negative>true</can_levels_go_negative>
    </product_group>
  </Product>
</Products>
```
