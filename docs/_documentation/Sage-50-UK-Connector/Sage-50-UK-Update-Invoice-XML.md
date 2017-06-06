---
slug: sage-50-uk-update-invoice-xml
title: Sage 50 UK Update Invoice XML
---
The Update Invoices task allows you to update certain fields on existing invoices in Sage 50. Any fields not documented below are not directly supported with our imports.  

Sample import file for updating an invoice:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <Id>123</Id>
      <InvoiceNumber>2014</InvoiceNumber>
      <CustomerOrderNumber>123</CustomerOrderNumber>
      <InvoiceAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Company>Zynk Software Limited</Company>
        <Address1>i6 Building</Address1>
        <Address2>Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE1 4XF</Postcode>
        <Telephone>0191 303 7279</Telephone>
      </InvoiceAddress>
      <InvoiceDeliveryAddress>
        <Company>Zynk Software Limited</Company>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Address1>i6 Building</Address1>
        <Address2>Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE1 4XF</Postcode>
      </InvoiceDeliveryAddress>
      <TakenBy>Frank</TakenBy>
      <Notes1>Website 1</Notes1>
      <Notes2>Leave next door</Notes2>
      <Notes3>Paid by PayPal</Notes3>
      <Custom1>Analysis 1</Custom1>
      <Custom2>Analysis 2</Custom2>
      <Custom3>Analysis 3</Custom3>
    </Invoice>
  </Invoices>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Matching Invoices  
You need to specify at least one of the fields below to identify the invoice to be updated.

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| -  | Id  | 123  | string  | 255 | Optional | If the invoice was created using [Importing Invoices into Sage 50 UK](importing-invoices-into-sage-50-uk), and an Id was provided in the XML at the time of import, you can use this field to match the invoices. Zynk will look up the invoice number in the truth table, based on the value you provide. |
| Inv No | InvoiceNumber  | 2014 | integer | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <Id>123</Id>
      <InvoiceNumber>2014</InvoiceNumber>
    </Invoice>
  </Invoices>
</Company>
```

## Details
The following fields can be updated on the Details tab on the invoices.

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name  | Company | Zynk Software Limited  | string  | 60  | Optional  | If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix. |
| Customer Contact | FullName | Mr Joe E Harrison Jr.  | string  | 30  | Optional  | This field is on the Order tab not Details, but included in the InvoiceAddress.  This field is not set directly in the XML, but is built up of Title, Forename, Middlename, Surname and Suffix. |
| -  | Title   | Mr  | string  | -  | Optional   |
| -  | Forename  | Joe  | string  | -  | Optional   |
| -  | Middlename | E  | string  | -  | Optional   |
| -  | Surname   | Harrison  | string  | -  | Optional   |
| -  | Suffix   | Jr.  | string  | -  | Optional   |
| Address 1  | Address1  | i6 Building | string  | 60  | Optional  |
| Address 2  | Address2  | Charlotte Square  | string  | 60  | Optional  |
| Address 3  | Address3 + Town  | Newcastle upon Tyne | string   | 60   | Optional  |
| Address 4  | County  | Tyne and Wear  | string  | 60  | Optional  |
| Address 5  | Postcode  | NE1 4XF | string   | 60  | Optional  |
| Customer Tel. No. | Telephone | 0191 303 7279 | string | 60 | Optional | This field is on the Order tab not Details, but included in the InvoiceAddress. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <InvoiceAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Company>Zynk Software Limited</Company>
        <Address1>i6 Building</Address1>
        <Address2>Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE1 4XF</Postcode>
        <Telephone>0191 303 7279</Telephone>
      </InvoiceAddress>
    </Invoice>
  </Invoices>
</Company>
```

## Order
The following fields can be updated on the Order tab on the invoices.

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Customer Order No. | CustomerOrderNumber  | 123  | string | 60  | Optional  |
| Order Taken By  | TakenBy  | Frank | string  | 60  | Optional  |
| Delivery Name | Company | Zynk Software Limited | string | 60 | Optional | If this field is not set in the XML, it is built up of Title, Forename, Middlename, Surname and Suffix. |
| -  | Title    | Mr   | string  | -  | Optional  |
| -  | Forename   | Joe  | string  | -  | Optional  |
| -  | Middlename  | E  | string  | -  | Optional  |
| -  | Surname  | Harrison  | string  | -  | Optional  |
| -  | Suffix  | Jr.   | string  | -  | Optional  |
| Delivery Address 1 | Address1 | i6 Building | string | 60 | Optional  |
| Delivery Address 2 | Address2 | Charlotte Square | string | 60 | Optional |
| Delivery Address 3 | Address3 + Town | Newcastle upon Tyne | string | 60 | Optional  |
| Delivery Address 4 | County | Tyne and Wear  | string | 60 | Optional |
| Delivery Address 5 | Postcode | NE1 4XF | string | 60 | Optional  |
| Notes 1 | Notes1 | Website 1 | string | 60 | Optional  |
| Notes 2 | Notes2 | Leave next door | string | 60 | Optional  |
| Notes 3 | Notes3 | Paid by PayPal  | string  | 60 | Optional   |
| Analysis1 | Custom1 | Analysis 1 | string | 60 | Optional | This field can be renamed in Sage, so may not appear as 'Analysis1' in the UI. |
| Analysis2 | Custom2 | Analysis 2 | string | 60 | Optional | This field can be renamed in Sage, so may not appear as 'Analysis2' in the UI. |
| Analysis3 | Custom3 | Analysis 3 | string | 60 | Optional | This field can be renamed in Sage, so may not appear as 'Analysis3' in the UI. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <CustomerOrderNumber>123</CustomerOrderNumber>
      <TakenBy>Frank</TakenBy>
      <InvoiceDeliveryAddress>
        <Company>Zynk Software Limited</Company>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Suffix>Jr.</Suffix>
        <Address1>i6 Building</Address1>
        <Address2>Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE1 4XF</Postcode>
      </InvoiceDeliveryAddress>
      <Notes1>Website 1</Notes1>
      <Notes2>Leave next door</Notes2>
      <Notes3>Paid by PayPal</Notes3>
      <Custom1>Analysis 1</Custom1>
      <Custom2>Analysis 2</Custom2>
      <Custom3>Analysis 3</Custom3>
    </Invoice>
  </Invoices>
</Company>
```