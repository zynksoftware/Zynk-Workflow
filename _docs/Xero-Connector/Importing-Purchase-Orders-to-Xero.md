---
slug: importing-purchase-orders-to-xero
redirect_from: "/article/962-uploading-purchase-orders-to-xero"
title: Importing Purchase Orders to Xero
---

This task will insert or update purchase orders in Xero from an XML file.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Fail File
_Required_  
The file to save failed record imports to.

### Input File
_Required_  
The file containing the bank transactions to upload to Xero.

### Success File
_Required_  
The file to save successful record imports to.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once, based on the ExternalId provided in the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples

A sample input file containing a purchase order is shown below. More detailed information about each field can be found in our [API Documentation](xero-purchase-order-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroPurchaseOrder>
  <XeroPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>3452</ExternalId>
    <Date>2017-01-04T00:00:00</Date>
    <Number>PO-0003</Number>
    <DeliveryDate>2017-01-11T00:00:00</DeliveryDate>
    <DeliveryAddress>Newcastle Enterprise Centres
6 Charlotte Square
Newcastle upon Tyne
Tyne and Wear
NE1 4XF
United Kingdom</DeliveryAddress>
    <AttentionTo>Bob</AttentionTo>
    <Telephone>0191 303 7279</Telephone>
    <DeliveryInstructions>Leave by the gate</DeliveryInstructions>
    <Reference>Test 123</Reference>
    <Contact>
      <Id>20435ce7-50b7-4a86-926a-8248778e1dcb</Id>
    </Contact>
    <Status>Submitted</Status>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <LineItems>
      <LineItem>
        <Quantity>1.0000</Quantity>
        <UnitAmount>15.0000</UnitAmount>
        <AccountCode>5000</AccountCode>
        <ItemCode>BOARD001</ItemCode>
        <TaxType>INPUT2</TaxType>
        <TaxAmount>3.00</TaxAmount>
        <LineAmount>15.00</LineAmount>
      </LineItem>
      <LineItem>
        <Quantity>5.0000</Quantity>
        <UnitAmount>1.5000</UnitAmount>
        <AccountCode>5000</AccountCode>
        <ItemCode>BOOKS002</ItemCode>
        <TaxType>INPUT2</TaxType>
        <TaxAmount>1.50</TaxAmount>
        <LineAmount>7.50</LineAmount>
      </LineItem>
    </LineItems>
  </XeroPurchaseOrder>
</ArrayOfXeroPurchaseOrder>
```