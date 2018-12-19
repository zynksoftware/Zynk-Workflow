---
slug: importing-despatch-notes-into-sage-50-uk
redirect_from: "/article/411-importing-despatch-notes-into-sage-50-uk"
title: Importing Despatch Notes into Sage 50 UK
---
This task will import despatch notes in to your Sage 50 Company that are supplied in Zynk XML format. You can either specify particular items and quantities on an order to despatch, or just specify the order and all allocated stock will be despatched.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Auto Allocate Stock
_Required_  
Set to true to automatically allocate stock to the sales orders if there is not enough stock already allocated. Only the minimum amount required for the despatch will be allocated. 

### Auto Post Invoices
_Required_  
Set to true to automatically post the generated invoices to the ledger. This will update the customer's account balance to reflect the new invoice.

### Payment Type
_Required_  
The default payment type. If a payment type is not specified in the input XML file, the payment type selected in this setting will be used. It can be set to either Sales Receipt or Sales Receipt on Account.

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
Sample input file, for full documentation and samples see [Sage 50 UK GDN XML](sage-50-uk-gdn-xml):  

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <DespatchNotes>
    <DespatchNote>
      <Id>1</Id>
      <OrderNumber>31</OrderNumber>
      <GoodsNotes>
        <GoodsNote>
          <Id>210</Id>
          <Type>GoodsDespatchedNote</Type>
          <Date>2013-03-11T14:13:13</Date>
          <Sku>PC003</Sku>
          <Quantity>1</Quantity>
        </GoodsNote>
        <GoodsNote>
          <Id>211</Id>
          <Type>GoodsDespatchedNote</Type>
          <Date>2013-03-11T14:13:13</Date>
          <Sku>MEM005</Sku>
          <Quantity>1</Quantity>
        </GoodsNote>
      </GoodsNotes>
    </DespatchNote>
  </DespatchNotes>
</Company>
```