---
slug: importing-customers-to-quickbooks-online
redirect_from: "/article/878-uploading-customers-to-quickbooks-online"
title: Importing Customers To QuickBooks Online
---


This task will insert new and update existing customers in Quickbooks Online, from an XML file. The logic surrounding inserting/updating customers works as follows:


1. If an Id is provided for the customer, and a customer already exists in Quickbooks with this Id, the existing customer will be updated.
2. If an ExternalId is provided for the customer, and a match is found in Zynk's truth table, the existing customer will be updated.
3. If a DisplayName is provided for the customer, and a customer already exists in Quickbooks with this DisplayName, the existing customer will be updated.
4. If none of the above conditions are fulfilled, a new customer will be created.


## Upload Customers

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
    <ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfCustomer>
        <ExternalId>6108</ExternalId>
        <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
          <FullyQualifiedName>Zynk Software</FullyQualifiedName>
          <CompanyName>Zynk Software</CompanyName>
          <DisplayName>Zynk Software</DisplayName>
          <PrintOnCheckName>Zynk Software</PrintOnCheckName>
          <Active>true</Active>
          <PrimaryEmailAddr>
            <Address>support@zynk.com</Address>
          </PrimaryEmailAddr>
          <DefaultTaxCodeRef name="20.0% S"></DefaultTaxCodeRef>
          <Taxable>false</Taxable>
          <BillAddr>
            <Id>69</Id>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Id>69</Id>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </ShipAddr>
          <Job>false</Job>
          <BillWithParent>false</BillWithParent>
          <CurrencyRef>GBP</CurrencyRef>
          <PreferredDeliveryMethod>None</PreferredDeliveryMethod>
        </Data>
      </RecordOfCustomer>
    </ArrayOfCustomer>

```