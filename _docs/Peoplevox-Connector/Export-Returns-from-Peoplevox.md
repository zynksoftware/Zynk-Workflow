---
slug: export-returns-from-peoplevox
title: Export Returns from Peoplevox
---

This task will export return information from Peoplevox in XML format, for detailed information see [Peoplevox Return XML](peoplevox-return-xml).  The information is exported using the "Return summary" report that can be ran through your Peoplevox web application.  You can add date filters and search clauses to limit the data that is returned.

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
Example output file, for detailed information see [Peoplevox Return XML](peoplevox-return-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<ReturnsSummary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Return>
    <Return_code>RET1</Return_code>
    <Return_date>'14/06/2018 16:55:07'</Return_date>
    <Quantity>1</Quantity>
    <Item_name>Sample Product</Item_name>
    <Sales_order_number>POO2</Sales_order_number>
    <Despatch_date>'14/06/2018 16:52:17'</Despatch_date>
    <Return_reason>Why Not</Return_reason>
    <Return_condition>NEW</Return_condition>
    <Return_comments>Internal notes: </Return_comments>
    <Days_since_despatch>237</Days_since_despatch>
    <Item_barcode>5060466510500</Item_barcode>
    <Sales_order_contact_name>Zynk Software</Sales_order_contact_name>
    <Customer_phone_number>0191 303 7279</Customer_phone_number>
    <Item_sale_price>3.00</Item_sale_price>
    <Sales_order_email>support@zynk.com</Sales_order_email>
    <Customer_purchase_order_reference_number>INT001</Customer_purchase_order_reference_number>
    <Channel_name>Web</Channel_name>
    <Payment_type>Card</Payment_type>
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
    <Site_reference>PrimarySite</Site_reference>
    <Is_Reusable>True</Is_Reusable>
    <Item_code>PROD001</Item_code>
  </Return>
</ReturnsSummary>
```