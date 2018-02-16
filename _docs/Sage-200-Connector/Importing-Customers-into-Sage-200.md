---
slug: importing-customers-into-sage-200
redirect_from: "/article/681-importing-customers-into-sage-200"
title: Importing Customers into Sage 200
---
This task will import customers in Zynk XML format into Sage 200 as customers. If the customer already exists (based on finding a matching account reference) it will be updated, otherwise a new customer will be created.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed customers in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported customers in Zynk XML format.

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
The list of fields to use to try and find an existing account in Sage which matches with the customer in the input file. These settings will only be used if there is no account reference provided for the customer in the input file. When multiple fields are selected, only customers in Sage where the value of all fields matches those in the input file will be considered a match. The following fields are supported:	

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
A sample input file for creating a customer is shown below. See [Sage 200 Customer XML](sage-200-customer-xml) for more details on the Zynk XML Customer format for Sage 200.

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <Id>123</Id>
      <AccountReference>JOE001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
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