---
slug: importing-records-to-bxp
redirect_from: "/article/973-uploading-records-to-bxp"
title: Importing Records To BXP
---
This task will read records from an XML file, and create new or update existing records in BXP based on whether a match was found.

## Upload Records
### Connection 
_Required_  
The connection to use. See [Connecting to BXP](connecting-to-bxp).

### Fail File
_Required_  
The file for failed records to be written to.

### Input File
_Required_  
The file containing records you'd like to import.

### Success File
_Required_  
The for successful records to be written to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once by Zynk.


## Examples
A sample input file is shown below, containing a single record to be uploaded to form ID 123, and a pair of related records to upload to form ID 124. Existing records will be matched in BXP based on the SOPOrderReturnID and SOPOrderReturnLineID fields. For more detailed information about the XML format, see [BXP Record XML](bxp-record-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<Records FormId="123">
  <Record>
    <ExternalId>5603567</ExternalId>
    <MatchField Name="SOPOrderReturnID" Value="5603567" />
    <Field Name="DocumentNo" Value="0000069771" />
    <Field Name="DocumentDate" Value="2016-11-20 00:00:00.000" />
    <Field Name="CustomerDocumentNo" Value="912741" />
    <Field Name="CustomerID" Value="469124" />
    <Field Name="RequestedDeliveryDate" Value="2016-11-20 00:00:00.000" />
    <Field Name="PromisedDeliveryDate" Value="2016-11-20 00:00:00.000" />
    <Field Name="SubtotalGoodsValue" Value="550.00" />
    <Field Name="TotalNetValue" Value="550.00" />
    <Field Name="TotalTaxValue" Value="0.00" />
    <Field Name="TotalGrossValue" Value="550.00" />
    <Field Name="DocumentDiscountPercent" Value="0.00" />
    <Field Name="DateTimeCreated" Value="2016-09-11 15:32:27.407" />
    <Field Name="DateTimeUpdated" Value="2016-12-16 15:24:23.207" />
    <RelatedRecords FormId="124">
      <Record>
        <ExternalId>5603569</ExternalId>
        <MatchField Name="SOPOrderReturnLineID" Value="5603569" />
        <Field Name="SOPOrderReturnID" Value="5603567" />
        <Field Name="ItemCode" Value="PROD001" />
        <Field Name="LineQuantity" Value="0" />
        <Field Name="LineTotalValue" Value="0" />
        <Field Name="LineTaxValue" Value="0" />
        <Field Name="UnitSellingPrice" Value="0" />
        <Field Name="UnitDiscountValue" Value="0" />
        <Field Name="ItemDescription" Value="Test Product" />
      </Record>
      <Record>
        <ExternalId>5603570</ExternalId>
        <MatchField Name="SOPOrderReturnLineID" Value="5603570" />
        <Field Name="SOPOrderReturnID" Value="5603567" />
        <Field Name="ItemCode" Value="SME MEM" />
        <Field Name="LineQuantity" Value="1" />
        <Field Name="LineTotalValue" Value="550" />
        <Field Name="LineTaxValue" Value="0" />
        <Field Name="UnitSellingPrice" Value="550" />
        <Field Name="UnitDiscountValue" Value="0" />
        <Field Name="ItemDescription" Value="SME Membership" />
      </Record>
    </RelatedRecords>
  </Record>
</Records>
```