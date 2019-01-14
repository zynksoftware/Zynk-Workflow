---
slug: sage-200-customer-xml
title: Sage 200 Customer XML
---
Import Customers allows you to create new and update existing customers in Sage 200. We recommend that the Id field be populated by the unique id of the customers from the external system, Zynk uses this field to track customers already imported to prevent duplicates being created in Sage, and to allow sales orders to be created without the customer's account reference (the CustomerId is provided instead, which is useful when the external system does not store the account reference).   

Any fields not documented below are not supported with our imports. Examples of where in the XML the fields should appear are shown in the samples below.  

Sample import file for creating a customer:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <ShortName>ZYNK</ShortName>
      <CreditLimit>1000</CreditLimit>
      <Currency>GBP</Currency>
      <CustomerInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
      </CustomerDeliveryAddress>
      <TermsAgreed>true</TermsAgreed>
      <TaxCode>4</TaxCode>
      <OverrideTaxCode>false</OverrideTaxCode>
      <VatNumber>796 5763 59</VatNumber>
      <NominalCode>4000</NominalCode>
      <CostCentre>INT</CostCentre>
      <Department>Dep</Department>
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
      <DeliveryAddresses>
        <Contact>
          <Id>5230</Id>
          <Company>internetware</Company>
          <Title>Mr</Title>
          <Forename>Joe</Forename>
          <Middlename>E</Middlename>
          <Surname>Harrison</Surname>
          <Address1>Nelson House</Address1>
          <Address2>Fleming Business Centre</Address2>
          <Address3>Jesmond</Address3>
          <Address4></Address4>
          <Town>Newcastle upon Tyne</Town>
          <County>Tyne &amp; Wear </County>
          <Postcode>NE2 3AE</Postcode>
          <Country>GB</Country>
          <Telephone>0845 123 2920</Telephone>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <VatNumber>796 5763 59</VatNumber>
          <TaxCode>1</TaxCode>
        </Contact>
      </DeliveryAddresses>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Web Customer</Name>
          <Value>true</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </Customer>
  </Customers>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read. The whole structure of the Company schema is used below as a reference of where fields should be in the XML.

## Company
The information below can be specified on the Company tab in Sage. Depending on your configuration at the Task Settings level in Zynk, you may not need to specify an account reference for every customer. This applies when the 'Auto Generate References' or 'Match Accounts On' settings are enabled.

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | Id | 123 | string | 255 | Optional | Used internally by Zynk for duplicate prevention and when importing sales orders. |
| A/C Ref | AccountReference | JOE001 | string | 8 | Optional | Required when 'Auto Generate References' and 'Match Accounts On' settings are disabled. |
| Name | CompanyName | Zynk Software Limited | string | 60 | Optional  | If a CompanyName is not provided, it will default to the Title, Forename, Middlename and Surname. |
| Short Name | ShortName | ZYNK | string | 8 | Optional  |
| Credit Limit | CreditLimit | 1000 | double | - | Optional | Defaults to 0 if not provided. |
| Currency | Currency | GBP | string | 3 | Optional | This field can only be set when creating a new customer. Defaults to the base currency from Accounting System Manager -> Currencies and Exchange Rates if not provided.|
| Address [Line 1] | Address1 | Nelson House | string | 60 | Optional |
| Address [Line 2] | Address2 | Fleming Business Centre | string | 60 | Optional |
| Address [Line 3] | Address3 | Jesmond | string | 60 | Optional |
| Address [Line 4] | Address4 | string | 60 | Optional |
| City | Town | Newcastle upon Tyne | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| County | County | Tyne &amp; Wear | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| Post Code | Postcode | NE2 3AE | string | 10 | Optional |
| Country | Country | GB | string | 2 | Optional | Use the 2 letter ISO country code as the value. |
| Telephone | Telephone | 0845 123 2920 | string | 30 | Optional |
| Fax | Fax | 0845 123 2921 | string | 30 | Optional |
| Website | Website | http://www.zynk.com/ | string | 200 | Optional |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <ShortName>ZYNK</ShortName>
      <CreditLimit>1000</CreditLimit>
      <Currency>GBP</Currency>
      <CustomerInvoiceAddress>
        <Company>Zynk Software Limited</Company>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
      </CustomerInvoiceAddress>
    </Customer>
  </Customers>
