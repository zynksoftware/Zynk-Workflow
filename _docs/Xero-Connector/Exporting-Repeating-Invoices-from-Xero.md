---
slug: exporting-repeating-invoices-from-xero
title: Exporting Repeating Invoices from Xero
---

This task will download all repeating invoices from Xero in XML format.

## Settings

### Connection 
_Required_  
The Xero connection use when running this task.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. `Status == "Draft"`

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples

Sample output file showing an invoice:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfXeroRepeatingInvoice>
  <XeroRepeatingInvoice xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <Errors />
    <Warnings />
    <ValidationStatus>Ok</ValidationStatus>
    <Id>54a973cb-7f36-4396-b35f-4ce47ca8e9f5</Id>
    <Type>AccountsReceivable</Type>
    <Contact>
      <ValidationStatus>Ok</ValidationStatus>
      <UpdatedDateUtc xsi:nil="true" />
      <Id>63c5cc69-f262-41ce-807f-0753ba11d84b</Id>
      <ContactStatus>Active</ContactStatus>
      <Name>Zynk</Name>
      <IsSupplier xsi:nil="true" />
      <IsCustomer xsi:nil="true" />
      <Discount xsi:nil="true" />
      <HasAttachments xsi:nil="true" />
      <ContactPersons />
      <Addresses />
      <Phones />
      <ContactGroups />
    </Contact>
    <Schedule>
      <ValidationStatus>Ok</ValidationStatus>
      <Period>1</Period>
      <Unit>Monthly</Unit>
      <DueDate>0</DueDate>
      <DueDateType>AfterBillDate</DueDateType>
      <StartDate>2019-02-13T00:00:00</StartDate>
      <NextScheduledDate>2019-03-13T00:00:00</NextScheduledDate>
      <EndDate>2020-04-01T00:00:00</EndDate>
    </Schedule>
    <LineItems>
      <LineItem>
        <ValidationStatus>Ok</ValidationStatus>
        <Description>Whiteboard - Drywipe (900 x 1200)</Description>
        <Quantity>1.0000</Quantity>
        <UnitAmount>20.0000</UnitAmount>
        <AccountCode>4000</AccountCode>
        <ItemCode>BOARD001</ItemCode>
        <TaxType>OUTPUT2</TaxType>
        <TaxAmount>4.00</TaxAmount>
        <LineAmount>20.00</LineAmount>
        <DiscountRate xsi:nil="true" />
        <Tracking />
        <LineItemId>c8ff41f5-a47c-4dfb-8c87-ee75f486e223</LineItemId>
      </LineItem>
    </LineItems>
    <LineAmountTypes>Exclusive</LineAmountTypes>
    <Reference>12345</Reference>
    <BrandingThemeId>9b84060c-c379-4bf7-97b4-896f8b78edea</BrandingThemeId>
    <CurrencyCode>GBP</CurrencyCode>
    <Status>Draft</Status>
    <SubTotal>20.00</SubTotal>
    <TotalTax>4.00</TotalTax>
    <Total>24.00</Total>
    <HasAttachments>false</HasAttachments>
    <ExternalId />
  </XeroRepeatingInvoice>
</ArrayOfXeroRepeatingInvoice>
```