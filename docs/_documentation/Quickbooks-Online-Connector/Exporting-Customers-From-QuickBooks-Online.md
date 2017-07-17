---
slug: exporting-customers-from-quickbooks-online
redirect_from: "/article/869-downloading-customers-from-quickbooks-online"
title: Exporting Customers From QuickBooks Online
---


This task will download customers from Quickbooks Online to an XML file.


## Download Customers

### Connection
_Required_  
Select a connection to the Quickbooks Online company you want to use. See [Connecting to QuickBooks Online](connecting-to-quickbooks-online)

### Output File
_Required_  
The file save exported records to.

### Quickbooks Online Settings
See [Common Quickbooks Online Settings](common-quickbooks-online-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Available Filters
- Id
- GivenName
- MiddleName
- FamilyName
- Suffix
- DisplayName
- FullyQualifiedName
- CompanyName
- PrintOnCheckName
- Active
- PrimaryEmailAddr
- Balance


## Examples


Sample output file:


```xml
    <?xml version="1.0" encoding="utf-8"?>
    <ArrayOfCustomer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <RecordOfCustomer>
        <ExternalId>6108</ExternalId>
        <Data domain="QBO" sparse="false" xmlns="http://schema.intuit.com/finance/v3">
          <Id>2068</Id>
          <SyncToken>2</SyncToken>
          <MetaData>
            <CreateTime>2016-07-07T09:41:38+01:00</CreateTime>
            <LastUpdatedTime>2016-07-18T11:49:20+01:00</LastUpdatedTime>
          </MetaData>
          <FullyQualifiedName>Zynk Software</FullyQualifiedName>
          <CompanyName>Zynk Software</CompanyName>
          <DisplayName>Zynk Software</DisplayName>
          <PrintOnCheckName>Zynk Software</PrintOnCheckName>
          <Active>true</Active>
          <PrimaryEmailAddr>
            <Address>support@zynk.com</Address>
          </PrimaryEmailAddr>
          <DefaultTaxCodeRef>3</DefaultTaxCodeRef>
          <Taxable>false</Taxable>
          <BillAddr>
            <Id>69</Id>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </BillAddr>
          <ShipAddr>
            <Id>74</Id>
            <Line1>Nelson House</Line1>
            <Line2>Jesmond</Line2>
            <City>Newcastle</City>
            <CountrySubDivisionCode>Tyne &amp;amp; Wear</CountrySubDivisionCode>
            <PostalCode>NE2 3AE</PostalCode>
          </ShipAddr>
          <Job>false</Job>
          <BillWithParent>false</BillWithParent>
          <Balance>4690</Balance>
          <BalanceWithJobs>4690</BalanceWithJobs>
          <CurrencyRef name="British Pound Sterling">GBP</CurrencyRef>
          <PreferredDeliveryMethod>None</PreferredDeliveryMethod>
        </Data>
      </RecordOfCustomer>
    </ArrayOfCustomer>

```