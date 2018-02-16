---
slug: exporting-credit-notes-from-xero
redirect_from: "/article/345-downloading-credit-notes-from-xero"
title: Exporting Credit Notes from Xero
---


This task will download credit notes from Xero in XML format.


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


Sample output file showing a credit note:

```xml
<?xml version="1.0"?>
    <ArrayOfXeroCreditNote>
      <XeroCreditNote>
        <UpdatedDateUtc>2011-04-06T21:00:33.82</UpdatedDateUtc>
        <Id>7d1f4e11-e909-43b0-901c-2c824dff1e82</Id>
        <Number>720-2</Number>
        <Type>AccountsPayable</Type>
        <Reference />
        <SentToContact xsi:nil="true" />
        <AppliedAmount>0</AppliedAmount>
        <RemainingCredit>0.00</RemainingCredit>
        <CurrencyRate>1.000000</CurrencyRate>
        <Contact>
          <UpdatedDateUtc xsi:nil="true" />
          <Id>305ca5cf-497d-4fee-a161-cdb30e6be989</Id>
          <ContactStatus>Active</ContactStatus>
          <Name>Zynk Software</Name>
          <IsSupplier xsi:nil="true" />
          <IsCustomer xsi:nil="true" />
          <Discount xsi:nil="true" />
          <HasAttachments xsi:nil="true" />
          <ContactPersons />
        </Contact>
        <Date>2014-07-07T00:00:00</Date>
        <DueDate>0001-01-01T00:00:00</DueDate>
        <BrandingThemeId>00000000-0000-0000-0000-000000000000</BrandingThemeId>
        <Status>Paid</Status>
        <LineAmountTypes>Inclusive</LineAmountTypes>
        <SubTotal>225.30</SubTotal>
        <TotalTax>45.06</TotalTax>
        <Total>270.36</Total>
        <CurrencyCode>GBP</CurrencyCode>
        <HasAttachments>false</HasAttachments>
        <FullyPaidOnDate>2014-07-07T00:00:00</FullyPaidOnDate>
        <LineItems />
        <Allocations>
          <Allocation>
            <AppliedAmount>0</AppliedAmount>
            <Date>2014-07-07T00:00:00</Date>
            <Invoice>
              <UpdatedDateUtc xsi:nil="true" />
              <Id>94f824a9-5346-4193-b0ec-1fde675df289</Id>
              <Number>720-2</Number>
              <Type>AccountsPayable</Type>
              <Status>Draft</Status>
              <LineAmountTypes>Exclusive</LineAmountTypes>
              <Date xsi:nil="true" />
              <DueDate xsi:nil="true" />
              <ExpectedPaymentDate xsi:nil="true" />
              <PlannedPaymentDate xsi:nil="true" />
              <SubTotal xsi:nil="true" />
              <TotalTax xsi:nil="true" />
              <Total xsi:nil="true" />
              <FullyPaidOnDate xsi:nil="true" />
              <AmountDue xsi:nil="true" />
              <AmountPaid xsi:nil="true" />
              <AmountCredited xsi:nil="true" />
              <HasAttachments xsi:nil="true" />
              <BrandingThemeId xsi:nil="true" />
              <LineItems />
            </Invoice>
            <Amount>270.36</Amount>
          </Allocation>
        </Allocations>
      </XeroCreditNote>
     </ArrayOfXeroCreditNote>
```