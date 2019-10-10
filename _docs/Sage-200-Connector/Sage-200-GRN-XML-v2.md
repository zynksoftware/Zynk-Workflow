---
slug: sage-200-grn-xml-v2
title: Sage 200 GRN XML V2
---
The [Import Goods Received Notes](importing-goods-received-notes-into-sage-200) task allows you to receive specific item lines on purchase orders within Sage 200. 

This documentation applies to the **ImportGoodsReceivedNotesV2** task, available since Zynk v2.22. For the earlier version of the task, please refer to [Sage 200 GRN XML](sage-200-grn-xml).

We recommend that the Id field be populated by the unique id of the goods received note from the external system, Zynk uses this field for logging if there are issues with the import.   

Any Sage fields not documented below are not directly supported with our imports.  

Sample import file for creating a basic goods received note:

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

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a goods received note. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Header Information
The following information can be specified at the goods received note header level.

| XML Field | Sage Field | Required | Notes |
| --- | --- | --- | --- |
| Id | N/A | No | Used internally by Zynk for duplicate prevention. Set this to the ID from the source system. |
| PurchaseOrderNumber | Order No | Yes | The Sage 200 purchase order no that you would like to receive to |
| ReceiptDate | Date | No | The date that the goods were received, will be defaulted to today's date if not provided |
| ReceiptReference | Reference | Yes | The reference you would like to use for the generated goods received note |
| ReceiptNarrative | Narrative | No | |

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
    </ReceiptNote>
  </ReceiptNotes>
</Company>
```

## Line Information
The following information can be specified at the goods received note line level.

| XML Field | Sage Field | Required | Notes |
| --- | --- | --- | --- |
| Sku | Item Code  | Yes | The Sage 200 item code that you would like to receive |
| Quantity | Qty Received | Yes | The quantity of the item that you would like to receive |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <ReceiptNotes>
    <ReceiptNote>
      <GoodsNotes>
        <GoodsNote>
          <Sku>PC005</Sku>
          <Quantity>3</Quantity>
        </GoodsNote>
      </GoodsNotes>
    </ReceiptNote>
  </ReceiptNotes>
</Company>
```

## Traceable Items
If you deal with traceable (batch or serial) items in Sage 200, then you can optionally provide the traceable identification numbers to receive the goods as.

N.B. When importing the goods received note, we will first of all check that the Sage 200 item we are dealing with is set up as a traceable item. If the item is not a traceable item in Sage 200 then any batches provided will be ignored.

N.B. The sum of the quantities of all provided batches must equal the quantity on the goods note.

### Batch items
If the item on the goods received note is configured in Sage 200 as a batch item, you can specify the batch information on the goods received note according to the below mapping.

| XML Field  | Sage Field  | Required  | Notes  |
| --- | --- | --- | --- |
| IdentificationNo | Batch No | Yes | The identification number for the current batch |
| Quantity | Qty Delivered | Yes | The quantity received in the batch, must be greater than 0 |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <ReceiptNotes>
    <ReceiptNote>
      <GoodsNotes>
        <GoodsNote>
          <Batches>
            <Batch>
              <IdentificationNo>BATCH1</IdentificationNo>
              <Quantity>3</Quantity>
            </Batch>
          </Batches>
        </GoodsNote>
      </GoodsNotes>
    </ReceiptNote>
  </ReceiptNotes>
</Company>
```

### Serial items
If the item on the goods received note is configured in Sage 200 as a serial item, you can specify the serial information on the goods received note according to the below mapping.

| XML Field  | Sage Field  | Required  | Notes  |
| --- | --- | --- | --- |
| IdentificationNo | Serial No | Yes | The identification number for the current serial |
| Quantity | Qty Delivered | Yes | Must be 1 |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <ReceiptNotes>
    <ReceiptNote>
      <GoodsNotes>
        <GoodsNote>
          <Batches>
            <Batch>
              <IdentificationNo>SERIAL1</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
            <Batch>
              <IdentificationNo>SERIAL2</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
            <Batch>
              <IdentificationNo>SERIAL3</IdentificationNo>
              <Quantity>1</Quantity>
            </Batch>
          </Batches>
        </GoodsNote>
      </GoodsNotes>
    </ReceiptNote>
  </ReceiptNotes>
</Company>
```

### Batch Attributes
If you deal with traceable (batch or serial) items in Sage 200, then it is possible that the stock item is configured to use 'Sell by dates' and/or 'Use by dates' and/or other custom batch attributes configured at the product group level. 

N.B. If any attributes configured at the product group level are marked as mandatory and you try to provide these attributes in a one of the batches you are importing, then you must provide the mandatory attribute in **all** of the batches you are importing.

| XML Field  | Sage Field  | Required  | Notes  |
| --- | --- | --- | --- |
| Name | Title | No | The name of the attribute to set (should be provided as it appears within Sage) |
| Value | Value | No | The value to use for the attribute on the batch |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <ReceiptNotes>
    <ReceiptNote>
      <GoodsNotes>
        <GoodsNote>
          <Batches>
            <Batch>
              <Attributes>
                <!-- If specifying Use by or Sell by date-->
                <Attribute>
                  <Name>UseByDate</Name>
                  <!-- The following date format should be used -->
                  <Value>2016-01-21</Value>
                </Attribute>
                <Attribute>
                  <Name>SellByDate</Name>
                 <!-- The following date format should be used -->
                  <Value>2015-07-21</Value>
                </Attribute>
                <!-- If specifying custom attributes-->
                <Attribute>
                  <!-- The title should match the title in Sage exactly -->
                  <Name>ATTRIBUTE1</Name>
                  <Value>ATTRIBUTE1 VALUE</Value>
                </Attribute>
                <Attribute>
                  <Name>ATTRIBUTE2</Name>
                  <Value>ATTRIBUTE2 VALUE</Value>
                </Attribute>
              </Attributes>
            </Batch>
          </Batches>
        </GoodsNote>
      </GoodsNotes>
    </ReceiptNote>
  </ReceiptNotes>
</Company>
```

### Sage 200 Batch/Serial Number Configuration
When items are set up in Sage 200 as traceable, the following settings can be configured at the item level, these will effect how the import goods received note routine processes the records.

N.B. If the *Allow duplicate numbers* setting is disabled for the item you are receiving, the identification no you provide must be unique for that item.

N.B. If the *Batch & serial numbers must be recorded when goods are received* setting is enabled for the item you are receiving but the *Automatic number generation* setting is disabled, then you must provide the batch information on the import of the goods received note, otherwise you will receive an error and the goods received note will be rejected. 

N.B. If the *Batch & serial numbers must be recorded when goods are received* setting is enabled for the item you are receiving and the *Automatic number generatio*n setting is enabled, then the identification numbers will be generated by Sage 200 according to the automatic number generation options. The generated identification numbers and quantities will be written out to the Import Goods Received Notes success file. 

N.B.If the *Batch & serial numbers must be recorded when goods are received* setting is disabled for the item you are receiving, then if you don't provide any batch information in the XML, no batches will be assigned (even if the setting is enabled; this reflects how this works within Sage 200). 

N.B. Regardless of the *Batch & serial numbers must be recorded when goods are received* and the *Automatic number generation* settings within Sage 200, if you provide the batch information XML in the goods received note, then this will **always** be used.