</Company>
```

## Contacts
The information below can be specified on the Contacts tab in Sage. The default contact is specified as part of the CustomerInvoiceAddress in the XML. Any other contacts are specified in the Contacts section of the XML. The telephone, mobile, fax, email and website are only used to set or update the default value for the corresponding fields in Sage, multiple values cannot be specified.

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Salutation | Title | Mr | string | 3 | Optional | If the salutation does not already exist in Sage, it will be created. |
| First Name | Forename | Joe | string | 60 | Optional |
| Middle Name | Middlename  | E | string | 60 | Optional |
| Last Name | Surname | Harrison | string | 60 | Optional |
| Telephone | Telephone | 0845 123 2920 | string | 30 | Optional |
| Mobile | Mobile | 0777 777 7777 | string | 30 | Optional |
| Fax | Fax | 0845 123 2921 | string | 30 | Optional |
| Email | Email | support@zynk.com | string | 200 | Optional |
| Website | Website | http://www.zynk.com/ | string | 200 | Optional |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <CustomerInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Middlename>E</Middlename>
        <Surname>Harrison</Surname>
        <Telephone>0845 123 2920</Telephone>
        <Mobile>0777 777 7777</Mobile>
        <Fax>0845 123 2921</Fax>
        <Email>support@zynk.com</Email>
        <Website>www.zynk.com</Website>
      </CustomerInvoiceAddress>
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
    </Customer>
  </Customers>
</Company>
```

## Trading
The information below can be specified on the Trading tab in Sage.

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Country Code | CountryCode | GB | string | 2 | Optional | Use the 2 letter ISO country code as the value. |
| Default Tax Code | TaxCode | 1 | int | - | Optional | Will use the default from the Sales Ledger settings if not provided. |
| Use Tax Code as SOP Default | OverrideTaxCode | false | bool | - | Optional |
| Tax Number | VatNumber | 796 5763 59 | string | 30 | Optional |
| Keep Transactions For | KeepTransactionsFor | 24 | int | - | Optional | |
| Order priority | OrderPriority | A | string | 1 | Optional | |
| Default Nominal Code - Account Number | NominalCode | 4000 | string | 30 | Optional | Will use the default from Sage if not provided. |
| Default Nominal Code - CC | CostCentre | INT | string | 30 | Optional | Will use the default from Sage if not provided. |
| Default Nominal Code - Dept | Department | Dep | string | 30 | Optional | Will use the default from Sage if not provided. |
| Analysis Codes - Name | Name | Web Customer | string | 60 | Optional | If the analysis code does not already exist in Sage, it will not be set on the customer. |
| Analysis Codes - Value | Value | true | string | 60 | Optional | If the analysis code does not already exist in Sage, it will not be set on the customer. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <CountryCode>GB</CountryCode>
      <TaxCode>4</TaxCode>
      <OverrideTaxCode>false</OverrideTaxCode>
      <VatNumber>796 5763 59</VatNumber>
      <KeepTransactionsFor>24</KeepTransactionsFor>
      <OrderPriority>A</OrderPriority>
      <NominalCode>4000</NominalCode>
      <CostCentre>INT</CostCentre>
      <Department>Dep</Department>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Web Customer</Name>
          <Value>true</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </Customer>
  </Customers>
</Company>
```

## Payment
The information below can be specified on the Payment tab in Sage. 

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Payment terms | PaymentTermsDays | 30 | int | - | Optional | |
| Payment terms - from | PaymentTermsBasis | PaymentDueFromDocumentDate | enum | - | Optional | Available values: PaymentDueFromCalendarMonth, PaymentDueFromStartOfMonth, PaymentDueFromEndOfMonth, PaymentDueFromDocumentDate |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <PaymentTermsDays>30</PaymentTermsDays>
      <PaymentTermsBasis>PaymentDueFromDocumentDate</PaymentTermsBasis>
    </Customer>
  </Customers>
</Company>
```

