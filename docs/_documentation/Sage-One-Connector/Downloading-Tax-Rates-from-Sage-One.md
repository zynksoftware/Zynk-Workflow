---
slug: downloading-tax-rates-from-sage-one
redirect_from: "/article/886-download-tax-rates"
title: Downloading Tax Rates from Sage One
---
This task will download Tax Rates from your instance of Sage One.

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
A sample output file is shown below.
```xml
<?xml version="1.0"?>
<ArrayOfTaxRate xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <TaxRate>
    <SageOneRecordId>1</SageOneRecordId>
    <Name>Standard 20.00%</Name>
    <Rate>20</Rate>
  </TaxRate>
  <TaxRate>
    <SageOneRecordId>2</SageOneRecordId>
    <Name>Lower Rate 5.00%</Name>
    <Rate>5</Rate>
  </TaxRate>
  <TaxRate>
    <SageOneRecordId>3</SageOneRecordId>
    <Name>Zero Rated 0.00%</Name>
    <Rate>0</Rate>
  </TaxRate>
  <TaxRate>
    <SageOneRecordId>4</SageOneRecordId>
    <Name>Exempt 0.00%</Name>
    <Rate>0</Rate>
  </TaxRate>
  <TaxRate>
    <SageOneRecordId>5</SageOneRecordId>
    <Name>No VAT</Name>
    <Rate>0</Rate>
  </TaxRate>
</ArrayOfTaxRate>
```