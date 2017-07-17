---
slug: importing-purchase-orders-to-quickbooks-online
redirect_from: "/article/882-uploading-purchase-orders-to-quickbooks-online"
title: Importing Purchase Orders To QuickBooks Online
---


This task will insert new and update existing purchase orders in Quickbooks Online, from an XML file. The logic surrounding inserting/updating purchase orders works as follows:


1. If an Id is provided for the purchase order, and a purchase order already exists in Quickbooks with this Id, the existing purchase order will be updated.
2. If an ExternalId is provided for the purchase order, and a match is found in Zynk's truth table, the existing purchase order will be updated.
3. If a DocNumber is provided for the purchase order, and a purchase order already exists in Quickbooks with this DocNumber, the existing purchase order will be updated.
4. If none of the above conditions are fulfilled, a new purchase order will be created.


## Upload Purchase Orders

### Connection
_Required_  
Select a connection to the Quickbooks Online company you want to use. See [Connecting to QuickBooks Online](connecting-to-quickbooks-online)

### Fail File 
_Required_  
The XML file to output any records to which fail to import to Quickbooks.

### Input File 
_Required_  
The XML file containing the records to import to Quickbooks. See below for a sample input file.

### Success File 
_Required_  
The XML file to output any records to which are successfully imported to Quickbooks.

### Prevent Reprocessing
_Required_  
Set to true to prevent the same records being imported to Quickbooks more than once. Only works on records where an ExternalId is provided in the input file.


## Examples


Sample input file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfPurchaseOrder>
        <ExternalId>12313</ExternalId>
        <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
          <TxnDate>2016-07-07T00:00:00</TxnDate>
          <VendorRef name="Zynk Software Vendor"></VendorRef>
          <CurrencyRef>GBP</CurrencyRef>
          <Line>
            <Id>1</Id>
            <Description>Water bottles -- generic</Description>
            <Amount>6617.17</Amount>
            <DetailType>ItemBasedExpenseLineDetail</DetailType>
            <ItemBasedExpenseLineDetail>
              <ItemRef name="Water Bottles"></ItemRef>
              <UnitPrice>66.1717023</UnitPrice>
              <Qty>10</Qty>
              <TaxCodeRef name="20.0% S"></TaxCodeRef>
              <CustomerRef name="Zynk Software"></CustomerRef>
              <BillableStatus>NotBillable</BillableStatus>
            </ItemBasedExpenseLineDetail>
          </Line>
          <APAccountRef name="Creditors"></APAccountRef>
          <BillAddr>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <Country>England</Country>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <Country>England</Country>
            <PostalCode>NE2 3AE</PostalCode>
          </ShipAddr>
        </Data>
      </RecordOfPurchaseOrder>
    </ArrayOfPurchaseOrder>

```