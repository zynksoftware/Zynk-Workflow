---
slug: sage-50-uk-grn-xml
title: Sage 50 UK GRN XML
---
The Import Goods Received Note task allows you to receive items on purchase orders already in Sage.  Note that for an order / order item to be received it must be in the correct state in Sage - the order must not be fully received or fully cancelled, and at least part allocated.  The quantity for the order item must not exceed the quantity allocated / ready to receive.

The status of the order in Sage will be updated depending on the current state, and result of the import.  The status will either not be updated, updated to complete or updated to part received.

Any Sage fields not documented below are not supported with our imports.  Examples of where in the XML the fields should appear are shown in the samples below.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| N/A | Id | 123 | int | - | Optional |  
| A/C Reference | AccountReference | MCN001 | string | 8 | Required |  
| N/A | Type | GoodsReceivedNote | string | - | Required |  
| Order No. | OrderNumber | 38 | int | - | Required |  
| Supplier GRN | Reference | PROJ006 | string | 20 | Required |  
| GRN Date | Date | 2012-10-03T10:00:00 | datetime | - | Required |  
| Product Code | Sku | PC005 | string | 30 | Required |  
| Quantity | Quantity | 1.00 | double | - | Required |  
| Product Cost Price | CostPrice | 780.41 | double | - | Optional |  

Sample import file for receiving an item on an order:
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

## Grouping
Individual goods notes can be grouped together to form a single Goods Received Note in Sage, with multiple item lines. Consecutive goods notes in the XML will be grouped where the following fields contain the same value on each goods note:

* OrderNumber
* Date
* Reference