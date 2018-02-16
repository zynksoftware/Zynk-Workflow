---
slug: zynk-csv-to-zynk-xml
redirect_from: "/article/384-zynk-csv-to-zynk-xml"
title: Zynk CSV to Zynk XML
---
This task allows you to provide a .csv file with Zynk element headers to be automatically transformed in to the Zynk XML format. The data types currently supported are Customers, Suppliers, Sales Orders, Purchase Orders, Invoices (Sage 50 only), Stock Records, Stock Transactions and Transactions.

This task supports subsequent imports in to Sage 50 and Sage 200.

## Settings
### Input File
_Required_  
The input CSV file containing the data you would like to transform.

### Mapping
_Required_  
This is where you specify the format of data you'd like to be mapped.

### Output File
_Required_  
The XML file the result should be saved to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Below is an example of a Zynk customer in .csv format.

```csv
Id, AccountReference, CompanyName, CreditLimit, Currency, Title, Forename, Surname, Company, Address1, Address2, Address3, Address4, Town, Postcode, County, Country, Telephone, Email, Website, DefaultDelTitle, DefaultDelForename, DefaultDelSurname, DefaultDelCompany, DefaultDelAddress1, DefaultDelAddress2, DefaultDelAddress3, DefaultDelAddress4, DefaultDelTown, DefaultDelPostcode, DefaultDelCounty, DefaultDelCountry, DefaultDelTelephone, DefaultDelEmail, DefaultDelWebsite, TermsAgreed, TaxCode, OverrideTaxCode, VatNumber, NominalCode, CostCentre, Department, Contact1Title, Contact1Forename, Contact1Middlename, Contact1Surname, Contact1Telephone, Contact1Mobile, Contact1Fax, Contact1Email, Contact1Website, Contact2Title, Contact2Forename, Contact2Middlename, Contact2Surname, Contact2Telephone, Contact2Mobile, Contact2Fax, Contact2Email, Contact2Website, DelAddress1Company, DelAddress1Title, DelAddress1Forename, DelAddress1Middlename, DelAddress1Surname, DelAddress1Address1, DelAddress1Address2, DelAddress1Address3, DelAddress4, DelAddress1Town, DelAddress1County, DelAddress1Postcode, DelAddress1Country, DelAddress1Telephone, DelAddress1Fax, DelAddress1Email, DelAddress1VatNumber, DelAddress1TaxCode, DelAddress2Company, DelAddress2Title, DelAddress2Forename, DelAddress2Middlename, DelAddress2Surname, DelAddress2Address1, DelAddress2Address2, DelAddress2Address3, DelAddress4, DelAddress2Town, DelAddress2County, DelAddress2Postcode, DelAddress2Country, DelAddress2Telephone, DelAddress2Fax, DelAddress2Email, DelAddress2VatNumber, DelAddress2TaxCode, AnalysisCode1Name, AnalysisCode1Value, AnalysisCode2Name, AnalysisCode2Value, IsActive
123, ZYNK01, Zynk Software Limited, 1000, GBP, Mr, Joe, Harrison, Zynk Software Limited, Nelson House, Fleming Business Centre, Jesmond, , Newcastle upon-Tyne, NE23AE, Tyne and Wear, GB, 0845 123 2920, support@zynk.com, www.zynk.com, Mr, Adam, Nicholson, Flow Digital Limited, Nelson House, Fleming Business Centre, Jesmond, , Newcastle upon-Tyne, NE23AE, Tyne and Wear, GB, 0845 004 6030, hello@flow.co.uk, www.flow.co.uk, true, 1, false, , 4000, ADM, DEP, Mr, Andrew, , Snape, 0845 123 2920, , 0845 123 2921, support@zynk.com, www.zynk.com, Mr, Chris, , Baker, 0845 123 2920, , 0845 123 2921, support@zynk.com, www.zynk.com, Zynk Software Limited, Mr, Chris, , Hotchkiss, 8 Test Road, Test House, , , Newcastle upon-Tyne, Tyne and Wear, NE2 3AR, GB, 0845 123 2920, 0845 123 2921, support@zynk.com, , 1, Zynk Software Limited, Mr, Adam, , Wardle, 900 Test Road, Test House, , , Newcastle upon-Tyne, Tyne and Wear, NE2 3BC, GB, 0845 123 2920, 0845 123 2921, support@zynk.com, , 1, TestAnalysis1, TestEntry1, TestAnalysis2, TestEntry2, false
456, ZYNK02, Zynk Software Limited, 1000, GBP, Mr, Joe, Harrison, Zynk Software Limited, Nelson House, Fleming Business Centre, Jesmond, , Newcastle upon-Tyne, NE23AE, Tyne and Wear, GB, 0845 123 2920, support@zynk.com, www.zynk.com, Mr, Adam, Nicholson, Flow Digital Limited, Nelson House, Fleming Business Centre, Jesmond, , Newcastle upon-Tyne, NE23AE, Tyne and Wear, GB, 0845 004 6030, hello@flow.co.uk, www.flow.co.uk, true, 1, false, , 4000, ADM, DEP, Mr, Andrew, , Snape, 0845 123 2920, , 0845 123 2921, support@zynk.com, www.zynk.com, Mr, Chris, , Baker, 0845 123 2920, , 0845 123 2921, support@zynk.com, www.zynk.com, Zynk Software Limited, Mr, Chris, , Hotchkiss, 8 Test Road, Test House, , , Newcastle upon-Tyne, Tyne and Wear, NE2 3AR, GB, 0845 123 2920, 0845 123 2921, support@zynk.com, , 1, Zynk Software Limited, Mr, Adam, , Wardle, 900 Test Road, Test House, , , Newcastle upon-Tyne, Tyne and Wear, NE2 3BC, GB, 0845 123 2920, 0845 123 2921, support@zynk.com, , 1, TestAnalysis1, TestEntry1, TestAnalysis2, TestEntry2, false
```

