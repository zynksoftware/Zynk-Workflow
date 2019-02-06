---
slug: export-despatches-from-peoplevox
title: Export Despatches from Peoplevox
---

This task will export despatch information from Peoplevox in XML format, for detailed information see [Peoplevox Despatch XML](peoplevox-despatch-xml).  The information is exported using the "Despatch summary" report that can be ran through your Peoplevox web application.  You can add date filters and search clauses to limit the data that is returned.

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
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_despatch_summary.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example output file, for detailed information see [Peoplevox Despatch XML](peoplevox-despatch-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<DespatchSummary 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Despatch>
    <Salesorder_number>1234</Salesorder_number>
    <Requested_delivery_date>'01/07/2017 23:46'</Requested_delivery_date>
    <Despatch_number>456</Despatch_number>
    <Carrier>DPD</Carrier>
    <Service>UK Standard 1-2 Days (Tracked)</Service>
    <Despatch_date>'03/07/2017 06:03'</Despatch_date>
    <Tracking_number>1234567890</Tracking_number>
    <Item_name>Test item</Item_name>
    <No_of_items>7</No_of_items>
    <Destination_country>England</Destination_country>
    <Site_reference>PrimarySite</Site_reference>
    <Parent />
    <Item_code>XXXX</Item_code>
    <Username>JoeH</Username>
    <Carrier_reference>DPD</Carrier_reference>
    <Service_type_code>UK Standard 1-2 Days (Tracked)</Service_type_code>
    <Customer_order_reference />
    <Shipping_cost>5.95</Shipping_cost>
    <Email>joe@zynk.com</Email>
    <Contact_name />
    <Total_sale>29.89</Total_sale>
    <Discount />
    <Tax_paid>4.98</Tax_paid>
    <Channel_name />
    <Sales_order_attribute_1 />
    <Sales_order_attribute_2 />
    <Sales_order_attribute_3 />
    <Sales_order_attribute_4 />
    <Sales_order_attribute_5 />
    <Item_barcode>5038135173981</Item_barcode>
    <Item_description>This is a test item created for test purposes.</Item_description>
    <Default_suppliers_part_number>17398</Default_suppliers_part_number>
    <Item_buy_price>1.29</Item_buy_price>
    <Item_wholesale_price>0.00</Item_wholesale_price>
    <Item_retail_price>3.42</Item_retail_price>
    <Item_weight>0.00</Item_weight>
    <Item_height />
    <Item_width />
    <Item_depth />
    <Item_tags />
    <Item_attribute_1>X</Item_attribute_1>
    <Item_attribute_2>Y</Item_attribute_2>
    <Item_attribute_3>Z</Item_attribute_3>
    <Item_attribute_4 />
    <Item_attribute_5 />
    <Item_attribute_6 />
    <Item_attribute_7 />
    <Item_attribute_8 />
    <Item_attribute_9 />
    <Item_attribute_10 />
    <Item_attribute_11 />
    <Item_attribute_12 />
    <Item_attribute_13 />
    <Item_attribute_14 />
    <Item_attribute_15 />
  </Despatch>
</DespatchSummary>
```