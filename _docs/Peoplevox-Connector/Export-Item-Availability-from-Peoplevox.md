---
slug: export-item-availability-from-peoplevox
title: Export Item Availability from Peoplevox
---

This task will export item availability information from Peoplevox in XML format, for detailed information see [Peoplevox Item Availability XML](peoplevox-item-availability-xml).  The information is exported using the "Item availability latest reconciliation" report that can be ran through your Peoplevox web application.  You can add date filters and search clauses to limit the data that is returned.

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
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_item_availability.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example output file, for detailed information see [Peoplevox Item Availability XML](peoplevox-item-availability-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<Items 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Item>
    <Item_code>ABBUILTIN/15/0/2</Item_code>
    <Name />
    <Barcode>800811232</Barcode>
    <On_hand>0</On_hand>
    <Activity>Sales order allocation</Activity>
    <Reason>Sales order Allocation</Reason>
    <User>admin</User>
    <Date_time>'03/07/2017 10:52'</Date_time>
    <Default_economic_order_quantity />
    <Default_lead_time />
    <Default_suppliers_part_number />
    <Has_serial_number>False</Has_serial_number>
    <Use_manufacturers_serial_number>False</Use_manufacturers_serial_number>
    <Reorder_point>0</Reorder_point>
    <Shelf_life />
    <Default_number_of_items_per_container />
    <Default_number_of_items_per_outercase />
    <Buy_price>0.00</Buy_price>
    <Wholesale_price>0.00</Wholesale_price>
    <Retail_price>0.00</Retail_price>
    <Weight />
    <Height />
    <Width />
    <Depth />
    <Item_type_group>Item group</Item_type_group>
    <Tags />
    <Allocated>10</Allocated>
    <On_order>0</On_order>
    <Attribute1 />
    <Attribute2 />
    <Attribute3 />
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
  </Item>
</Items>
```