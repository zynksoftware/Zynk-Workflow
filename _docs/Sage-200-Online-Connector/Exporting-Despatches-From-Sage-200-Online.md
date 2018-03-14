---
slug: exporting-despatches-from-sage-200-online
redirect_from: "/article/exporting-despatches-from-sage-200-online"
title: Exporting Despatches From Sage 200 Online
---
This task will download despatches from Sage 200 Online to an XML file.

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
Allows a filter to be set to limit the data that is returned. For example, you can return the despatches for sales order number 0000000001 using: `sop_order_document_no eq '0000000001'`

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
<DespatchLineViews xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <DespatchLineView>
    <sop_despatch_line_id>16268</sop_despatch_line_id>
    <sop_despatch_line_quantity>2.00000</sop_despatch_line_quantity>
    <sop_despatch_id>16267</sop_despatch_id>
    <sop_despatch_document_no>0000000001</sop_despatch_document_no>
    <sop_despatch_date>2016-05-09T00:00:00</sop_despatch_date>
    <sop_despatch_user_name>Demo Site</sop_despatch_user_name>
    <sop_order_line_id>16057</sop_order_line_id>
    <sop_order_line_print_sequence_number>1</sop_order_line_print_sequence_number>
    <sop_order_line_quantity>2.00000</sop_order_line_quantity>
    <sop_order_line_despatch_quantity>2.00000</sop_order_line_despatch_quantity>
    <sop_order_id>16056</sop_order_id>
    <sop_order_document_no>0000000001</sop_order_document_no>
    <sop_order_document_date>2016-05-09T00:00:00</sop_order_document_date>
    <sop_order_document_status_type>2</sop_order_document_status_type>
    <sop_order_customer_document_no>12345</sop_order_customer_document_no>
    <customer_id>14950</customer_id>
    <customer_reference>ZYNK0001</customer_reference>
    <customer_name>Zynk Software</customer_name>
    <product_id>15536</product_id>
    <product_code>TEST001</product_code>
    <product_name>Test Product</product_name>
    <warehouse_holding_id>15596</warehouse_holding_id>
    <warehouse_id>1</warehouse_id>
    <warehouse_name>HOME</warehouse_name>
    <date_time_updated>2016-05-09T11:24:12.983</date_time_updated>
  </DespatchLineView>
</DespatchLineViews>
```
