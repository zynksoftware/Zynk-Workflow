---
slug: importing-goods-received-notes-into-sage-200
redirect_from: "/article/438-import-goods-received-note"
title: Importing Goods Received Notes into Sage 200
---
This task will import new goods received notes in Zynk XML format into Sage 200. This task only supports receiving goods on purchase orders, to receive goods on a sales return, use the [Update Purchase Orders](updating-purchase-orders-in-sage-200) task instead. 

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed goods notes in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported goods notes in Zynk XML format.

### Auto Invoice
_Required_  
Set to 'True' to automatically invoice received purchase orders items.

### Prevent Duplicates
_Required_  
Set to 'True' to check whether the goods note Id supplied in the  input XML file has already been imported, and if so skip the despatch  note.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a goods note is shown below. This applies to workflows created in v2.22 of Zynk and above (using the ImportGoodsReceivedNotesV2 task). See our [Sage 200 GRN XML](sage-200-grn-xml) for more details on the Zynk XML Goods Note format for Sage 200.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <ReceiptNotes>
    <ReceiptNote>
      <Id>123456</Id>
      <PurchaseOrderNumber>38</PurchaseOrderNumber>
      <ReceiptDate>2012-10-03T10:00:00</ReceiptDate>
      <ReceiptReference>PROJ006</ReceiptReference>
      <ReceiptNarrative>Goods received</ReceiptNarrative>
      <GoodsNotes>
        <GoodsNote>
          <Sku>PC005</Sku>
          <Quantity>3</Quantity>
          <Location>HOME</Location>
          <Bin>B001</Bin>
          <Batches>
            <Batch>
              <IdentificationNo>0000000001</IdentificationNo>
              <Quantity>3</Quantity>
            </Batch>
          </Batches>
        </GoodsNote>
      </GoodsNotes>
    </ReceiptNote>
  </ReceiptNotes>
</Company>
```

For workflows created in versions of Zynk prior to v2.22 (using the ImportGoodsReceivedNotes task), the format is as follows.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <GoodsNotes>
    <GoodsNote>
      <Id>123456</Id>
      <AccountReference>MCN001</AccountReference>
      <Type>GoodsReceivedNote</Type>
      <OrderNumber>38</OrderNumber>
      <Reference>PROJ006</Reference>
      <Date>2012-10-03T10:00:00</Date>
      <Sku>PC005</Sku>
      <Quantity>3</Quantity>
    </GoodsNote>
  </GoodsNotes>
</Company>
```
