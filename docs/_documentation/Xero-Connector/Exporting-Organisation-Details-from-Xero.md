---
slug: exporting-organisation-details-from-xero
redirect_from: "/article/905-downloading-organisation-details-from-xero"
title: Exporting Organisation Details from Xero
---


This task will download details of your organisation from Xero in XML format.


## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Zynk Settings
See [Common Task Settings](common-task-settings)



## Examples


Sample output file showing organisation information:

```xml
<?xml version="1.0"?>
    <Organisation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <Name>Zynk Test 1</Name>
      <LegalName>Zynk Test 1</LegalName>
      <ShortCode>!4!2XZ</ShortCode>
      <PaysTax>true</PaysTax>
      <Version>UnitedKingdom</Version>
      <OrganisationType>Company</OrganisationType>
      <IsDemoCompany>false</IsDemoCompany>
      <BaseCurrency>GBP</BaseCurrency>
      <ApiKey>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ApiKey>
      <CountryCode>GB</CountryCode>
      <OrganisationStatus>Active</OrganisationStatus>
      <FinancialYearEndDay>31</FinancialYearEndDay>
      <FinancialYearEndMonth>3</FinancialYearEndMonth>
      <PeriodLockDate xsi:nil="true" />
      <EndOfYearLockDate xsi:nil="true" />
      <CreatedDateUtc>2015-03-15T20:32:59.323Z</CreatedDateUtc>
      <Timezone>GMTSTANDARDTIME</Timezone>
      <PaymentTerms>
        <ValidationStatus>Ok</ValidationStatus>
        <Sales>
          <ValidationStatus>Ok</ValidationStatus>
          <Day>0</Day>
          <TermType>AfterBillDate</TermType>
        </Sales>
      </PaymentTerms>
      <SalesTaxBasisType>None</SalesTaxBasisType>
      <SalesTaxPeriod>None</SalesTaxPeriod>
      <Addresses />
      <Phones />
      <ExternalLinks />
    </Organisation>
```