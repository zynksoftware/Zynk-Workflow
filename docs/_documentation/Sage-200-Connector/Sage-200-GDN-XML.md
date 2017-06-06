---
slug: sage-200-gdn-xml
title: Sage 200 GDN XML
---
The Import Goods Despatched Notes task allows you to despatch items on sales orders in Sage 200. The task supports despatching specific items or all stock allocated to the order.  

Any fields not documented below are not supported with our imports.  

Examples of where in the XML the fields should appear are shown in the samples below. Sample import file for despatching items on an order:

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

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a goods despatched note. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.  

## Despatch Note  
The following information is required at the despatch note level, to identify which sales order to despatch goods for.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Order No | OrderNumber | 0000001579 | string | 20 | Required, if a CustomerOrderNumber has not been provided |
| Customer Order No | CustomerOrderNumber | 02-139483-383 | string | 30 | Required, if an OrderNumber has not been provided |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <DespatchNotes>
    <DespatchNote>
      <OrderNumber>0000001579</OrderNumber>
      <CustomerOrderNumber>02-139483-383</CustomerOrderNumber>
    </DespatchNote>
  </DespatchNotes>
</Company>
```

## Goods Note  
The following information is required at the goods note level, to identify which items to despatch, and the quantity. Alternatively, all items which are ready for despatch can be desptached automatically, by not providing a GoodsNotes collection in the XML.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| - | Type* | GoodsDespatchedNote | enum | - | Required |
| Req'd Date | Date* | 2014-01-01T00:00:00 | date | - | Optional |
| Item Code | Sku | PROD001 | string | 30 | Required |
| Qty to Despatch | Quantity | 3 | decimal | - | Required |

*   Type* - The type must be set to 'GoodsDespatchedNote'
*   Date* - If the date is not provided, it will default to the current date

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <DespatchNotes>
    <DespatchNote>
      <GoodsNotes>
        <GoodsNote>
          <Type>GoodsDespatchedNote</Type>
          <Date>2014-01-01T00:00:00</Date>
          <Sku>PROD001</Sku>
          <Quantity>3</Quantity>
        </GoodsNote>
      </GoodsNotes>
    </DespatchNote>
  </DespatchNotes>
</Company>
```