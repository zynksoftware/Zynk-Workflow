---
slug: exporting-payments-from-xero
redirect_from: "/article/348-downloading-payments-from-xero"
title: Exporting Payments from Xero
---


This task will download payments from Xero in XML format.

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
    <ArrayOfXeroPayment>
      <XeroPayment>
        <UpdatedDateUtc>2011-04-04T01:59:25.413</UpdatedDateUtc>
        <Id>4c955477-b582-4d5e-898a-86fa14e461fb</Id>
        <Type>AccountsRecievable</Type>
        <Status>Authorised</Status>
        <Date>2013-09-08T00:00:00</Date>
        <CurrencyRate>1.000000</CurrencyRate>
        <Amount>500.00</Amount>
        <Reference>INV-001</Reference>
        <IsReconciled xsi:nil="true" />
        <Invoice>
          <UpdatedDateUtc xsi:nil="true" />
          <Id>4b6d0c8f-10fa-42cd-a6e5-53b175e90005</Id>
          <Number>INV-0001</Number>
          <Contact>
            <UpdatedDateUtc xsi:nil="true" />
            <Id>305ca5cf-497d-4fee-a161-cdb30e6be989</Id>
            <ContactStatus>Active</ContactStatus>
            <Name>Zynk Software</Name>
            <ContactNumber />
            <IsSupplier xsi:nil="true" />
            <IsCustomer xsi:nil="true" />
            <Discount xsi:nil="true" />
            <HasAttachments xsi:nil="true" />
            <ContactPersons />
            <Addresses />
            <Phones />
            <ContactGroups />
          </Contact>
          <Type>AccountsReceivable</Type>
          <Status>Draft</Status>
          <LineAmountTypes>Exclusive</LineAmountTypes>
          <Date xsi:nil="true" />
          <DueDate xsi:nil="true" />
          <ExpectedPaymentDate xsi:nil="true" />
          <PlannedPaymentDate xsi:nil="true" />
          <SubTotal xsi:nil="true" />
          <TotalTax xsi:nil="true" />
          <Total xsi:nil="true" />
          <CurrencyCode>GBP</CurrencyCode>
          <FullyPaidOnDate xsi:nil="true" />
          <AmountDue xsi:nil="true" />
          <AmountPaid xsi:nil="true" />
          <AmountCredited xsi:nil="true" />
          <HasAttachments xsi:nil="true" />
          <BrandingThemeId xsi:nil="true" />
          <Items />
        </Invoice>
        <Account>
          <Id>bd9e85e0-0478-433d-ae9f-0b3c4f04bfe4</Id>
          <Code>090</Code>
          <Status>Active</Status>
          <Type>None</Type>
          <Class>Asset</Class>
          <SystemAccount>Debtors</SystemAccount>
          <EnablePaymentsToAccount xsi:nil="true" />
          <ShowInExpenseClaims xsi:nil="true" />
          <HasAttachments xsi:nil="true" />
        </Account>
      </XeroPayment>
    </ArrayOfXeroPayment>

```