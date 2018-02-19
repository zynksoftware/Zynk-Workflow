---
slug: importing-customers-into-sage-50-us
title: Importing Customers into Sage 50 US
---
This task will import customer information in the [Sage 50 US Customer XML](sage-50-us-customer-xml) format into Sage 50 US.

## Settings
### Sage Connection
_Required_  
The connection to Sage 50 US to use. See the [Connecting to Sage 50 US](connecting-to-sage-50-us) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file that you want to import in XML format.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.

### Auto Generate Account IDs
_Required_  
Set this to 'True' to automatically generate an ID for each customer if it isn't specified in the input file.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage 50 US Customer XML](sage-50-us-customer-xml) for full documentation of the XML format.
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