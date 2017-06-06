---
slug: sage-200-supplier-xml
title: Sage 200 Supplier XML
---
Import Suppliers allows you to create new and update existing suppliers in Sage 200. We recommend that the Id field be populated by the unique id of the suppliers from the external system, Zynk uses this field to track suppliers already imported to prevent duplicates being created in Sage, and to allow purchase orders to be created without the supplier's account reference (the SupplierId is provided instead, which is useful when the external system does not store the account reference).   

Any fields not documented below are not supported with our imports. Examples of where in the XML the fields should appear are shown in the samples below.  

Sample import file for creating a supplier:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <Id>123</Id>
      <AccountReference>CON001</AccountReference>
      <CompanyName>Concept Stationery Supplies</CompanyName>
      <VatNumber>GB988 3453 23</VatNumber>
      <CreditLimit>5000</CreditLimit>
      <SupplierInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Mark</Forename>
        <Surname>Ramsay</Surname>
        <Address1>66 New Street</Address1>
        <Address2>Ridgeway</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE1 4GF</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Telephone>0191 643 4343</Telephone>
        <Mobile>0191 643 4344</Mobile>
        <Fax>0191 643 4345</Fax>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
      </SupplierInvoiceAddress>
      <Currency>GBP</Currency>
      <TaxCode>1</TaxCode>
      <NominalCode>4002</NominalCode>
      <CostCentre>TES</CostCentre>
      <Department>DEP</Department>
      <TermsAgreed>true</TermsAgreed>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>TEST</Name>
          <Value>123</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </Supplier>
  </Suppliers>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the Company schema is used below as a reference of where fields should be in the XML.

## Company
The information below can be specified on the Company tab in Sage. Depending on your configuration at the Task Settings level in Zynk, you may not need to specify an account reference for every supplier. This applies when the 'Auto Generate References' or 'Match Accounts On' settings are enabled. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes  |
| --- | --- | --- | --- | --- | --- | --- |
| - | Id | 123 | string | 255 | Optional | Used internally by Zynk for duplicate prevention and when importing suppliers. |
| A/C Ref | AccountReference | CON001 | string | 8 | Optional | Required when the 'Auto Generate References' and 'Match Accounts On' task settings are disabled, and the 'Automatically generate supplier numbers' setting in Sage is disabled. |
| Name | CompanyName | Concept Stationery Supplies | string | 60 | Optional  | If a CompanyName is not provided, it will default to the Title, Forename, Middlename and Surname. |
| Short Name | ShortName | Concept | string | 8 | Optional  |
| Credit Limit | CreditLimit | 5000 | double | - | Optional | Defaults to 0 if not provided when creating a new supplier. The value must be positive. |
| Currency | Currency | GBP | string | 3 | Optional | Defaults to the base currency from Currencies and Exchange Rate Settings in the Accounting System Manager if not provided. This field can only be set when creating a new supplier. |
| Address [Line 1] | Address1 | 66 New Street | string | 60 | Optional |
| Address [Line 2] | Address2 | Ridgeway | string | 60 | Optional |
| Address [Line 3] | Address3 | string | 60 | Optional |
| Address [Line 4] | Address4 | string | 60 | Optional |
| City | Town | Newcastle upon Tyne | string | 60 | Optional  | Can only be set if 'Use Segmented Addresses' is enabled in System Settings in the Accounting System Manager. |
| County  | County | Tyne &amp; Wear  | string  | 60  | Optional  | Can only be set if 'Use Segmented Addresses' is enabled in System Settings in the Accounting System Manager. |
| Post Code | Postcode | NE1 4GF | string | 10 | Optional |
| Country | Country | GB | string | 2 | Optional  | Use the 2 letter ISO country code as the value. |
| Telephone | Telephone | 0191 643 4343 | string  | 30  | Optional |
| Fax | Fax | 0191 643 4345 | string  | 30  | Optional  |
| Website | Website | http://www.zynk.com/ | string  | 200 | Optional  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <AccountReference>CON001</AccountReference>
      <CompanyName>Concept Stationery Supplies</CompanyName>
      <ShortName>Concept</ShortName>
      <CreditLimit>5000</CreditLimit>
      <SupplierInvoiceAddress>
        <Address1>66 New Street</Address1>
        <Address2>Ridgeway</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE1 4GF</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Telephone>0191 643 4343</Telephone>
        <Fax>0191 643 4345</Fax>
        <Website>www.zynk.com</Website>
      </SupplierInvoiceAddress>
      <Currency>GBP</Currency>
    </Supplier>
  </Suppliers>
