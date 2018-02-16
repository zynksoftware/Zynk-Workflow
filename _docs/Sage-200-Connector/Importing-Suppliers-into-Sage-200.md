---
slug: importing-suppliers-into-sage-200
redirect_from: "/article/443-import-suppliers"
title: Importing Suppliers into Sage 200
---
This task will import supplier records in Zynk XML format to the Purchase Ledger in Sage 200. If the supplier already exists (based on finding a matching account reference) it will be updated, otherwise a new supplier will be created.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed suppliers in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported suppliers in Zynk XML format.

### Auto Generate References
_Required_  

 * **Auto generate Account References** - Set this to True to have the task auto generate account references where an account reference is not provided in the input file. Set to False if an account reference generation is not required.
 * **Alphabetic Length** - Used with auto-generated Account Ref - specify the number of alphabetic characters to use e.g. 3 = ABC
 * **Numeric Length** - Used with auto-generated Account Ref - specify the number of numeric characters to use e.g. 3 = 001
 * **Account Reference Convention** - Select a method for generating the alphabetic part of the account reference. The following options are available:	
   - CompanyOtherwiseFullName - The company name will be used if provided, otherwise the customers full name.
   - CompanyOtherwiseForenameSurname - The company name will be used if provided, otherwise the customers forename followed by surname.
   - CompanyOtherwiseSurnameForename - The company name will be used if provided, otherwise the customers surname followed by forename.
   - ForenameSurname - The customers forename followed by surname.
   - SurnameForename - The customers surname followed by forename.
 * **Mask** - A mask to apply to the auto generated account references. This can be used to add prefixes or suffixes to the account references. Question marks are replaced by auto generated characters, as determined by the Alphabetic Length and Numeric Length settings, any other characters will be included in the generated account reference. For example, the mask 	`A??????` would ensure that the account references always start with the letter A.
 * **Regular Expression** - The regular expression to use for stripping out undesired characters from the generated account reference. Any character which matches the regular expression will be removed. For example, 	`\s*` would be used to strip out all spaces.

### Match Accounts On
_Optional_  
The list of fields to use to try and find an existing account in Sage which matches with the supplier in the input file. These settings will only be used if there is no account reference provided for the supplier in the input file. When multiple fields are selected, only suppliers in Sage where the value of all fields matches those in the input file will be considered a match. The following fields are supported:	

 * Company Name
 * Telephone
 * Mobile
 * Fax
 * Email
 * Website
 * Postcode

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a supplier is shown below. See our [Sage 200 Supplier XML](sage-200-supplier-xml) for more details on the Zynk XML Supplier format for Sage 200.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Suppliers>
    <Supplier>
      <Id>1</Id>
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
        <County />
        <Country>GB</Country>
        <Telephone>0191 643 4343</Telephone>
        <Fax>0191 643 4345</Fax>
        <Mobile>0191 643 4344</Mobile>
        <Email>newbusinessadvice@sage.com</Email>
        <Website />
        <Notes />
      </SupplierInvoiceAddress>
      <Currency>GBP</Currency>
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