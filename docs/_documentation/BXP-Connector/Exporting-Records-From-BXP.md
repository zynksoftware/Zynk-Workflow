---
slug: exporting-records-from-bxp
redirect_from: "/article/972-downloading-records-from-bxp"
title: Exporting Records From BXP
---
This task will export records from BXP and write them to an XML file.

## Download Records
### Connection 
_Required_  
The connection to use. See [Connecting to BXP](connecting-to-bxp).

### Export Settings -> Date Modified
_Required_  
When exporting modified records, only records modified after this date will be exported. This date will update automatically when the task runs.

### Export Settings -> Export Modified or All Records
_Required_  
Choose whether to export all records, or only those modified since the task last ran. Note that the 'Modified' setting will also export any new records.

### Field Settings -> Fields Type
_Required_  
Choose whether to export all fields, or only selected ones. Use the 'Selected Fields' setting to specify the fields to export.

### Field Settings -> Select Fields
_Optional_  
Allows you to specify specific fields to include in the export. Simply enter the field name for each field to export on a separate line. Please note that this setting only takes effect when the 'Fields Type' setting is set to 'Selected'.

### Form ID
_Required_  
Enter the ID of the form to export records from.

### Related Form Settings -> Field Settings
_Dependant_  
Select which fields to export from the related form. Refer to the Field Settings as described above for more detail.  Required when exporting related records from another form.

### Related Form Settings -> Form ID
_Dependant_  
Enter the ID of the form to download related records from. Required when exporting related records from another form.	

### Related Form Settings -> Match Field
_Dependant_  
Enter the name of the field from this form to use to match related records on. Required when exporting related records from another form.

### Related Form Settings -> Parent Match Field
_Dependant_  
Enter the name of the field from the parent form to use to match related records on. Required when exporting related records from another form.

### Where 
_Optional_  
Enter an SQL where clause to filter the records returned. Please note that use must use the BXP DB column names (e.g. strCDA\_123\_field\_0\_1) in the where clause, not the mapped field names.

### Output File
_Required_  
The file to save records to.

### Zynk Settings
See [Common Task Settings](common-task-settings)cords to.

## Examples
A sample output file is shown below, containing a single record downloaded from form ID 123, with a pair of related records from form ID 124.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Records xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" FormId="123">
  <Record>
    <ExternalId>5603567</ExternalId>
    <Field Name="Id" Value="4567" />
    <Field Name="Last user ID" Value="John Smith" />
    <Field Name="SOPOrderReturnID" Value="5603567" />
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
        <Field Name="Id" Value="7675" />
        <Field Name="Last user ID" Value="John Smith" />
        <Field Name="SOPOrderReturnLineID" Value="5603569" />
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
        <Field Name="Id" Value="7676" />
        <Field Name="Last user ID" Value="John Smith" />
        <Field Name="SOPOrderReturnLineID" Value="5603570" />
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