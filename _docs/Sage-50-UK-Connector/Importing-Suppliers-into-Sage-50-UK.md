---
slug: importing-suppliers-into-sage-50-uk
redirect_from: "/article/419-importing-suppliers-into-sage-50-uk"
title: Importing Suppliers into Sage 50 UK
---
This task will import suppliers to Sage 50 that is supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Alphabetic Length
_Required_  
Used when auto generating account references. Controls the number of alphabetic characters to use in the generated account reference (e.g. 3 may produce an account reference starting with ABC).

### Auto Generate Account Ref
_Required_  
Set this to True to have the task automatically generate an account reference for the customer if it is not provided in the input file, and is not found in the truth table based on the customer Id. Set to False to prevent new account references being generated automatically.

### Numeric Length
_Required_  
Used when auto generating account references. Controls the number of numeric characters to use in the generated account reference (e.g. 3 may produce an account reference ending in 001).

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.  

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Supplier XML](sage-50-uk-supplier-xml):  

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Suppliers>
    <Supplier>
      <Id>123</Id>
      <CompanyName>Internetware</CompanyName>
      <AccountReference>INTE001</AccountReference>
      <SupplierInvoiceAddress>
        <Title />
        <Forename>Support</Forename>
        <Surname>Person</Surname>
        <Company>Internetware</Company>
        <Address1>6-8 Charlotte Square</Address1>
        <Address2>i6 Building</Address2>
        <Address3 />
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Mobile />
        <Email>support@internetware.co.uk</Email>
      </SupplierInvoiceAddress>
      <SupplierDeliveryAddress>
        <Title />
        <Forename>Support</Forename>
        <Surname>Person</Surname>
        <Company>Internetware</Company>
        <Address1>6-8 Charlotte Square</Address1>
        <Address2>i6 Building</Address2>
        <Address3 />
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Mobile />
        <Email>support@internetware.co.uk</Email>
      </SupplierDeliveryAddress>
      <Currency>GBP</Currency>
      <TermsAgreed>1</TermsAgreed>
      <AccountStatus>1</AccountStatus>
    </Supplier>
  </Suppliers>
</Company>
```