And this will return the following output

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>ZYNK01</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <CreditLimit>1000</CreditLimit>
      <Currency>GBP</Currency>
      <Company>Zynk Software Limited</Company>
      <DefaultDelCompany>Flow Digital Limited</DefaultDelCompany>
      <TermsAgreed>true</TermsAgreed>
      <TaxCode>1</TaxCode>
      <OverrideTaxCode>false</OverrideTaxCode>
      <VatNumber />
      <NominalCode>4000</NominalCode>
      <CostCentre>ADM</CostCentre>
      <Department>DEP</Department>
      <IsActive>false</IsActive>
      <CustomerInvoiceAddress>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Address4></Address4>
        <Town>Newcastle upon-Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE23AE</Postcode>
        <Country>GB</Country>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Telephone>0845 123 2920</Telephone>
        <Website>www.zynk.com</Website>
        <Email>support@zynk.com</Email>
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Address4></Address4>
        <Town>Newcastle upon-Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE23AE</Postcode>
        <Country>GB</Country>
        <Title>Mr</Title>
        <Forename>Adam</Forename>
        <Surname>Nicholson</Surname>
        <Telephone>0845 004 6030</Telephone>
        <Website>www.flow.co.uk</Website>
        <Email>hello@flow.co.uk</Email>
      </CustomerDeliveryAddress>
      <DeliveryAddresses>
        <Contact>
          <Title>Zynk Software Limited</Title>
          <Title>Mr</Title>
          <Forename>Chris</Forename>
          <Middlename></Middlename>
          <Surname>Hotchkiss</Surname>
          <Address1>8 Test Road</Address1>
          <Address2>Test House</Address2>
          <Address3></Address3>
          <Town>Newcastle upon-Tyne</Town>
          <County>Tyne and Wear</County>
          <Postcode>NE2 3AR</Postcode>
          <Country>GB</Country>
          <Telephone>0845 123 2920</Telephone>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <VatNumber></VatNumber>
          <TaxCode>1</TaxCode>
        </Contact>
        <Contact>
          <Title>Zynk Software Limited</Title>
          <Title>Mr</Title>
          <Forename>Adam</Forename>
          <Middlename></Middlename>
          <Surname>Wardle</Surname>
          <Address1>900 Test Road</Address1>
          <Address2>Test House</Address2>
          <Address3></Address3>
          <Town>Newcastle upon-Tyne</Town>
          <County>Tyne and Wear</County>
          <Postcode>NE2 3BC</Postcode>
          <Country>GB</Country>
          <Telephone>0845 123 2920</Telephone>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <VatNumber></VatNumber>
          <TaxCode>1</TaxCode>
        </Contact>
      </DeliveryAddresses>
      <Contacts>
        <Contact>
          <Title>Mr</Title>
          <Forename>Andrew</Forename>
          <Middlename></Middlename>
          <Surname>Snape</Surname>
          <Telephone>0845 123 2920</Telephone>
          <Mobile></Mobile>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <Website>www.zynk.com</Website>
        </Contact>
        <Contact>
          <Title>Mr</Title>
          <Forename>Chris</Forename>
          <Middlename></Middlename>
          <Surname>Baker</Surname>
          <Telephone>0845 123 2920</Telephone>
          <Mobile></Mobile>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <Website>www.zynk.com</Website>
        </Contact>
      </Contacts>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>TestAnalysis1</Name>
          <Value>TestEntry1</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>TestAnalysis2</Name>
          <Value>TestEntry2</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </Customer>
    <Customer>
      <Id>456</Id>
      <AccountReference>ZYNK02</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <CreditLimit>1000</CreditLimit>
      <Currency>GBP</Currency>
      <Company>Zynk Software Limited</Company>
      <DefaultDelCompany>Flow Digital Limited</DefaultDelCompany>
      <TermsAgreed>true</TermsAgreed>
      <TaxCode>1</TaxCode>
      <OverrideTaxCode>false</OverrideTaxCode>
      <VatNumber />
      <NominalCode>4000</NominalCode>
      <CostCentre>ADM</CostCentre>
      <Department>DEP</Department>
      <IsActive>false</IsActive>
      <CustomerInvoiceAddress>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Address4></Address4>
        <Town>Newcastle upon-Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE23AE</Postcode>
        <Country>GB</Country>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Telephone>0845 123 2920</Telephone>
        <Website>www.zynk.com</Website>
        <Email>support@zynk.com</Email>
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Address4></Address4>
        <Town>Newcastle upon-Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE23AE</Postcode>
        <Country>GB</Country>
        <Title>Mr</Title>
        <Forename>Adam</Forename>
        <Surname>Nicholson</Surname>
        <Telephone>0845 004 6030</Telephone>
        <Website>www.flow.co.uk</Website>
        <Email>hello@flow.co.uk</Email>
      </CustomerDeliveryAddress>
      <DeliveryAddresses>
        <Contact>
          <Title>Zynk Software Limited</Title>
          <Title>Mr</Title>
          <Forename>Chris</Forename>
          <Middlename></Middlename>
          <Surname>Hotchkiss</Surname>
          <Address1>8 Test Road</Address1>
          <Address2>Test House</Address2>
          <Address3></Address3>
          <Town>Newcastle upon-Tyne</Town>
          <County>Tyne and Wear</County>
          <Postcode>NE2 3AR</Postcode>
          <Country>GB</Country>
          <Telephone>0845 123 2920</Telephone>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <VatNumber></VatNumber>
          <TaxCode>1</TaxCode>
        </Contact>
        <Contact>
          <Title>Zynk Software Limited</Title>
          <Title>Mr</Title>
          <Forename>Adam</Forename>
          <Middlename></Middlename>
          <Surname>Wardle</Surname>
          <Address1>900 Test Road</Address1>
          <Address2>Test House</Address2>
          <Address3></Address3>
          <Town>Newcastle upon-Tyne</Town>
          <County>Tyne and Wear</County>
          <Postcode>NE2 3BC</Postcode>
          <Country>GB</Country>
          <Telephone>0845 123 2920</Telephone>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <VatNumber></VatNumber>
          <TaxCode>1</TaxCode>
        </Contact>
      </DeliveryAddresses>
      <Contacts>
        <Contact>
          <Title>Mr</Title>
          <Forename>Andrew</Forename>
          <Middlename></Middlename>
          <Surname>Snape</Surname>
          <Telephone>0845 123 2920</Telephone>
          <Mobile></Mobile>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <Website>www.zynk.com</Website>
        </Contact>
        <Contact>
          <Title>Mr</Title>
          <Forename>Chris</Forename>
          <Middlename></Middlename>
          <Surname>Baker</Surname>
          <Telephone>0845 123 2920</Telephone>
          <Mobile></Mobile>
          <Fax>0845 123 2921</Fax>
          <Email>support@zynk.com</Email>
          <Website>www.zynk.com</Website>
        </Contact>
      </Contacts>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>TestAnalysis1</Name>
          <Value>TestEntry1</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>TestAnalysis2</Name>
          <Value>TestEntry2</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </Customer>
  </Customers>
</Company>
```