</Company>
```

## Contacts
The information below can be specified on the Contacts tab in Sage. The default contact is specified as part of the SupplierInvoiceAddress in the XML. Any other contacts are specified in the Contacts section of the XML. The telephone, mobile, fax, email and website are only used to set or update the default value for the corresponding fields in Sage, multiple values cannot be specified. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes  |
| --- | --- | --- | --- | --- | --- | --- |
| Salutation | Title  | Mr  | string  | 3 | Optional  | If the salutation does not already exist in Sage, it will be created. |
| First Name | Forename  | Mark | string  | 60 | Optional  |
| Middle Name | Middlename  | E  | string  | 60 | Optional  |
| Last Name | Surname  | Ramsay | string  | 60 | Optional  |
| Telephone | Telephone | 0191 643 4343 | string  | 30  | Optional |
| Mobile | Mobile | 0191 643 4344  | string  | 30  | Optional  |
| Fax | Fax | 0191 643 4345 | string  | 30  | Optional  |
| Email | Email | support@zynk.com | string | 200 | Optional  |
| Website | Website | http://www.zynk.com/ | string  | 200 | Optional  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <SupplierInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Mark</Forename>
        <Middlename>E</Middlename>
        <Surname>Ramsay</Surname>
        <Telephone>0191 643 4343</Telephone>
        <Mobile>0191 643 4344</Mobile>
        <Fax>0191 643 4345</Fax>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
      </SupplierInvoiceAddress>
      <Contacts>
        <Contact>
          <Title>Mr</Title>
          <Forename>Joe</Forename>
          <Middlename>E</Middlename>
          <Surname>Harrison</Surname>
          <Telephone>0845 123 2920</Telephone>
          <Mobile>0777 777 7777</Mobile>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <Website>www.zynk.com</Website>
        </Contact>
      </Contacts>
    </Supplier>
  </Suppliers>
</Company>
```

## Trading
The information below can be specified on the Trading tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes  |
| --- | --- | --- | --- | --- | --- | --- |
| Country Code | Country | GB | string  | 2 | Optional  | Use the 2 letter ISO country code as the value. |
| Default Tax Code | TaxCode | 1 | int | -  | Optional  | Will use the default from the Purchase Ledger settings if not provided. |
| Tax Number | VatNumber | GB988 3453 23 | string  | 30  | Optional |
| Default Nominal Code - Account Number | NominalCode | 4002 | string  | 30  | Optional  | Will use the default from Sage if not provided. |
| Default Nominal Code - CC | CostCentre | TES | string  | 3 | Optional  | Will use the default from Sage if not provided. |
| Default Nominal Code - Dept | Department | DEP | string | 3 | Optional  | Will use the default from Sage if not provided. |
| Analysis Code | Name | TEST | string  | 60 | Optional  | If the analysis code does not already exist in Sage, it will not be set on the supplier. |
| Value | Value | 123 | string  | 60 | Optional  | If the analysis code does not already exist in Sage, it will not be set on the supplier. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <SupplierInvoiceAddress>
        <Country>GB</Country>
      </SupplierInvoiceAddress>
      <TaxCode>1</TaxCode>
      <VatNumber>GB988 3453 23</VatNumber>
      <NominalCode>4002</NominalCode>
      <CostCentre>TES</CostCentre>
      <Department>DEP</Department>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>TEST</Name>
          <Value>123</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </Supplier>
  </Suppliers>
</Company>
```

## Credit
The information below can be specified on the Credit tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  | Notes  |
| --- | --- | --- | --- | --- | --- | --- |
| Terms Agreed | TermsAgreed | true | bool | -  | Optional  | Will use the default from the Purchase Ledger settings if not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <TermsAgreed>true</TermsAgreed>
    </Supplier>
  </Suppliers>
</Company>
```