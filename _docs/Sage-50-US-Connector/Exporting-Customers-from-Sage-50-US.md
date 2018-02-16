---
slug: exporting-customers-from-sage-50-us
title: Exporting Customers from Sage 50 US
---
This task will export customer information from Sage 50 US in the [Sage 50 US Customer XML](sage-50-us-customer-xml) format. You can choose to export either all, modified or only new records, and can filter the exports if only a subset of your customer records are required.

## Settings
### Sage Connection
_Required_  
The connection to Sage 50 US to use. See the [Connecting to Sage 50 US](connecting-to-sage-50-us) article if you require more information on how to create/manage connections.

### Export New, Modified or All Records
_Required_  
Setting to determine which records are exported from Sage. New will only export records created since the last time Zynk was ran. Modified will only export records updated in Sage since the last time Zynk was ran. All will always export all records.

### Filters
_Optional_  
Settings to allow only specific records to be exported from Sage. See the [Sage 50 US Filters](sage-50-us-filters) article for more information.

### Output File
_Required_  
The name of the file to export to. Data is exported in [Sage 50 US Customer XML](sage-50-us-customer-xml) format.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage 50 US Customer XML](sage-50-us-customer-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>123</ExternalId>
    <Id>ALDRED</Id>
    <Name>Aldred Builders, Inc.</Name>
    <IsInactive>false</IsInactive>
    <AccountNumber />
    <Category>LAND</Category>
    <CustomFields>
      <CustomField>
        <Name>Sales Contact</Name>
        <Value />
      </CustomField>
      <CustomField>
        <Name>Lawn Care Srvc?</Name>
        <Value>Yes</Value>
      </CustomField>
      <CustomField>
        <Name>Monthly Service?</Name>
        <Value>Yes</Value>
      </CustomField>
      <CustomField>
        <Name>Qtrly Mailing?</Name>
        <Value>Yes</Value>
      </CustomField>
      <CustomField>
        <Name>Referral</Name>
        <Value>Internet</Value>
      </CustomField>
    </CustomFields>
    <ShipVia>None</ShipVia>
    <UseEmailToDeliverForms>false</UseEmailToDeliverForms>
    <ReplaceInventoryItemIDWithUPC>false</ReplaceInventoryItemIDWithUPC>
    <ReplaceInventoryItemIDWithPartNumber>false</ReplaceInventoryItemIDWithPartNumber>
    <PaymentMethod>Check</PaymentMethod>
    <CashAccountReference>10200-00</CashAccountReference>
    <Terms>
      <ChargeInterest>true</ChargeInterest>
      <CreditLimit>50000.00</CreditLimit>
      <DiscountDays>10</DiscountDays>
      <DiscountPercent>2.00</DiscountPercent>
      <DueDays>30</DueDays>
      <IsStandardTerms>false</IsStandardTerms>
      <PaymentTimeFrame>DueInNumberOfDays</PaymentTimeFrame>
      <UseDiscounts>true</UseDiscounts>
    </Terms>
    <IsProspect>false</IsProspect>
    <BillToContact>
      <Prefix />
      <FirstName>Tony</FirstName>
      <MiddleInitial />
      <LastName>Aldred</LastName>
      <Suffix />
      <CompanyName>Aldred Builders, Inc.</CompanyName>
      <Title />
      <Telephone1>770-555-0654</Telephone1>
      <Telephone2>770-555-0655</Telephone2>
      <Fax>770-555-0656</Fax>
      <Email>taldred@sample.sage.com</Email>
      <Gender>NotSpecified</Gender>
      <NameToUseOnForms>CompanyName</NameToUseOnForms>
      <Address>
        <Address1>412 Sever Rd</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30092</Zip>
        <Country />
        <SalesTaxCode>GAGWINN</SalesTaxCode>
      </Address>
      <Notes />
    </BillToContact>
    <ShipToContact>
      <Prefix />
      <FirstName>Tammy</FirstName>
      <MiddleInitial />
      <LastName>Aldred</LastName>
      <Suffix />
      <CompanyName>Aldred Builders, Inc.</CompanyName>
      <Title>Bookkeeper</Title>
      <Telephone1>770-555-0657</Telephone1>
      <Telephone2>770-555-0658</Telephone2>
      <Fax>770-555-0659</Fax>
      <Email>tammyaldred@sample.sage.com</Email>
      <Gender>NotSpecified</Gender>
      <NameToUseOnForms>ContactName</NameToUseOnForms>
      <Address>
        <Address1>412 Sever Rd</Address1>
        <Address2 />
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30092</Zip>
        <Country />
        <SalesTaxCode>GAGWINN</SalesTaxCode>
      </Address>
      <Notes />
    </ShipToContact>
    <CustomerSince>2011-03-15T00:00:00</CustomerSince>
    <SalesRepresentativeReference>DGROSS</SalesRepresentativeReference>
    <UsualSalesAccountReference>40000-00</UsualSalesAccountReference>
    <OpenPurchaseOrderNumber />
    <ResaleNumber />
    <PriceLevel>Price Level 1</PriceLevel>
    <CreditStatus>NotifyOverLimit</CreditStatus>
  </Customer>
</ArrayOfCustomer>
```