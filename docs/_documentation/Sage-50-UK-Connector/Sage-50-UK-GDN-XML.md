---
slug: sage-50-uk-gdn-xml
title: Sage 50 UK GDN XML
---
The Import Despatch Note task allows you to despatch sales orders that are already in Sage.  Note that for an order to be despatched it must be allocated (or partially allocated).  The task can either despatch all stock allocated to the orders specified, or only despatch specific quantities on specific items.  The output of the task will be a collection of goods notes detailing the items and quantities that have been despatched.

Any Sage fields not documented below are not supported with our imports.  Examples of where in the XML the fields should appear are shown in the samples below.

## Despatching All Items
The following fields are used when despatching all allocated items on an order:

| Sage Field | XML Field  |  Example | Field Type  |  Field Length | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id  | 1  | int | -  | Optional  |
| Order No. | OrderNumber  | 31  | int | -  | Required (if CustomerOrderNumber not provided)  |
| Customer Order No. | CustomerOrderNumber  | 02-139483-383 | string | 60 | Required (if OrderNumber not provided) |

*Support for CustomerOrderNumber added into Zynk version 1.6.8*

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <DespatchNotes>
    <DespatchNote>
      <Id>1</Id>
      <OrderNumber>31</OrderNumber>
    </DespatchNote>
    <DespatchNote>
      <Id>2</Id>
      <CustomerOrderNumber>02-139483-383</CustomerOrderNumber>
    </DespatchNote>
  </DespatchNotes>
</Company>
```

Sample output file after despatching an order

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <DespatchNotes>
    <DespatchNote>
      <Id>1</Id>
      <OrderNumber>31</OrderNumber>
      <CustomerOrderNumber>02-139483-383</CustomerOrderNumber>
      <GoodsNotes>
        <GoodsNote>
          <Id>210</Id>
          <AccountReference>BBS001</AccountReference>
          <Type>GoodsDespatchedNote</Type>
          <OrderNumber>31</OrderNumber>
          <Date>2013-03-11T14:13:13.6804579+00:00</Date>
          <Sku>PC003</Sku>
          <Quantity>4</Quantity>
        </GoodsNote>
        <GoodsNote>
          <Id>211</Id>
          <AccountReference>BBS001</AccountReference>
          <Type>GoodsDespatchedNote</Type>
          <OrderNumber>31</OrderNumber>
          <Date>2013-03-11T14:13:13.7214602+00:00</Date>
          <Sku>MEM005</Sku>
          <Quantity>5</Quantity>
        </GoodsNote>
      </GoodsNotes>
    </DespatchNote>
  </DespatchNotes>
</Company>
```

## Despatching Selected Items
A collection of GoodsNotes is required in addition to the fields above when despatching selected items on an order.

| Sage Field | XML Field  |  Example | Field Type  |  Field Length | Input  |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 210 | int | -  | Optional  |
| N/A | Type\* | GoodsDespatchedNote  | enum  | -  | Required  |
| Date Despatched  | Date\* | 2013-03-11T14:13:13 | dateTime | - | Optional |
| Product Code  | Sku | PC003 | string | 30 | Required |
| This Despatch  | Quantity | 1 | double | - | Required |

* Type* - Must be set to GoodsDespatchedNote
* Date* - Will default to the current date if not provided

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