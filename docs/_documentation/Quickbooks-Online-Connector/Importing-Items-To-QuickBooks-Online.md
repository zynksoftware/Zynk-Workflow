---
slug: importing-items-to-quickbooks-online
redirect_from: "/article/880-uploading-items-to-quickbooks-online"
title: Importing Items To QuickBooks Online
---


This task will insert new and update existing items in Quickbooks Online, from an XML file. The logic surrounding inserting/updating items works as follows:


1. If an Id is provided for the item, and an item already exists in Quickbooks with this Id, the existing item will be updated.
2. If an ExternalId is provided for the item, and a match is found in Zynk's truth table, the existing item will be updated.
3. If a Sku is provided for the item, and an item already exists in Quickbooks with this Sku, the existing item will be updated.
4. If a Name is provided for the item, and an item already exists in Quickbooks with this Name, the existing item will be updated.
5. If none of the above conditions are fulfilled, a new item will be created.


## Upload Items

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
    <ArrayOfItem xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfItem>
        <ExternalId>PROD-1</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Name>Product 1</Name>
          <Sku>PROD-1</Sku>
          <Type>NonInventory</Type>
          <IncomeAccountRef name="Sales of Product Income">66</IncomeAccountRef>
          <SalesTaxCodeRef name="20.0% S"></SalesTaxCodeRef>
         <PurchaseTaxCodeRef name="20.0% S">
          </PurchaseTaxCodeRef>
        </Data>
      </RecordOfItem>
    </ArrayOfItem>

```