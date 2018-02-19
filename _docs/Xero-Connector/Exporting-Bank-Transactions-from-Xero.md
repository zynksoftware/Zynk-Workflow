---
slug: exporting-bank-transactions-from-xero
redirect_from: "/article/904-downloading-bank-transactions-from-xero"
title: Exporting Bank Transactions from Xero
---


This task will download bank transactions from Xero in XML format.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Export All
_Required_
Set to true to export all records, or false to only export records since the time shown in the Export From setting.

### Export From
_Required_
The rolling date to export modified records from. This will update automatically when the task runs. This setting only takes affect when Export All is set to false.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. 	`Type == "BANK" AND Name.Contains("Business")`

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample output file showing a bank transaction:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroBankTransaction>
  <XeroBankTransaction xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ValidationStatus>Ok</ValidationStatus>
    <UpdatedDateUtc>2015-10-27T14:56:45.677</UpdatedDateUtc>
    <Id>11f64cd1-4323-4f86-bc2d-dac88458b225</Id>
    <Contact>
      <ValidationStatus>Ok</ValidationStatus>
      <UpdatedDateUtc xsi:nil="true" />
      <Id>bcc999c0-9273-4e2f-82be-882ed4d1aad1</Id>
      <ContactStatus>Active</ContactStatus>
      <Name>Westpac</Name>
      <IsSupplier xsi:nil="true" />
      <IsCustomer xsi:nil="true" />
      <Discount xsi:nil="true" />
      <HasAttachments xsi:nil="true" />
      <ContactPersons />
      <Addresses />
      <Phones />
      <ContactGroups />
    </Contact>
    <BankAccount>
      <ValidationStatus>Ok</ValidationStatus>
      <Id>12c4da0e-c2e0-4b25-837e-734b3875c2bc</Id>
      <Code>1200B</Code>
      <Name>Bank</Name>
      <Status>Active</Status>
      <Type>None</Type>
      <BankAccountType xsi:nil="true" />
      <Class>Asset</Class>
      <SystemAccount xsi:nil="true" />
      <EnablePaymentsToAccount xsi:nil="true" />
      <ShowInExpenseClaims xsi:nil="true" />
      <HasAttachments xsi:nil="true" />
      <UpdatedDateUTC>0001-01-01T00:00:00</UpdatedDateUTC>
    </BankAccount>
    <Type>Spend</Type>
    <Status>Authorised</Status>
    <LineAmountTypes>Inclusive</LineAmountTypes>
    <IsReconciled>false</IsReconciled>
    <Date>2015-10-28T00:00:00</Date>
    <Reference />
    <CurrencyRate>0</CurrencyRate>
    <CurrencyCode>GBP</CurrencyCode>
    <SubTotal>16.67</SubTotal>
    <TotalTax>3.33</TotalTax>
    <Total>20.00</Total>
    <HasAttachments>false</HasAttachments>
    <LineItems>
      <LineItem>
        <ValidationStatus>Ok</ValidationStatus>
        <Description>Yearly Bank Account Fee</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>20.0000</UnitAmount>
        <AccountCode>4000</AccountCode>
        <TaxType>OUTPUT2</TaxType>
        <TaxAmount>3.33</TaxAmount>
        <LineAmount>20.00</LineAmount>
        <DiscountRate xsi:nil="true" />
        <Tracking />
        <LineItemId>c438eaf3-fcef-4a31-a9b6-d6377319455f</LineItemId>
      </LineItem>
    </LineItems>
    <PrepaymentID xsi:nil="true" />
    <OverpaymentID xsi:nil="true" />
  </XeroBankTransaction>
</ArrayOfXeroBankTransaction>
```
