---
slug: exporting-invoices-from-xero
redirect_from: "/article/346-downloading-invoices-from-xero"
title: Exporting Invoices from Xero
---


This task will download invoices from Xero in XML format.

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


Sample output file showing an invoice:


```xml
    <?xml version="1.0"?>
    <ArrayOfXeroInvoice>
      <XeroInvoice>
        <UpdatedDateUtc>2012-05-18T22:19:24.92</UpdatedDateUtc>
        <Id>3d9bc4f4-d3d2-48a1-b5c2-c8eb313d199c</Id>
        <Number>SM0210</Number>
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
          <Addresses />
          <Phones />
          <ContactGroups />
        </Contact>
        <Type>AccountsPayable</Type>
        <Status>Authorised</Status>
        <LineAmountTypes>Inclusive</LineAmountTypes>
        <Date>2014-08-22T00:00:00</Date>
        <DueDate>2014-09-01T00:00:00</DueDate>
        <ExpectedPaymentDate xsi:nil="true" />
        <PlannedPaymentDate xsi:nil="true" />
        <SubTotal>2083.33</SubTotal>
        <TotalTax>416.67</TotalTax>
        <Total>2500.00</Total>
        <CurrencyCode>GBP</CurrencyCode>
        <FullyPaidOnDate xsi:nil="true" />
        <AmountDue>2500.00</AmountDue>
        <AmountPaid>0.00</AmountPaid>
        <AmountCredited>0.00</AmountCredited>
        <HasAttachments>false</HasAttachments>
        <BrandingThemeId xsi:nil="true" />
        <Reference />
        <LineItems>
          <LineItem>
            <Description>Prototype media banner &amp; print mockups for Oaktown Business Leader ad series</Description>
            <Quantity>1.0000</Quantity>
            <UnitAmount>2500.0000</UnitAmount>
            <AccountCode>400</AccountCode>
            <TaxType>INPUT2</TaxType>
            <TaxAmount>416.67</TaxAmount>
            <LineAmount>2500.00</LineAmount>
            <DiscountRate xsi:nil="true" />
            <Tracking>
              <ItemTrackingCategory>
                <Id>9d8ad8f6-0d0f-41e0-8851-ef47e8b54ae6</Id>
                <Name>Region</Name>
                <Option>Eastside</Option>
              </ItemTrackingCategory>
            </Tracking>
          </LineItem>
        </LineItems>
      </XeroInvoice>
    </ArrayOfXeroInvoice>

```