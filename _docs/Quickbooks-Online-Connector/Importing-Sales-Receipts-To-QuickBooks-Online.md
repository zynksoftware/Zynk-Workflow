---
slug: importing-sales-receipts-to-quickbooks-online
redirect_from: "/article/883-uploading-sales-receipts-to-quickbooks-online"
title: Importing Sales Receipts To QuickBooks Online
---


This task will insert new and update existing sales receipts in Quickbooks Online, from an XML file. The logic surrounding inserting/updating sales receipts works as follows:


1. If an Id is provided for the sales receipt, and a sales receipt already exists in Quickbooks with this Id, the existing sales receipt will be updated.
2. If an ExternalId is provided for the sales receipt, and a match is found in Zynk's truth table, the existing sales receipt will be updated.
3. If a DocNumber is provided for the sales receipt, and a sales receipt already exists in Quickbooks with this DocNumber, the existing sales receipt will be updated.
4. If none of the above conditions are fulfilled, a new sales receipt will be created.


## Upload Sales Receipts

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
    <ArrayOfSalesReceipt xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfSalesReceipt>
        <ExternalId>114</ExternalId>
        <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
          <AutoDocNumber>true</AutoDocNumber>
          <CurrencyRef name="United States Dollar">GBP</CurrencyRef>
          <PrivateNote>this is a memo</PrivateNote>
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
            <Id>1</Id>
            <LineNum>1</LineNum>
            <Description>Catering -- food &amp;amp; beverage</Description>
            <Amount>50</Amount>
            <DetailType>SalesItemLineDetail</DetailType>
            <SalesItemLineDetail>
              <ItemRef name="Catering"></ItemRef>
              <UnitPrice>50</UnitPrice>
              <Qty>1</Qty>
              <TaxCodeRef name="20.0% S"></TaxCodeRef>
            </SalesItemLineDetail>
          </Line>
          <CustomerRef name="Zynk Software"></CustomerRef>
          <CustomerMemo>this is a message</CustomerMemo>
          <BillEmail>
            <Address>support@zynk.com</Address>
          </BillEmail>
          <PaymentMethodRef name="Cash"></PaymentMethodRef>
          <PaymentRefNum>abc123</PaymentRefNum>
          <DepositToAccountRef name="Current"></DepositToAccountRef>
        </Data>
      </RecordOfSalesReceipt>
    </ArrayOfSalesReceipt>

```