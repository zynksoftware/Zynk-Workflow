---
slug: exporting-suppliers-from-sage-50-uk
redirect_from: "/article/407-exporting-suppliers-from-sage-50-uk"
title: Exporting Suppliers from Sage 50 UK
---
This task will export suppliers from Sage 50 in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.
 
### Query Settings
_Optional_  

 * **Columns** - Allows you to specify additional columns to include in the export.  Additional fields will be exported in the CustomFields section in the XML.  Be sure to include the table name for each of the additional columns provided eg. `[STOCK].[QTY_LAST_STOCK_TAKE]`.  If the table that the column you are trying to retrieve is not used by the standard export, you will need to add the table to Joins.
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported.

### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Suppliers>
    <Supplier>
      <UniqueId>CON001</UniqueId>
      <CompanyName>Concept Stationery Supplies</CompanyName>
      <AccountReference>CON001</AccountReference>
      <VatNumber>GB988 3453 23</VatNumber>
      <CreditLimit>17000</CreditLimit>
      <Balance>1644.39</Balance>
      <SupplierInvoiceAddress>
        <Title />
        <Forename>Mark</Forename>
        <Surname>Ramsay</Surname>
        <Company>Concept Stationery Supplies</Company>
        <Description>Mark Ramsay - NE1 4GF</Description>
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
        <Website>www.sage.co.uk</Website>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <TradeContact>Anthony Thane</TradeContact>
        <Activities />
        <Groups />
      </SupplierInvoiceAddress>
      <SupplierDeliveryAddress>
        <Title />
        <Forename>Mark</Forename>
        <Surname>Ramsay</Surname>
        <Company>Concept Stationery Supplies</Company>
        <Description>Mark Ramsay - NE1 4GF</Description>
        <Address1>66 New Street</Address1>
        <Address2>Ridgeway</Address2>
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE1 4GF</Postcode>
        <County />
        <Country>GB</Country>
        <Telephone>0191 643 4343</Telephone>
        <Fax>0191 643 4344</Fax>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </SupplierDeliveryAddress>
      <TermsAgreed>true</TermsAgreed>
      <AccountStatus>0</AccountStatus>
      <Priority>true</Priority>
      <NominalCode>5000</NominalCode>
      <Analysis1>North East</Analysis1>
      <Analysis2>Stationery</Analysis2>
      <Analysis3 />
      <Contacts />
      <TaxCode>1</TaxCode>
      <Banks>
        <Bank>
          <BankName>HSBC Bank</BankName>
          <Address1>86 New Street</Address1>
          <Address2>Ridgeway</Address2>
          <Town>Newcastle upon Tyne</Town>
          <County />
          <Postcode>NE1 4GF</Postcode>
          <AccountName>Concept Stationery Supplies</AccountName>
          <SortCode>88-99-99</SortCode>
          <AccountNumber>99889988</AccountNumber>
          <BACSRef />
          <IBAN />
          <BICSwift />
          <RollNumber>Ridgeway</RollNumber>
          <AdditionalRef1 />
          <AdditionalRef2 />
          <AdditionalRef3 />
          <OnlineReceipts>true</OnlineReceipts>
        </Bank>
      </Banks>
    </Supplier>
  </Suppliers>
</Company>
```