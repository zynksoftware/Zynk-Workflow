---
slug: export-item-movements-from-peoplevox
title: Export Item Movements from Peoplevox
---

This task will export item movement information from Peoplevox in XML format, for detailed information see [Peoplevox Item Movement XML](peoplevox-item-movement-xml).  The information is exported using the "Item movement history" report that can be ran through your Peoplevox web application.  You can add date filters and search clauses to limit the data that is returned.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set to False only bring back modified information since that last time the task was ran. Zynk will update the Modified Since setting based on the information returned from the report.  Set to  True to download all data.  Note, in both cases the Search Clauses will be applied to the report which can limit the data that is returned.  Defaults to `False`.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Modified Since
_Required_  
The date to use to limit the data returned, this is only used when Download All is set to False.  Zynk will update the Modified Since setting based on the information returned from the report.  Defaults to the time when the task was added to the Workflow.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_item_movements.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example output file, for detailed information see [Peoplevox Item Movement XML](peoplevox-item-movement-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<ItemMovementHistory 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ItemMovement>
    <Item_code>TEST01</Item_code>
    <Item_name>This is a test item.</Item_name>
    <Item_barcode>5016447208891</Item_barcode>
    <Date_timestamp>'05/07/2017 10:05'</Date_timestamp>
    <User>Joe Harrison</User>
    <From>XYZ</From>
    <To>ABC</To>
    <Quantity>5</Quantity>
    <Comments>Despatched</Comments>
    <Sales_order_number>1234</Sales_order_number>
    <From_Container />
    <To_Container />
    <History_Id>160738</History_Id>
    <Site_reference>PrimarySite</Site_reference>
    <Buy_Price>0.35</Buy_Price>
    <Manufacturer_item_no>H03M020</Manufacturer_item_no>
    <Item_group_name>Item group</Item_group_name>
    <Attribute_1>Whitefurze</Attribute_1>
    <Attribute_2>n/a</Attribute_2>
    <Attribute_3>Clear</Attribute_3>
    <Attribute_4 />
    <Attribute_5 />
    <Attribute_6 />
    <Attribute_7 />
    <Attribute_8 />
    <Attribute_9 />
    <Attribute_10 />
    <Attribute_11 />
    <Attribute_12 />
    <Attribute_13 />
    <Attribute_14 />
    <Attribute_15 />
    <Register_Reason />
  </ItemMovement>
</ItemMovementHistory>
```