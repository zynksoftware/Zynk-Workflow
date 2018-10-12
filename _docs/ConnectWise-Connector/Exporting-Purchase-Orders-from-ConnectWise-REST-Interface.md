---
slug: exporting-purchase-orders-from-connectwise-rest-interface
title: Exporting Purchase Orders from ConnectWise REST Interface
---
This task will export purchase orders from ConnectWise in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Export Item Lines
_Required_  
Set to true to include the item lines in the exported data.

### Export Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'New', only purchase orders created after this date will be exported. This date will update automatically each time the task runs, to ensure only new puchase orders are exported each time.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only purchase orders updated after this date will be downloaded. This date will update automatically each time the task runs, to ensure only modified invoices are exported each time.

### Export Settings > Export Modified, New or All Records
_Required_  
Choose which records should be downloaded. The available options are:

* __Modified__ - Only records updated after the date shown in the 'Date Modified' setting will be downloaded.
* __New__ - Only records created after the date shown in the 'Date Created' setting will be downloaded.
* __All__ - All records will be downloaded, regardless of when they were created or updated.

### Export Settings > Page Size
_Required_  
The number of records to include in each page of results. Defaults to 100. Increasing this value will reduce the number of requests made to the API. The maximum value is 1000.

### Output File
_Required_  
The name of the file to export the purchase orders to.

### References To Fetch
_Optional_  
The exported data may include fields which reference other records in ConnectWise. If you specify the reference field names here, and the task will fetch the related records and include them in the exported data. The supported fields are listed below: 

* customerCompany
* customerContact
* customerSite
* shipmentMethod
* status
* taxCode
* terms
* vendorCompany
* vendorContact
* vendorSite
* warehouse
* currency
* purchaseOrderItem/product
* purchaseOrderItem/shipmentMethod
* purchaseOrderItem/warehouse
* purchaseOrderItem/warehouseBin

### Where Settings > Child Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields which are part of an array.

### Where Settings > Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields.

### Where Settings > Custom Field Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding custom fields.

### Where Settings > Condition > Comparison
_Required_  
The following types of filter are available:

* __Contains__ - Returns records where the field contains the specified value.
* __Equal__ - Returns records where the field matches the specified value.
* __GreaterThan__ - Returns records where the field is greater than the specified value.
* __GreaterThanOrEqual__ - Returns records where the field is greater than or equal to the specified value.
* __In__ - Returns records where the field matches one of the specified values.
* __Like__ - Returns records where the field contains the specified value.
* __LessThan__ - Returns records where the field is less than the specified value.
* __LessThanOrEqual__ - Returns records where the field is less than or equal to the specified value.
* __NotContains__ - Returns records where the field does not contain the specified value.
* __NotEqual__ - Returns records where the field does not match the specified value.
* __NotIn__ - Returns records where the field does not match one of the specified values.
* __NotLike__ - Returns records where the field does not contain the specified value.

### Where Settings > Condition > Field
_Required_  
The name of the field the condition is to be based upon. The name should match the API field name, as seen in the output file. If using a reference field, include the name of the reference field followed by a slash, then the field to filter on. e.g. `defaultContact/name`

### Filter Groups > Condition > Logic Operator
_Optional_  
The logic operator to use with the next condition when building the where clause. Choose from:

* __And__ - Will return records which meet all of the conditions specified.
* __Or__ - Will return records which meet at least one of the conditions specified.

### Filter Groups > Condition > Value
_Optional_  
The value the filter is to be based upon.

