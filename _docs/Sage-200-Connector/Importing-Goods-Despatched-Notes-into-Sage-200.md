---
slug: importing-goods-despatched-notes-into-sage-200
redirect_from: "/article/437-importing-goods-despatched-notes-into-sage-200"
title: Importing Goods Despatched Notes into Sage 200
---
This task will import new despatch notes in Zynk XML format into Sage 200 as goods despatched notes. To amend existing despatches, use the [Update Sales Orders](updating-sales-orders-in-sage-200) task instead.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed despatch notes in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported despatch notes in Zynk XML format.

### Auto Allocate Stock
_Required_  
Set to 'True' to automatically allocate stock to the sales order if there isn't already enough stock allocated for the despatch

### Prevent Duplicates
_Required_  
Set to 'True' to check whether the despatch note Id supplied in the  input XML file has already been imported, and if so skip the despatch  note.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a despatch note is shown below. See our [Sage 200 GDN XML](sage-200-gdn-xml) for more details on the Zynk XML Despatch Note format for Sage 200.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <DespatchNotes>
    <DespatchNote>
      <OrderNumber>0000001579</OrderNumber>
      <GoodsNotes>
        <GoodsNote>
          <Type>GoodsDespatchedNote</Type>
          <Date>2014-01-01T00:00:00</Date>
          <Sku>PROD001</Sku>
          <Quantity>3</Quantity>
        </GoodsNote>
        <GoodsNote>
          <Type>GoodsDespatchedNote</Type>
          <Date>2014-01-01T00:00:00</Date>
          <Sku>PROD002</Sku>
          <Quantity>1</Quantity>
        </GoodsNote>
      </GoodsNotes>
    </DespatchNote>
  </DespatchNotes>
</Company>
```