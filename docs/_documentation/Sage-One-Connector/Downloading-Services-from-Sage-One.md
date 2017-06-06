---
slug: downloading-services-from-sage-one
redirect_from: "/article/857-download-services"
title: Downloading Services from Sage One
---
This task will download Services from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Download Type
_Required_  
Select All, New or Modified.

### Record Id
_Optional_  
Optionally download a specific record by specifying the Sage One id.

### Output File
_Required_  
The file to save the downloaded records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage One Supplier XML](sage-one-supplier-xml) for full documentaion of the XML format.
```xml
<?xml version="1.0"?>
<ArrayOfService xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Service>
    <SageOneRecordId>1757583</SageOneRecordId>
    <Name>Bringing It All Back Home</Name>
    <ServiceLedgerAccount>
      <SageOneRecordId>9081395</SageOneRecordId>
      <Errors />
      <Name>Sales Type B</Name>
      <NominalCode>4001</NominalCode>
    </ServiceLedgerAccount>
    <ServiceTaxRate>
      <SageOneRecordId>1</SageOneRecordId>
      <Errors />
      <Name>Standard 20.00%</Name>
      <Rate>20</Rate>
      <SubTaxRates />
    </ServiceTaxRate>
    <PeriodRateIncludesTax xsi:nil="true" />
    <PeriodRate>
      <SageOneRecordId>1</SageOneRecordId>
      <PeriodRateType>Annually</PeriodRateType>
    </PeriodRate>
    <SalePrice>16</SalePrice>
    <Notes>Bob Dylan's first electric album includes tracks It's All Over Now Baby Blue, Maggie's Farm and Subterranean Homesick Blues.</Notes>
  </Service>
  <Service>
    <SageOneRecordId>1797952</SageOneRecordId>
    <Name>Oasis - Be Here Now</Name>
    <ServiceLedgerAccount>
      <SageOneRecordId>2654285</SageOneRecordId>
      <Errors />
      <Name>Sales Type A</Name>
      <NominalCode>4000</NominalCode>
    </ServiceLedgerAccount>
    <ServiceTaxRate>
      <SageOneRecordId>1</SageOneRecordId>
      <Errors />
      <Name>Standard 20.00%</Name>
      <Rate>20</Rate>
      <SubTaxRates />
    </ServiceTaxRate>
    <PeriodRateIncludesTax xsi:nil="true" />
    <PeriodRate>
      <SageOneRecordId>2</SageOneRecordId>
      <PeriodRateType>Daily</PeriodRateType>
    </PeriodRate>
    <SalePrice>9.99</SalePrice>
    <Notes />
  </Service>
</ArrayOfService>
```