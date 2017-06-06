---
slug: quickbooks-online-customer-xml
title: Quickbooks Online Customer XML
---
The Upload Customers task allows you to create and update customers in QuickBooks. Any fields not documented below are not currently supported by our upload.

Sample import file for creating a basic customer:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCustomer>
    <Data domain="QBO" xmlns="http://schema.intuit.com/finance/v3">
      <DisplayName>Zynk Software</DisplayName>
    </Data>
  </RecordOfCustomer>
</ArrayOfCustomer>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a customer. The whole structure from the root element down is shown in the samples below as a reference of where elements should appear in the object model.

## Customer Details

|  XML Field | QuickBooks Field  | Example | Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 1234 | integer | - | Optional | Used for matching to existing customers. |
| ExternalId | - | 6492 | string | 255 | Optional | Used for matching to existing customers. The value provided will be stored in Zynk's truth table, and used to lookup the Id of the customer. |
| DisplayName | Display Name As | Zynk Software | string | 21 | Required | Used for matching to existing customers. Must not contain a colon ':' character. |
| Title | Title | Mr | string | - | Optional |
| GivenName | First Name | John | string | - | Optional | Must not contain a colon ':' character. |
| MiddleName | Middle Name | Neville | string | - | Optional | Must not contain a colon ':' character. |
| FamilyName | Last Name | Smith | string | - | Optional | Must not contain a colon ':' character. |
| Suffix | Suffix | BSc | string | - | Optional |
| CompanyName | Company | Zynk Software | string | 4000 | Optional |
| PrimaryEmailAddr > Address | Email | support@zynk.com | string | 1000 | Optional |
| PrimaryPhone > FreeFormNumber | Phone | 0191 123 4567 | string | 21 | Optional |
| Mobile > FreeFormNumber | Mobile | 07123456789 | string | 21 | Optional |
| Fax > FreeFormNumber | Fax | 0191 123 4567 | string | 21 | Optional |
| AlternatePhone > FreeFormNumber | Other | 0191 123 4567 | string | 21 | Optional |
| WebAddr > URI | Website | www.zynk.com | string | 1000 | Optional |
| ParentRef | Parent Customer | 1 | integer | - | Optional | If you don't know the customer ID, you can specify their display name using the name attribute, and the task will perform a lookup. |
| BillWithParent | Bill With Parent | true | boolean | -| Optional | Defaults to false if not specified. Can only be set if the customer is a sub-customer. |
| BillAddr > Line 1 | Billing Address | Zynk Software | string | 500 | Optional |
| BillAddr > Line 2 | Billing Address | Nelson House | string | 500 | Optional |
| BillAddr > Line 3 | Billing Address | Jesmond | string | 500 | Optional |
| BillAddr > Line 4 | Billing Address | string | 500 | Optional |
| BillAddr > Line 5 | Billing Address | string | 500 | Optional |
| BillAddr > City | City/Town | Newcastle | string | 255 | Optional |
| BillAddr > Country | Country | England | string | 255 | Optional |
| BillAddr > CountrySubDivisionCode | Region | Tyne & Wear | string | 255 | Optional |
| BillAddr > PostalCode | Postcode | NE2 3AE | string | 31 | Optional |
| ShipAddr > Line 1 | Shipping Address | Zynk Software | string | 500 | Optional |
| ShipAddr > Line 2 | Shipping Address | Nelson House | string | 500 | Optional |
| ShipAddr > Line 3 | Shipping Address | Jesmond | string | 500 | Optional |
| ShipAddr > Line 4 | Shipping Address | string | 500 | Optional |
| ShipAddr > Line 5 | Shipping Address | string | 500 | Optional |
| ShipAddr > City | City/Town | Newcastle | string | 255 | Optional |
| ShipAddr > Country | County | England | string | 255 | Optional |
| ShipAddr > CountrySubDivisionCode | Region | Tyne & Wear | string | 255 | Optional |
| ShipAddr > PostalCode | Postcode | NE2 3AE | string | 31 | Optional |
| Notes | Notes | Sample note | string | 2000 | Optional |
| PaymentMethodRef | Preferred Payment Method | 1 | integer | - | Optional | If you don't know the payment method ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| PreferredDeliveryMethod | Preferred Delivery Method | Print | enum | - | Optional | Allowed values are Print, Email and None. Defaults to None if not specified. |
| SalesTermRef | Terms | 1 | integer | - | Optional | If you don't know the sales term ID, you can specify the name using the name attribute, and the task will perform a lookup. |
| Balance | Opening Balance | 1000 | decimal | - | Optional | Can only be set when first creating the customer. Will default to 0 if not specified. |
| OpenBalanceDate | Opening Balance As Of | 2016-07-15 | date | - | Optional | Can only be set when first creating the customer. |
| CurrencyRef | This Customer Pays Me With | GBP | string | - | Optional | Can only be set when first creating the customer. Provide the three letter ISO currency code as the value. Defaults to the home currency of the QuickBooks company if not specified. |
| Active | Active | true | boolean | - | Optional | Defaults to true if not specified. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <RecordOfCustomer>
    <ExternalId>6492</ExternalId>
    <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
      <Id>1234</Id>
      <DisplayName>Zynk Software</DisplayName>
      <Title>Mr</Title>
      <GivenName>John</GivenName>
      <MiddleName>Neville</MiddleName>
      <FamilyName>Smith</FamilyName>
      <Suffix>BSc</Suffix>
      <CompanyName>Zynk Software</CompanyName>
      <PrimaryEmailAddr>
        <Address>support@zynk.com</Address>
      </PrimaryEmailAddr>
      <PrimaryPhone>
        <FreeFormNumber>0191 123 4567</FreeFormNumber>
      </PrimaryPhone>
      <Mobile>
        <FreeFormNumber>07123456789</FreeFormNumber>
      </Mobile>
      <Fax>
        <FreeFormNumber>0191 123 4567</FreeFormNumber>
      </Fax>
      <AlternatePhone>
        <FreeFormNumber>0191 123 4567</FreeFormNumber>
      </AlternatePhone>
      <WebAddr>
        <URI>www.zynk.com</URI>
      </WebAddr>
      <ParentRef name="Internetware">1</ParentRef>
      <BillWithParent>false</BillWithParent>
      <BillAddr>
        <Line1>Zynk Software</Line1>
        <Line2>Nelson House</Line2>
        <Line3>Jesmond</Line3>
        <City>Newcastle</City>
        <Country>England</Country>
        <CountrySubDivisionCode>Tyne & Wear</CountrySubDivisionCode>
        <PostalCode>NE2 3AE</PostalCode>
      </BillAddr>
      <ShipAddr>
        <Line1>Zynk Software</Line1>
        <Line2>Nelson House</Line2>
        <Line3>Jesmond</Line3>
        <City>Newcastle</City>
        <Country>England</Country>
        <CountrySubDivisionCode>Tyne & Wear</CountrySubDivisionCode>
        <PostalCode>NE2 3AE</PostalCode>
      </ShipAddr>
      <Notes>Sample note</Notes>
      <PaymentMethodRef name="Card">1</PaymentMethodRef>
      <PreferredDeliveryMethod>None</PreferredDeliveryMethod>
      <SalesTermRef name="Due on receipt">1</SalesTermRef>
      <Balance>1000</Balance>
      <OpenBalanceDate>2016-07-15</OpenBalanceDate>
      <CurrencyRef>GBP</CurrencyRef>
      <Active>true</Active>
    </Data>
  </RecordOfCustomer>
</ArrayOfCustomer>
```