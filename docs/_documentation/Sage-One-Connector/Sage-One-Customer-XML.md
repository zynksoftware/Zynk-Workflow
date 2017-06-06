---
slug: sage-one-customer-xml
title: Sage One Customer XML
---
Upload Customers allows you to create new and update existing customer records in Sage One. You can either provide a field in the XML and set up the task to match customer records based on that field, or alternatively you can provide an Id node in your XML.  

Any Sage One fields not documented below are not supported with our uploads.   

Sample upload file for creating a customer record in Sage One:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer>
    <Id>ZIGG01</Id>
    <Company>Ziggy Stardust and the Spiders from Mars</Company>
    <Name>Ziggy Stardust</Name>
    <Notes>Testing, testing, 1, 2, 3...</Notes>
    <MainAddress>
      <Address1>Starman House</Address1>
      <Address2>123 Ziggy Street</Address2>
      <Town>Bowietown</Town>
      <County>Bowieshire</County>
      <Postcode>NE1 2DE</Postcode>
      <Country>
        <Code>GB</Code>
      </Country>
      <Email>z.stardust@thespidersfrommars.com</Email>
      <Telephone>0191 290 0614</Telephone>
    </MainAddress>
    <DeliveryAddress>
      <Address1>Spider House</Address1>
      <Address2>123 Mars Street</Address2>
      <Town>Bowietown</Town>
      <County>Bowieshire</County>
      <Postcode>NE5 6DE</Postcode>
      <Country>
        <Code>GB</Code>
      </Country>
    </DeliveryAddress>
  </Customer>
</ArrayOfCustomer>
```

## Company Details
The below information is in relation to the customer details you are able to set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 1234567 | string | Optional |
| - | Id | ZIGG01 | string  | Optional |
| Company / Name | Company | Ziggy Stardust and the Spiders from Mars | string | Required |
| Full Name | Name | Ziggy Stardust | string | Optional |
| Notes  | Notes  | This is a customer record.  | string   | Optional  |

## Main Address Details
You must always provide a main address for a customer record, however the details are optionally and dependant upon your task settings. For example, if you are matching customers based on their postcode you must provide a postcode.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Street 1 | Address1 | Starman House | string | Optional |
| Street 2 | Address2 | 123 Ziggy Street | string | Optional |
| Town / City | Town | Bowietown | string | Optional |
| State / Province | County | Bowieshire | string | Optional |
| Postal Code | Postcode | NE1 2DE | string | Optional |
| Email | Email | z.stardust@spidersfrommars.com | string | Optional |
| Telephone | Telephone | 0191 290 0617 | string | Optional |
| Mobile | Mobile | 0773 863 6049 | string | Optional |

## Delivery Address Details
The below information is in relation to a delivery address on your customer record in Sage One.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| Street 1 | Address1 | Starman House | string | Optional |
| Street 2 | Address2 | 123 Ziggy Street | string | Optional |
| Town / City | Town | Bowietown | string | Optional |
| State / Province | County | Bowieshire | string | Optional |
| Postal Code | Postcode | NE1 2DE | string | Optional |

## Main and Delivery Address Country Details
The below information is to setting a country on either your main or delivery addresses. You can match this value to a country in Sage One using any one of the below fields.

| Sage Field | XML Field | Example | Field Type | Input |
| --- | --- | --- | --- | --- |
| - | SageOneRecordId | 218 | string | Optional |
| Country | Code | GB | string | Optional |
| Country | Name | United Kingdom | string | Optional |