* String values should be surrounded by quotes. e.g. `"John"`
* Boolean values should be specified as either `True` or `False`, with no quotes.
* Datetime values should be specified in ISO8601 format, surrounded by square brackets. e.g. `[2000-01-31T14:51:00Z]`
* Null is specified as `null`.
* When using the In or NotIn comparison, specify a comma separated list of values surrounded by brackets. e.g. `("John", "Ben")`

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<PurchaseOrders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrder>
    <id>1</id>
    <externalId />
    <_info>
      <dateEntered>2011-03-23T18:48:40Z</dateEntered>
      <enteredBy>Admin1</enteredBy>
      <lastUpdated>2011-03-23T18:48:40Z</lastUpdated>
      <updatedBy>Admin1</updatedBy>
    </_info>
    <businessUnitId>10</businessUnitId>
    <closedFlag>false</closedFlag>
    <customerCompany>
      <id>37</id>
      <name>Arts Midwest</name>
      <identifier>ArtsMidwest</identifier>
    </customerCompany>
    <customerSite>
      <id>41</id>
      <name>Main</name>
    </customerSite>
    <dateClosed xsi:nil="true" />
    <dropShipCustomerFlag>true</dropShipCustomerFlag>
    <enteredBy>Admin1</enteredBy>
    <freightCost>0</freightCost>
    <freightTaxTotal>0</freightTaxTotal>
    <locationId>2</locationId>
    <poDate>2011-03-23T00:00:00Z</poDate>
    <poNumber>0</poNumber>
    <salesTax>0</salesTax>
    <shipmentDate xsi:nil="true" />
    <shipmentMethod>
      <id>8</id>
      <name>Courier Service</name>
    </shipmentMethod>
    <status>
      <id>1</id>
      <name>New</name>
    </status>
    <subTotal>200</subTotal>
    <taxCode>
      <id>11</id>
      <name>Standard VAT</name>
    </taxCode>
    <taxFreightFlag>false</taxFreightFlag>
    <taxPoFlag>false</taxPoFlag>
    <terms>
      <id>2</id>
      <name>Net 10</name>
    </terms>
    <total>200</total>
    <updateShipmentInfo xsi:nil="true" />
    <updateVendorOrderNumber xsi:nil="true" />
    <vendorCompany>
      <id>8</id>
      <name>Angry Fox, Co.</name>
      <identifier>AngryFoxCo</identifier>
    </vendorCompany>
    <vendorContact>
      <id>20</id>
      <name>Robert Storts</name>
    </vendorContact>
    <vendorInvoiceDate xsi:nil="true" />
    <vendorSite>
      <id>7</id>
      <name>Main</name>
    </vendorSite>
    <currency>
      <id>4</id>
      <name>French Francs</name>
      <symbol>FFr</symbol>
      <isoCode>EUR</isoCode>
    </currency>
    <customFields>
      <customField>
        <id>1</id>
        <caption>Sign Off</caption>
        <type>Checkbox</type>
        <entryMethod>EntryField</entryMethod>
        <numberOfDecimals>0</numberOfDecimals>
      </customField>
    </customFields>
    <purchaseOrderItems>
      <purchaseOrderItem>
        <id>1</id>
        <_info>
          <dateEntered>2011-03-23T18:48:40Z</dateEntered>
          <enteredBy>Conversion</enteredBy>
          <lastUpdated>2011-03-23T18:48:40Z</lastUpdated>
          <updatedBy>Admin1</updatedBy>
        </_info>
        <backorderedFlag>false</backorderedFlag>
        <canceledFlag>false</canceledFlag>
        <closedFlag>false</closedFlag>
        <dateCanceled xsi:nil="true" />
        <dateCanceledUtc xsi:nil="true" />
        <description>SPAM -ConnectFilter</description>
        <displayInternalNotesFlag>false</displayInternalNotesFlag>
        <expectedShipDate xsi:nil="true" />
        <lineNumber>1</lineNumber>
        <packingSlip>0</packingSlip>
        <product>
          <id>750</id>
          <identifier>SPAM -ConnectFilter</identifier>
        </product>
        <purchaseOrderId>1</purchaseOrderId>
        <quantity>20</quantity>
        <receivedQuantity>20</receivedQuantity>
        <shipDate xsi:nil="true" />
        <shipmentMethod>
          <id>8</id>
          <name>Courier Service</name>
        </shipmentMethod>
        <tax>0</tax>
        <unitCost>10</unitCost>
        <unitOfMeasure>
          <id>12</id>
          <name>User-based</name>
        </unitOfMeasure>
        <receivedStatus>FullyReceived</receivedStatus>
      </purchaseOrderItem>
    </purchaseOrderItems>
  </PurchaseOrder>
</PurchaseOrders>
```
