---
slug: exporting-orders-from-ekm
title: Exporting Orders from EKM
---
This task will export orders from EKM, and output them to an XML file.

## Settings
### Connection
_Required_  
The EKM connection to use. See the [Connecting to EKM](connecting-to-ekm) article if you require more information on how to create/manage connections.

### Export Settings > Date Modified
_Required_  
When the task is set to export modified records, this is the date modified records will be exported from. The value for this setting will update automatically when the task is ran.

### Export Settings > Export Modified or All Records
_Required_  
Select which records should be included in the export. The following options are available:
- **Modified** - Only records created or updated since the date shown in the Date Modified setting will be exported.
- **All** - All records will be exported.

### Page Size
_Required_  
The number of records to export on each page of data requested from EKM. The maximum value is 20.

### Query 
_Optional_  
Specify a custom filter to apply to the export. Only records meeting the criteria specified will be exported. The query must be specified using [OData filter syntax](https://www.odata.org/getting-started/basic-tutorial/#filter). Please note that EKM only supports a subset of the OData filter syntax.

For example, you can use `status eq 'PENDING'` to only export orders at the pending status. 

### Record IDs
_Optional_  
Specify a list of comma separated record IDs to export specific records from EKM. Using this setting will override the Query and Export Settings.

### Output File
_Required_  
The name of the file to output the exported data to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <Id>1</Id>
    <ExternalId />
    <OrderNumber>1/311019/48</OrderNumber>
    <OrderDate>2019-10-31T17:14:21Z</OrderDate>
    <IsConfirmed>true</IsConfirmed>
    <SubTotal>2</SubTotal>
    <TotalDelivery>0</TotalDelivery>
    <TotalTax>0.4</TotalTax>
    <TotalCost>2.4</TotalCost>
    <Status>PENDING</Status>
    <OrderType>Quote</OrderType>
    <UseShippingAddress>true</UseShippingAddress>
    <ShippingAddress>
      <Id>0</Id>
      <CustomerId>0</CustomerId>
      <FirstName>Adam</FirstName>
      <LastName>Wardle</LastName>
      <Company>Zynk Software</Company>
      <Address>6-8 Charlotte Square</Address>
      <Address2 />
      <Town>Newcatle upon Tyne</Town>
      <County>Tyne &amp; Wear</County>
      <Country>GB</Country>
      <FriendlyCountry>United Kingdom</FriendlyCountry>
      <PostCode>NE1 4XF</PostCode>
      <IsPreferredBillingAddress>false</IsPreferredBillingAddress>
      <IsPreferredShippingAddress>false</IsPreferredShippingAddress>
      <CreatedDate xsi:nil="true" />
      <ModifiedDate xsi:nil="true" />
    </ShippingAddress>
    <InternalNotes>internal notes</InternalNotes>
    <CustomerFacingNotes>order notes</CustomerFacingNotes>
    <Emailed>false</Emailed>
    <Discounts />
    <DiscountsTotal>0.5</DiscountsTotal>
    <ShippingCompany>Zynk Software</ShippingCompany>
    <Guid>00000000-0000-0000-0000-000000000000</Guid>
    <LastUpdated>2019-10-31T17:17:36Z</LastUpdated>
    <Items>
      <OrderItem>
        <Id>1</Id>
        <ItemDelivery>0</ItemDelivery>
        <ItemDiscount>0</ItemDiscount>
        <ItemName>Pen</ItemName>
        <ItemOptions />
        <ItemPrice>2.5</ItemPrice>
        <ItemTax>0.5</ItemTax>
        <ItemTaxId>1</ItemTaxId>
        <ItemTaxRate>20</ItemTaxRate>
        <OrderNumber>1/311019/48</OrderNumber>
        <Quantity>1</Quantity>
        <OriginalItemId>1</OriginalItemId>
        <OrderId>1</OrderId>
        <Product>
          <Id>1</Id>
          <Name>Pen</Name>
        </Product>
      </OrderItem>
    </Items>
    <CustomerDetails>
      <CustomerId>1</CustomerId>
      <EmailAddress>support@zynk.com</EmailAddress>
      <FirstName>Adam</FirstName>
      <LastName>Wardle</LastName>
      <Company>Zynk Software</Company>
      <Address>6-8 Charlotte Square</Address>
      <Address2 />
      <Town>Newcatle upon Tyne</Town>
      <County>Tyne &amp; Wear</County>
      <Country>GB</Country>
      <PostCode>NE1 4XF</PostCode>
      <Telephone>0191 303 7279</Telephone>
      <BillingAddressVerified>false</BillingAddressVerified>
    </CustomerDetails>
  </Order>
</Orders>
```
