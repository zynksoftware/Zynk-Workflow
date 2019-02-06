---
slug: export-report-from-peoplevox
title: Export Report from Peoplevox
---

This task will export information from the specified report in Peoplevox to XML format, the format will depend on what settings are enabled on the task the report used.  

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

### Date Modified Field
_Dependant_  
If you have Export All set to False this is date field to use on the report that Zynk will filter against.  If Export All is set to True you do not need to update this field.  Defaults to `Despatch date`.  You will need to check the report you are exporting to find the column name of the field to use.

### Export All
_Required_  
Set to False only bring back modified information since that last time the task was ran. Zynk will update the Modified Since setting based on the information returned from the report.  Set to  True to download all data.  Note, in both cases the Search Clauses will be applied to the report which can limit the data that is returned.  Defaults to `False`.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Order By Field
_Optional_  
The field to use to order the records by.  If left empty, it will default to the date created field.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_report.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Template
_Required_  
The name of the report you want to export from Peoplevox, this must match the name as showing through the reporting section of your Peoplevox web application.  Defaults to `Despatch summary`.

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Export As Elements
_Required_  
Set to False to export all information as attributes in the output XML file, this usually ends up with a smaller file size.  Note, when using attributes in XSLT you must prepend the name of the field with `@` e.g. `@Item_code`.  Set to True to export all information as elements in the output XML file.  Defaults to `False`.

### Root
_Required_  
The name of the main root node of the output XML file, using this field you can customise the format of the output if required.  Defaults to `Rows`.

### Row
_Required_  
The name of each row created in the output XML file that relates to each record returned in the report, using this field you can customise the format of the output if required.  Defaults to `Row`.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML

### Item Availability Report

 * **Template** - Item availability latest reconciliation
 * **Export As Elements** - False
 * **Root** - Rows
 * **Row** - Row

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<Rows>
  <Row Item_code="ABBUILTIN/15/0/2" Name="" Barcode="800811232" Quantity_changed="-10" On_hand="0" Activity="Sales order allocation" Reason="Sales order Allocation" User="admin" Date_time="'03/07/2017 10:52:21'" Default_economic_order_quantity="" Default_lead_time="" Default_suppliers_part_number="" Has_serial_number="False" Use_manufacturers_serial_number="False" Reorder_point="0" Shelf_life="" Default_number_of_items_per_container="" Default_number_of_items_per_outercase="" Buy_price="0.00" Wholesale_price="0.00" Retail_price="0.00" Weight="0.00" Height="0.00" Width="0.00" Depth="0.00" Item_type_group="Item group" Tags="" Allocated="10" Available="0" On_order="0" Attribute1="" Attribute2="" Attribute3="" Attribute4="" Attribute5="" Attribute6="" Attribute7="" Attribute8="" Attribute9="" Attribute10="" Attribute11="" Attribute12="" Attribute13="" Attribute14="" Attribute15="" />
</Rows>
```

### Item Movement Report

 * **Template** - Item movement history
 * **Export As Elements** - True
 * **Root** - Movements
 * **Row** - Movement

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<Movements>
  <Movement>
    <Item_code>ABBUILTIN/15/0/2</Item_code>
    <Item_name></Item_name>
    <Item_barcode>800811232</Item_barcode>
    <Date_timestamp>'03/07/2017 10:52:21'</Date_timestamp>
    <User>Admin</User>
    <From></From>
    <To>Pick.Default</To>
    <Quantity>10</Quantity>
    <Comments>Added through adjustment module</Comments>
    <Sales_order_number></Sales_order_number>
    <From_Container></From_Container>
    <To_Container></To_Container>
    <History_Id>1</History_Id>
    <Site_reference>PrimarySite</Site_reference>
    <Buy_Price>0.00</Buy_Price>
    <Location_type_from></Location_type_from>
    <Location_type_to>Despatch</Location_type_to>
    <Manufacturer_item_no.></Manufacturer_item_no.>
    <Item_group_name>Item group</Item_group_name>
    <Attribute_1></Attribute_1>
    <Attribute_2></Attribute_2>
    <Attribute_3></Attribute_3>
    <Attribute_4></Attribute_4>
    <Attribute_5></Attribute_5>
    <Attribute_6></Attribute_6>
    <Attribute_7></Attribute_7>
    <Attribute_8></Attribute_8>
    <Attribute_9></Attribute_9>
    <Attribute_10></Attribute_10>
    <Attribute_11></Attribute_11>
    <Attribute_12></Attribute_12>
    <Attribute_13></Attribute_13>
    <Attribute_14></Attribute_14>
    <Attribute_15></Attribute_15>
    <Register_Reason></Register_Reason>
  </Movement>
</Movements>
```
