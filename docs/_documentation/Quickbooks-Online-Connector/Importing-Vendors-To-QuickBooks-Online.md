---
slug: importing-vendors-to-quickbooks-online
redirect_from: "/article/884-uploading-vendors-to-quickbooks-online"
title: Importing Vendors To QuickBooks Online
---


This task will insert new and update existing vendors in Quickbooks Online, from an XML file. The logic surrounding inserting/updating vendors works as follows:


1. If an Id is provided for the vendor, and a vendor already exists in Quickbooks with this Id, the existing vendor will be updated.
2. If an ExternalId is provided for the vendor, and a match is found in Zynk's truth table, the existing vendor will be updated.
3. If a DisplayName is provided for the vendor, and a vendor already exists in Quickbooks with this DisplayName, the existing vendor will be updated.
4. If none of the above conditions are fulfilled, a new vendor will be created.


## Upload Vendors

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
    <ArrayOfVendor xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfVendor>
        <ExternalId>467</ExternalId>
        <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
          <CompanyName>Zynk Software</CompanyName>
          <DisplayName>Zynk Software Vendor</DisplayName>
          <Active>true</Active>
          <BillAddr>
            <Id>24</Id>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <Vendor1099>false</Vendor1099>
          <CurrencyRef>GBP</CurrencyRef>
        </Data>
      </RecordOfVendor>
    </ArrayOfVendor>

```