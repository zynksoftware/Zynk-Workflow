---
slug: exporting-suppliers-from-sage-200
redirect_from: "/article/435-exporting-suppliers-from-sage-200"
title: Exporting Suppliers from Sage 200
---
This task will export suppliers in [Sage 200 XML](sage-200-xml) format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Characters To Cleanse
_Optional_  
A list of characters to remove from the output file. Use this if your Sage data contains characters that are not valid for XML documents (e.g. 	`&#x0;`).

### Export Settings
_Optional_  

 * **Date Created** - Used when exporting new records. Only records created after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 * **Op Lock** - Used when exporting modified records. Only records where the Op Lock is greater than this value will be exported. The value will update automatically each time the task runs.

### Query Settings
_Optional_  

 * **Columns** - Used to enter the column names to export from the Sage database. Be sure to include the table name eg. `[SLCustomerAccount].[CustomerAccountNumber]`
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported. 
  
### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The file to save the exported records to, in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Suppliers>
    <Supplier>
      <Id>1234</Id>
      <UniqueId>1620</UniqueId>
      <CompanyName>Zynk Software</CompanyName>
      <AccountReference>ZYN001</AccountReference>
      <VatNumber>GB12345</VatNumber>
      <CreditLimit>1000</CreditLimit>
      <Balance>270</Balance>
      <SupplierInvoiceAddress>
        <Title>Mr.</Title>
        <Forename>Joe</Forename>
        <Surname>Bloggs</Surname>
        <Company>Zynk Software</Company>
        <Description>Joe Bloggs - NE2 3AE</Description>
        <Address1>Flemming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Address3 />
        <Town>Newcastle</Town>
        <Postcode>NE2 3AE</Postcode>
        <Country> </Country>
        <Telephone>0845 123 2920</Telephone>
        <Fax />
        <Mobile />
        <Email>support@example.com</Email>
        <ContactName>Joe Bloggs</ContactName>
        <Website>www.example.com</Website>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </SupplierInvoiceAddress>
      <SupplierDeliveryAddress>
        <Title>Mr.</Title>
        <Forename>Joe</Forename>
        <Surname>Bloggs</Surname>
        <Company>Zynk Software</Company>
        <Description>Joe Bloggs - NE2 3AE</Description>
        <Address1>Flemming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Address3 />
        <Town>Newcastle</Town>
        <Postcode>NE2 3AE</Postcode>
        <Country> </Country>
        <Telephone>0845 123 2920</Telephone>
        <Fax />
        <Mobile />
        <Email>support@example.com</Email>
        <ContactName>Joe Bloggs</ContactName>
        <Website>www.example.com</Website>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </SupplierDeliveryAddress>
      <Currency>GBP</Currency>
      <TermsAgreed>true</TermsAgreed>
      <AccountStatus xsi:nil="true" />
      <Priority xsi:nil="true" />
      <ShortName>Internet</ShortName>
      <Contacts />
      <TaxCode>1</TaxCode>
      <Banks />
      <CustomFields />
    </Supplier>
  </Suppliers>
</Company>
```
