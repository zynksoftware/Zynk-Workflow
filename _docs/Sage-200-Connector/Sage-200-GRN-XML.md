---
slug: sage-200-grn-xml
title: Sage 200 GRN XML
---
Import Goods Received Notes allows you to receive specific item lines on purchase orders within Sage 200.  We recommend that the Id field be populated by the unique id of the goods received note from the external system, Zynk uses this field for logging if there are issues with the import.   

Any Sage fields not documented below are not directly supported with our imports.  

Sample import file for creating a basic goods received note

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

In the following section, the mapping between the XML goods note object model and the Sage 200 goods received note fields are described.

| XML Field  | Sage Field  | Required  | Notes  |
| --- | --- | --- | --- |
| Id | N/A | No | Used internally in Zynk |
| AccountReference | A/C ref | Yes | The Sage 200 supplier account reference that the purchase order is assigned to in Sage  |
| Type | N/A | Yes | Must be GoodsReceivedNote |
| OrderNumber | Order No | Yes | The Sage 200 purchase order no that you would like to receive to |
| Reference | Reference | Yes | The reference you would like to use for the generated goods received note |
| Details | Narrative | No |
| Date | Date | No | The date that the goods were received, will be defaulted to today's date if not provided |
| Sku | Item Code  | Yes | The Sage 200 item code that you would like to receive |
| Quantity | Qty Received  | Yes | The quantity of the item that you would like to receive |

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a goods received note. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

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
  <GoodsNotes>
    <GoodsNote>
      <Batches>
        <Batch>
          <IdentificationNo>BATCH1</IdentificationNo>
          <Quantity>1</Quantity>
        </Batch>
        <Batch>
          <IdentificationNo>BATCH2</IdentificationNo>
          <Quantity>2</Quantity>
        </Batch>
      </Batches>
    </GoodsNote>
  </GoodsNotes>
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
</Company>
```


## Batch Attributes
If you deal with traceable (batch or serial) items in Sage 200, then it is possible that the stock item is configured to use 'Sell by dates' and/or 'Use by dates' and/or other custom batch attributes configured at the product group level. 

N.B. If any attributes configured at the product group level are marked as mandatory and you try to provide these attributes in a one of the batches you are importing, then you must provide the mandatory attribute in **all** of the batches you are importing.

| XML Field  | Sage Field  | Required  | Notes  |
| --- | --- | --- | --- |
| Name | Title | No | The name of the attribute to set (should be provided as it appears within Sage) |
| Value | Value | No | The value to use for the attribute on the batch |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
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
</Company>
```

## Sage 200 Batch/Serial Number Configuration
When items are set up in Sage 200 as traceable, the following settings can be configured at the item level, these will effect how the import goods received note routine processes the records.

N.B. If the *Allow duplicate numbers* setting is disabled for the item you are receiving, the identification no you provide must be unique for that item.

N.B. If the *Batch & serial numbers must be recorded when goods are received* setting is enabled for the item you are receiving but the *Automatic number generation* setting is disabled, then you must provide the batch information on the import of the goods received note, otherwise you will receive an error and the goods received note will be rejected. 

N.B. If the *Batch & serial numbers must be recorded when goods are received* setting is enabled for the item you are receiving and the *Automatic number generatio*n setting is enabled, then the identification numbers will be generated by Sage 200 according to the automatic number generation options. The generated identification numbers and quantities will be written out to the Import Goods Received Notes success file. 

N.B.If the *Batch & serial numbers must be recorded when goods are received* setting is disabled for the item you are receiving, then if you don't provide any batch information in the XML, no batches will be assigned (even if the setting is enabled; this reflects how this works within Sage 200). 

N.B. Regardless of the *Batch & serial numbers must be recorded when goods are received* and the *Automatic number generation* settings within Sage 200, if you provide the batch information XML in the goods received note, then this will **always** be used.