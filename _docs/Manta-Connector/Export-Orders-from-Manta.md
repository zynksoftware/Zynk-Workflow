---
slug: exporting-orders-from-manta
title: Exporting Orders from Manta
---

This task will export orders from Manta in [Manta Order XML](manta-order-xml) format to a file.

## Settings
### Connection Settings
#### Manta Connection
_Required_  
The connection to Manta to use. See the [Connecting to Manta](connecting-to-manta) article if you require further information on how to create/manage the connection to Manta.

### Export Settings
#### Order Type
_Required_  
Order status to export from Manta. Supported types:
* po
* oc
* proforma

### Import Settings
#### Output File
_Required_   
The name of the file to export the quotations to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file, for full documentation and samples see [Manta Order XML](manta-order-xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <OrderId>32904</OrderId>
    <BackOrder xsi:nil="true" />
    <PoAttached xsi:nil="true" />
    <OrderType>po</OrderType>
    <OrderDate>2018-10-12 00:00:00</OrderDate>
    <OrderStatus>wait_brand_confirm</OrderStatus>
    <Shopcode>fr</Shopcode>
    <ShopName>Zynk Software</ShopName>
    <TransactionCurrency>EUR</TransactionCurrency>
    <OrderReference>PO-000012345</OrderReference>
    <CompanyOrderReference>Zynk Sofware</CompanyOrderReference>
    <CompanyId>1</CompanyId>
    <BuyerContactId>2212</BuyerContactId>
    <InvoiceContactId>2212</InvoiceContactId>
    <DeliveryContactId>2212</DeliveryContactId>
    <InvoiceAddressId>10771</InvoiceAddressId>
    <DeliveryAddressId>11266</DeliveryAddressId>
    <Carriage>0</Carriage>
    <CompanyCode>ZYNK001</CompanyCode>
    <Company>Zynk</Company>
    <CompanyBrandCode>ZYNK</CompanyBrandCode>
    <BrandReference>LU</BrandReference>
    <SalesPerson>Joe Bloggs</SalesPerson>
    <VatNumber>GB796576359</VatNumber>
    <PaymentTerms>30 Days Net</PaymentTerms>
    <PaymentMethod>bank_transfer</PaymentMethod>
    <OrderLocation>Mail</OrderLocation>
    <BrandDiscount>0</BrandDiscount>
    <BuyerContact>
      <ContactId>2212</ContactId>
      <ContactType>buyer</ContactType>
      <Language>fr_FR</Language>
      <Email>test@zynk.com</Email>
      <Prefix>mr</Prefix>
      <Firstname>Zynk</Firstname>
      <Lastname>Test</Lastname>
      <Phone>01913037279</Phone>
      <WorkingHours />
      <AddressIds>
        <string>10771</string>
        <string>11266</string>
      </AddressIds>
      <MobilePhone>01913037279</MobilePhone>
      <ActiveShops>
        <string>fr</string>
      </ActiveShops>
    </BuyerContact>
    <Contacts>
      <Contact>
        <ContactId>2212</ContactId>
        <ContactType>buyer</ContactType>
        <Language>fr_FR</Language>
        <Email>test@zynk.com</Email>
        <Prefix>mr</Prefix>
        <Firstname>Zynk</Firstname>
        <Lastname>Test</Lastname>
        <Phone>01913037279</Phone>
        <WorkingHours />
        <AddressIds>
          <string>10771</string>
          <string>11266</string>
        </AddressIds>
        <MobilePhone>01913037279</MobilePhone>
        <ActiveShops>
          <string>fr</string>
        </ActiveShops>
      </Contact>
    </Contacts>
    <ProductSubtotal>10.6</ProductSubtotal>
    <ProductDiscount>0</ProductDiscount>
    <ProductTotal>10.6</ProductTotal>
    <TotalDiscountIncludingCarriage>0</TotalDiscountIncludingCarriage>
    <TotalDiscount>0</TotalDiscount>
    <TotalDiscountPercentage>0</TotalDiscountPercentage>
    <TotalNet>10.6</TotalNet>
    <TotalVat>0</TotalVat>
    <TotalGross>10.6</TotalGross>
    <InvoiceAddressContact>
      <City>Newcastle upon Tyne</City>
      <CountryId>GB</CountryId>
      <Email>test@zynk.com</Email>
      <Firstname>Zynk</Firstname>
      <Lastname>Software</Lastname>
      <Postcode>NE1 4XF</Postcode>
      <Prefix>mr</Prefix>
      <Street>i6 Charlotte Square</Street>
      <Street>6-8 Charlotte Square</Street>
      <Phone>01913037279</Phone>
    </InvoiceAddressContact>
    <DeliveryAddressContact>
      <City>Newcastle upon Tyne</City>
      <CountryId>GB</CountryId>
      <Email>test@zynk.com</Email>
      <Firstname>Zynk</Firstname>
      <Lastname>Software</Lastname>
      <Postcode>NE1 4XF</Postcode>
      <Prefix>mr</Prefix>
      <Street>i6 Charlotte Square</Street>
      <Street>6-8 Charlotte Square</Street>
      <Phone>01913037279</Phone>
      <OtherRemarks>No remarks</OtherRemarks>
    </DeliveryAddressContact>
    <Comments>
      <Comment>
        <Message>Order Message</Message>
        <CreatedAt>2018-10-12 08:48:49</CreatedAt>
        <IsVisibleOnFront>0</IsVisibleOnFront>
      </Comment>
    </Comments>
    <TotalItemCount>1</TotalItemCount>
    <Items>
      <Item>
        <ItemId>46212</ItemId>
        <Sku>TEST01</Sku>
        <Ean>1060146590300</Ean>
        <Name>Zynk test product</Name>
        <Price>10.6</Price>
        <Qty>1</Qty>
        <NetPrice>10.6</NetPrice>
        <DiscountPercentage>0</DiscountPercentage>
        <Discount>0</Discount>
        <RowTotalNet>10.6</RowTotalNet>
        <RowTotalVat>0</RowTotalVat>
        <RowTotalGross>10.6</RowTotalGross>
        <Invoiced>0</Invoiced>
        <Shipped>0</Shipped>
        <Creditmemo>0</Creditmemo>
        <Confirmed>0</Confirmed>
        <NotConfirmed>1</NotConfirmed>
        <Canceled>0</Canceled>
      </Item>
    </Items>
  </Order>
</Orders>
```