## Credit
The information below can be specified on the Credit tab in Sage. 

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Terms Agreed | TermsAgreed | true | bool | - | Optional | Will use the default from the Sales Ledger settings if not provided. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <TermsAgreed>true</TermsAgreed>
    </Customer>
  </Customers>
</Company>
```

## Documents  
The information below can be specified on the Documents tab in Sage. 

| Sage Field | XML Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| Price Band | PriceListReference | Standard | string | 20 | Optional |
| Discount Group | DiscountGroupReference | Trade | string | 20 | Optional |
| Order Value Discount | OrderValueDiscountReference | 10% Off orders over 1000 | string | 20 | Optional |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <PriceListReference>Standard</PriceListReference>
      <DiscountGroupReference>Trade</DiscountGroupReference>
      <OrderValueDiscountReference>10% Off orders over 1000</OrderValueDiscountReference>
    </Customer>
  </Customers>
</Company>
```

## Delivery Addresses
The information below can be specified under Sales Order Processing -> SOP Maintenance -> Customer Delivery Addresses in Sage. We recommend that the Id field be populated by the unique id of the delivery address from the external system, Zynk uses this field to track delivery addresses already imported to prevent duplicates being created in Sage.

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| - | Id | 5230 | string | 30 | Optional |
| Postal Name | Company | Zynk Software Limited | string | 60 | Optional | If a value is not provided for this field, it will default to the Title, Forename, Middlename, Surname and Suffix. |
| - | Title | Mr | string | - | Optional | Only used if Company is not provided. |
| - | Forename | Joe | string | - | Optional | Only used if Company is not provided. |
| - | Middlename | E | string | - | Optional | Only used if Company is not provided. |
| - | Surname | Harrison | string | - | Optional | Only used if Company is not provided. |
| Address [Line 1] | Address1 | Nelson House | string | 60 | Optional |
| Address [Line 2] | Address2 | Fleming Business Centre | string | 60 | Optional |
| Address [Line 3] | Address3 | Jesmond | string | 60 | Optional |
| Address [Line 4] | Address4 | string | 60 | Optional |
| City | Town | Newcastle upon Tyne | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| County | County | Tyne &amp; Wear | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| Post Code | Postcode | NE2 3AE | string | 10 | Optional |
| Country | Country | GB | string | 2 | Optional |
| Telephone | Telephone | 0845 123 2920 | string | 30 | Optional |
| Fax | Fax | 0845 123 2921 | string | 30 | Optional |
| E-mail | Email | support@zynk.com | string | 255 | Optional |
| Tax Number | VatNumber | 796 5763 59 | string | 30 | Optional |
| Tax Code | TaxCode | 1 | int | - | Optional |
| Country Code | Country | GB | string | 2 | Optional | Use the 2 letter ISO country code as the value. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>      
      <DeliveryAddresses>
        <Contact>
          <Id>5230</Id>
          <Company>internetware</Company>
          <Title>Mr</Title>
          <Forename>Joe</Forename>
          <Middlename>E</Middlename>
          <Surname>Harrison</Surname>
          <Address1>Nelson House</Address1>
          <Address2>Fleming Business Centre</Address2>
          <Address3>Jesmond</Address3>
          <Address4></Address4>
          <Town>Newcastle upon Tyne</Town>
          <County>Tyne &amp; Wear</County>
          <Postcode>NE2 3AE</Postcode>
          <Country>GB</Country>
          <Telephone>0845 123 2920</Telephone>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <VatNumber>796 5763 59</VatNumber>
          <TaxCode>1</TaxCode>
        </Contact>
      </DeliveryAddresses>
    </Customer>
  </Customers>
</Company>
```

## Account Status
The information below can be specified on the Account Status screen in Sage. 

| Sage Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| On Hold | AccountOnHold | true | bool | - | Optional |  |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>      
      <AccountOnHold>true</AccountOnHold>
    </Customer>
  </Customers>
</Company>
```
