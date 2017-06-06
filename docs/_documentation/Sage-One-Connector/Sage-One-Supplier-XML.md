---
slug: sage-one-supplier-xml
title: Sage One Supplier XML
---
Upload Suppliers allows you to create new and update existing Supplier records in Sage One. You can either provide a field in the XML and set up the task to match Supplier records based on that field, or alternatively you can provide an Id node in your XML.  

Any Sage One fields not documented below are not supported with our uploads.   

Sample upload file for creating a Supplier record in Sage One:

```xml
<?xml version="1.0"?>
<ArrayOfSupplier xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Supplier>
    <Id>SMITH01</Id>
    <Company>The Smiths</Company>
    <Name>Johnny Marr</Name>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <MainAddress>
      <Address1>Charming Man House</Address1>
      <Address2>123 Ask Road</Address2>
      <Town>Morrissey</Town>
      <County>Marrshire</County>
      <Postcode>NE29 2PQ</Postcode>
      <Country>
        <Name>United Kingdom</Name>
      </Country>
      <Email>johnny@thesmiths.co.uk</Email>
      <Telephone>0191 290 0618</Telephone>
    </MainAddress>
    <DeliveryAddress>
      <Address1>Asleep House</Address1>
      <Address2>123 Bigmouth Road</Address2>
      <Town>Morrissey</Town>
      <County>Marrshire</County>
      <Postcode>NE29 2RT</Postcode>
      <Country>
        <Name>United Kingdom</Name>
      </Country>
    </DeliveryAddress>
  </Supplier>
</ArrayOfSupplier>
```

## Company Details
The below information is in relation to the supplier details you are able to set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 1234567 | string | Optional |
| - | Id | SMITH01 | string  | Optional |
| Company / Name | Company | The Smiths | string | Required |
| Full Name | Name | Johnny Marr | string | Optional |
| Notes  | Notes  | This is a supplier record.  | string   | Optional  |

## Main Address Details
You must always provide a main address for a supplier record, however the details are optionally and dependant upon your task settings. For example, if you are matching suppliers based on their postcode you must provide a postcode.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Street 1 | Address1 | Charming House | string | Optional |
| Street 2 | Address2 | 123 Ask Street | string | Optional |
| Town / City | Town | Morrissey | string | Optional |
| State / Province | County | Marrshire | string | Optional |
| Postal Code | Postcode | NE29 2PQ | string | Optional |
| Email | Email | johnny@thesmiths.co.uk | string | Optional |
| Telephone | Telephone | 0191 290 0618 | string | Optional |
| Mobile | Mobile | 0773 863 6049 | string | Optional |

## Delivery Address Details
The below information is in relation to a delivery address on your supplier record in Sage One.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Street 1 | Address1 | Asleep House | string | Optional |
| Street 2 | Address2 | 123 Bigmouth Street | string | Optional |
| Town / City | Town | Morrissey | string | Optional |
| State / Province | County | Marrshire | string | Optional |
| Postal Code | Postcode | NE29 2RT | string | Optional |

## Delivery Address Details
The below information is in relation to a delivery address on your supplier record in Sage One.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Street 1 | Address1 | Asleep House | string | Optional |
| Street 2 | Address2 | 123 Bigmouth Street | string | Optional |
| Town / City | Town | Morrissey | string | Optional |
| State / Province | County | Marrshire | string | Optional |
| Postal Code | Postcode | NE29 2RT | string | Optional |

## Main and Delivery Address Counry Details
The below information is to setting a country on either your main or delivery addresses. You can match this value to a country in Sage One using any one of the below fields.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 218 | string | Optional |
| Country | Code | GB | string | Optional |
| Country | Name | United Kingdom | string | Optional |