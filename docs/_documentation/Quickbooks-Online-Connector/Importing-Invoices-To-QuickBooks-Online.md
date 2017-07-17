---
slug: importing-invoices-to-quickbooks-online
redirect_from: "/article/879-uploading-invoices-to-quickbooks-online"
title: Importing Invoices To QuickBooks Online
---


This task will insert new and update existing invoices in Quickbooks Online, from an XML file. The logic surrounding inserting/updating invoices works as follows:


1. If an Id is provided for the invoice, and an invoice already exists in Quickbooks with this Id, the existing invoice will be updated.
2. If an ExternalId is provided for the invoice, and a match is found in Zynk's truth table, the existing invoice will be updated.
3. If a DocNumber is provided for the invoice, and an invoice already exists in Quickbooks with this DocNumber, the existing invoice will be updated.
4. If none of the above conditions are fulfilled, a new invoice will be created.


## Upload Invoices

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
    <ArrayOfInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfInvoice>
        <ExternalId>1</ExternalId>
        <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
          <AutoDocNumber>true</AutoDocNumber>
          <CustomerRef name="Zynk Software"></CustomerRef>
          <CurrencyRef>GBP</CurrencyRef>
          <BillAddr>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <Country>England</Country>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Line1>Zynk Software</Line1>
            <Line2>Nelson House</Line2>
            <Line3>Jesmond</Line3>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <Country>England</Country>
            <PostalCode>NE2 3AE</PostalCode>
          </ShipAddr>
          <Line>
            <LineNum>1</LineNum>
            <Description>Employee training off site</Description>
            <Amount>1000.00</Amount>
            <DetailType>SalesItemLineDetail</DetailType>
            <SalesItemLineDetail>
              <ItemRef name="Employee Training"></ItemRef>
              <UnitPrice>1000.0</UnitPrice>
              <Qty>1</Qty>
              <TaxCodeRef name="20.0% S"></TaxCodeRef>
            </SalesItemLineDetail>
          </Line>
          <SalesTermRef>3</SalesTermRef>
        </Data>
      </RecordOfInvoice>
    </ArrayOfInvoice>

```