---
slug: exporting-purchase-orders-from-xero
redirect_from: "/article/961-downloading-purchase-orders-from-xero"
title: Exporting Purchase Orders from Xero
---


This task will download purchase orders from Xero in XML format.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Export All
_Required_
Set to true to export all records, or false to only export records since the time shown in the Export From setting.

### Export From
_Required_
The rolling date to export modified records from. This will update automatically when the task runs. This setting only takes affect when Export All is set to false.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. 	`Type == "BANK" AND Name.Contains("Business")`

### Zynk Settings
See [Common Task Settings](common-task-settings)



## Examples


Sample output file showing two accounts:

```xml
<?xml version="1.0" encoding="utf-8"?>
    <ArrayOfPurchaseOrder>
      <XeroPurchaseOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <Errors />
        <Warnings />
        <ValidationStatus>Ok</ValidationStatus>
        <UpdatedDateUtc>2017-01-06T15:02:12.493</UpdatedDateUtc>
        <Id>e9228aac-745b-4d05-b121-31c98b6593fc</Id>
        <ExternalId>3452</ExternalId>
        <Number>PO-0003</Number>
        <Date>2017-01-04T00:00:00</Date>
        <DeliveryDate>2017-01-11T00:00:00</DeliveryDate>
        <ExpectedArrivalDate xsi:nil="true" />
        <DeliveryAddress>Newcastle Enterprise Centres
    6 Charlotte Square
    Newcastle upon Tyne
    Tyne and Wear
    NE1 4XF
    United Kingdom</DeliveryAddress>
        <AttentionTo>Bob</AttentionTo>
        <Telephone>0191 303 7279</Telephone>
        <DeliveryInstructions>Leave by the gate</DeliveryInstructions>
        <TotalDiscount xsi:nil="true" />
        <SentToContact>false</SentToContact>
        <Reference>Test 123</Reference>
        <CurrencyCode>GBP</CurrencyCode>
        <CurrencyRate>1.000000</CurrencyRate>
        <Contact>
          <ValidationStatus>Ok</ValidationStatus>
          <UpdatedDateUtc>2015-09-25T08:30:57.533</UpdatedDateUtc>
          <Id>20435ce7-50b7-4a86-926a-8248778e1dcb</Id>
          <ContactStatus>Active</ContactStatus>
          <Name>Concept Stationery Supplies</Name>
          <FirstName>Mark</FirstName>
          <LastName>Ramsay</LastName>
          <IsSupplier xsi:nil="true" />
          <IsCustomer xsi:nil="true" />
          <DefaultCurrency>GBP</DefaultCurrency>
          <Discount xsi:nil="true" />
          <HasAttachments xsi:nil="true" />
          <ContactPersons />
          <Addresses>
            <Address>
              <ValidationStatus>Ok</ValidationStatus>
              <AddressType>Street</AddressType>
              <AddressLine1>66 New Street</AddressLine1>
              <AddressLine2>Ridgeway</AddressLine2>
              <AddressLine3 />
              <City>Newcastle upon Tyne</City>
              <Region />
              <PostalCode>NE1 4GF</PostalCode>
              <Country>GB</Country>
              <AttentionTo>Mark Ramsay</AttentionTo>
            </Address>
            <Address>
              <ValidationStatus>Ok</ValidationStatus>
              <AddressType>PostOfficeBox</AddressType>
              <AddressLine1>66 New Street</AddressLine1>
              <AddressLine2>Ridgeway</AddressLine2>
              <AddressLine3 />
              <City>Newcastle Upon Tyne</City>
              <Region />
              <PostalCode>NE1 4GF</PostalCode>
              <Country>GB</Country>
              <AttentionTo>Mark Ramsay</AttentionTo>
            </Address>
          </Addresses>
          <Phones>
            <Phone>
              <ValidationStatus>Ok</ValidationStatus>
              <PhoneType>Default</PhoneType>
              <PhoneNumber>0191 643 4343</PhoneNumber>
              <PhoneAreaCode />
              <PhoneCountryCode />
            </Phone>
            <Phone>
              <ValidationStatus>Ok</ValidationStatus>
              <PhoneType>Fax</PhoneType>
              <PhoneNumber>0191 643 4345</PhoneNumber>
              <PhoneAreaCode />
              <PhoneCountryCode />
            </Phone>
            <Phone>
              <ValidationStatus>Ok</ValidationStatus>
              <PhoneType>Mobile</PhoneType>
              <PhoneNumber>0191 643 4344</PhoneNumber>
              <PhoneAreaCode />
              <PhoneCountryCode />
            </Phone>
          </Phones>
          <ContactGroups />
        </Contact>
        <BrandingThemeID xsi:nil="true" />
        <Status>Submitted</Status>
        <LineAmountTypes>Exclusive</LineAmountTypes>
        <LineItems>
          <LineItem>
            <ValidationStatus>Ok</ValidationStatus>
            <Description>test</Description>
            <Quantity>1.0000</Quantity>
            <UnitAmount>15.0000</UnitAmount>
            <AccountCode>5000</AccountCode>
            <ItemCode>BOARD001</ItemCode>
            <TaxType>INPUT2</TaxType>
            <TaxAmount>3.00</TaxAmount>
            <LineAmount>15.00</LineAmount>
            <DiscountRate xsi:nil="true" />
            <Tracking />
            <LineItemId>25cfa16c-1116-49f8-ae7d-3f5de3d81416</LineItemId>
          </LineItem>
          <LineItem>
            <ValidationStatus>Ok</ValidationStatus>
            <Description>test 2</Description>
            <Quantity>5.0000</Quantity>
            <UnitAmount>1.5000</UnitAmount>
            <AccountCode>5000</AccountCode>
            <ItemCode>BOOKS002</ItemCode>
            <TaxType>INPUT2</TaxType>
            <TaxAmount>1.50</TaxAmount>
            <LineAmount>7.50</LineAmount>
            <DiscountRate xsi:nil="true" />
            <Tracking />
            <LineItemId>9a602aa5-bd07-4c77-a646-9adfc8498eb4</LineItemId>
          </LineItem>
        </LineItems>
        <SubTotal>22.50</SubTotal>
        <TotalTax>4.50</TotalTax>
        <Total>27.00</Total>
        <HasAttachments>false</HasAttachments>
        <ExternalId />
      </XeroPurchaseOrder>
    </ArrayOfPurchaseOrder>
```