---
slug: importing-goods-received-notes-into-sage-50-uk
redirect_from: "/article/412-importing-goods-received-notes-into-sage-50-uk"
title: Importing Goods Received Notes into Sage 50 UK
---
This task will import goods received notes to Sage 50 that are supplied in Zynk XML format. The import will check that the Account Reference and the Order Number match a valid purchase order in Sage, and that the item is correct for the order. During the import the status of the purchase order will be updated to either PART or COMPLETE depending on what was provided in the XML. The import will not update the purchase order to create the invoice. If an invalid Goods Note Type is used, the goods note will be marked as failed.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Prevent Duplicates
_Required_  
Set this to 'True' to check whether the record Id supplied in the input XML file has already been imported, and if so skip the record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK GRN XML](sage-50-uk-grn-xml):  

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <GoodsNotes>
    <GoodsNote>
      <Id>123</Id>
      <AccountReference>MCN001</AccountReference>
      <Type>GoodsReceivedNote</Type>
      <OrderNumber>38</OrderNumber>
      <Reference>PROJ006</Reference>
      <Date>2012-10-03T10:00:00</Date>
      <Sku>PC005</Sku>
      <Quantity>1.00</Quantity>
      <CostPrice>780.41</CostPrice>
    </GoodsNote>
  </GoodsNotes>
</Company>
```