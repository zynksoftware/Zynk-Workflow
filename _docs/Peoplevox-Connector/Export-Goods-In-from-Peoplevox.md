---
slug: export-goods-in-from-peoplevox
title: Export Goods In from Peoplevox
---

This task will export goods in information from Peoplevox in XML format, for detailed information see [Peoplevox Goods In XML](peoplevox-goods-in-xml).  The information is exported using the "Goods in summary" report that can be ran through your Peoplevox web application.  You can add date filters and search clauses to limit the data that is returned.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to 1.

### Columns
_Optional_  
By default all columns returned in the report will be included in the output file.  You can optionally provide a list of columns to limit the amount of data returned.  Note the columns must be as they are shown through the reporting in the Peoplevox web application e.g. `Salesorder number` for the `Despatch summary` report.

### Created Since
_Required_  
The date to use to limit the data returned, this is only used when Download All is set to False.  Zynk will update the setting based on the information returned from the report.  Defaults to the time when the task was added to the Workflow.

### Export All
_Required_  
Set to False only bring back modified information since that last time the task was ran. Zynk will update the Modified Since setting based on the information returned from the report.  Set to  True to download all data.  Note, in both cases the Search Clauses will be applied to the report which can limit the data that is returned.  Defaults to `False`.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_goods_in_summary.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example output file, for detailed information see [Peoplevox Goods In XML](peoplevox-goods-in-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<GoodsInSummary 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <GoodsIn>
    <Goods_in_reference_number>4604</Goods_in_reference_number>
    <Delivery_date>'05/07/2017 11:42'</Delivery_date>
    <Reconciled_date>'05/07/2017 15:48'</Reconciled_date>
    <Carrier_name>Unknown</Carrier_name>
    <User_name>JoeH</User_name>
    <Item_code>STRAPPING</Item_code>
    <Item_name>Strapping 12 x 55 x 3000m</Item_name>
    <Item_barcode>STRAPPING</Item_barcode>
    <Description />
    <Quantity>30</Quantity>
    <Default_economic_order_quantity />
    <Default_lead_time />
    <Default_suppliers_part_number />
    <Has_serial_number>False</Has_serial_number>
    <Use_manufacturers_serial_number>False</Use_manufacturers_serial_number>
    <Reorder_point>0</Reorder_point>
    <Traceability>False</Traceability>
    <Shelf_life />
    <Default_number_of_items_per_container />
    <Default_number_of_items_per_outercase />
    <Buy_price>19.82</Buy_price>
    <Wholesale_price>0.00</Wholesale_price>
    <Retail_price>0.00</Retail_price>
    <Weight />
    <Height />
    <Width />
    <Depth />
    <Unit_of_measure>Unit</Unit_of_measure>
    <Tags />
    <Purchase_order_number>PO29</Purchase_order_number>
    <Delivery_note_number />
    <Attribute1>Gordian </Attribute1>
    <Attribute2>n/a</Attribute2>
    <Attribute3>n/a</Attribute3>
    <Attribute4 />
    <Attribute5 />
    <Attribute6 />
    <Attribute7 />
    <Attribute8 />
    <Attribute9 />
    <Attribute10 />
    <Attribute11 />
    <Attribute12 />
    <Attribute13 />
    <Attribute14 />
    <Attribute15 />
    <Site_reference>PrimarySite</Site_reference>
    <Purchase_order_supplier>Gordian Strapping</Purchase_order_supplier>
  </GoodsIn>
</GoodsInSummary>
```