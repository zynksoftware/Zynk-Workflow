---
slug: exporting-customers-from-sage-200
redirect_from: "/article/424-exporting-customers-from-sage-200"
title: Exporting Customers from Sage 200
---
This task will export new, modified or all customers in [Sage 200 XML](sage-200-xml) format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Contact Settings
_Required_  

 * **Export All** - Set to true to export the full list of contacts for each customer, or false to export only modified contacts since the task last ran. Only takes effect when Export Contacts is set to true.
 * **Export Contacts** - Set to true to export the list of contacts for each customer.
 
### Delivery Address Settings
_Required_  

 * **Export All** - Set to true to export the full list of delivery address for each customer, or false to export only modified delivery addresses since the task last ran. Only takes effect when Export Delivery Addresses is set to true.
 * **Export Delivery Addresses** - Set to true to export the list of delivery addresses for each customer.

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
  <Customers>
    <Customer>
      <UniqueId>1228</UniqueId>
      <AccountReference>ZYN0001</AccountReference>
      <CompanyName>Zynk Software Limited</CompanyName>
      <Balance>299.28</Balance>
      <VatNumber />
      <SendElectronicInvoice xsi:nil="true" />
      <SendElectronicLetter xsi:nil="true" />
      <CustomerInvoiceAddress>
        <UniqueId>1229</UniqueId>
        <Title>Mr.</Title>
        <Forename>A</Forename>
        <Middlename />
        <Surname>W</Surname>
        <Company>Zynk Software Limited</Company>
        <Description> - NE1 4XF</Description>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3 />
        <Address4 />
        <Town>Jesmond</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country> </Country>
        <CountryName><Non-European></CountryName>
        <Telephone>0845 123 2920</Telephone>
        <TelephoneCountryCode />
        <TelephoneAreaCode />
        <Fax />
        <FaxCountryCode />
        <FaxAreaCode />
        <Email />
        <ContactName />
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <UniqueId>1229</UniqueId>
        <Title>Mr.</Title>
        <Forename>A</Forename>
        <Middlename />
        <Surname>W</Surname>
        <Company>Zynk Software Limited</Company>
        <Description> - NE1 4XF</Description>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3 />
        <Address4 />
        <Town>Jesmond</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country> </Country>
        <CountryName><Non-European></CountryName>
        <Telephone>0845 123 2920</Telephone>
        <TelephoneCountryCode />
        <TelephoneAreaCode />
        <Fax />
        <FaxCountryCode />
        <FaxAreaCode />
        <Email />
        <ContactName />
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </CustomerDeliveryAddress>
      <Analysis1 />
      <Analysis2 />
      <Analysis3 />
      <NominalCode>PREPAYME</NominalCode>
      <CostCentre />
      <Department />
      <OverrideNominalCode xsi:nil="true" />
      <TaxCode>1</TaxCode>
      <OverrideTaxCode xsi:nil="true" />
      <Currency>GBP</Currency>
      <FixedDiscount xsi:nil="true" />
      <LineDiscount>0</LineDiscount>
      <PriceListReference>Standard</PriceListReference>
      <DiscountGroupReference />
      <OrderValueDiscountReference />
      <DiscountType xsi:nil="true" />
      <CreditLimit>0</CreditLimit>
      <SettlementDays>0</SettlementDays>
      <SettlementDiscount>0</SettlementDiscount>
      <PaymentDays>0</PaymentDays>
      <Terms />
      <AccountStatus xsi:nil="true" />
      <DUNSNumber xsi:nil="true" />
      <TermsAgreed>true</TermsAgreed>
      <AccountOnHold>false</AccountOnHold>
      <AccountOpened>2013-10-04T00:00:00</AccountOpened>
      <LastCreditReview xsi:nil="true" />
      <NextCreditReview xsi:nil="true" />
      <ApplicationDate xsi:nil="true" />
      <DateReceived xsi:nil="true" />
      <LastInvoiceDate xsi:nil="true" />
      <LastPaymentDate xsi:nil="true" />
      <TurnoverMTD xsi:nil="true" />
      <TurnoverYTD xsi:nil="true" />
      <PriorYear xsi:nil="true" />
      <Priority xsi:nil="true" />
      <RestrictMailing xsi:nil="true" />
      <ChargeCredit xsi:nil="true" />
      <Banks />
      <Attachments />
      <Memo />
      <CreateOnly xsi:nil="true" />
      <ShortName>Websales</ShortName>
      <Contacts>
        <Contact>
          <UniqueId>1230</UniqueId>
          <Title>Mr.</Title>
          <Forename>A</Forename>
          <Middlename />
          <Surname>W</Surname>
          <Company>Zynk Software Limited</Company>
          <Description> - NE1 4XF</Description>
          <Address1>Nelson House</Address1>
          <Address2>Fleming Business Centre</Address2>
          <Address3 />
          <Address4 />
          <Town>Jesmond</Town>
          <Postcode>NE2 3AE</Postcode>
          <County>Tyne &amp; Wear</County>
          <Country> </Country>
          <Telephone>0845 123 2920</Telephone>
          <TelephoneCountryCode />
          <TelephoneAreaCode />
          <Fax />
          <FaxCountryCode />
          <FaxAreaCode />
          <Mobile />
          <MobileCountryCode />
          <MobileAreaCode />
          <Email />
          <Website />
          <Birthdate xsi:nil="true" />
          <Notes />
          <TaxCode>1</TaxCode>
          <Activities />
          <Groups />
        </Contact>
      </Contacts>
      <DeliveryAddresses />
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Web Customer</Name>
          <Value>false</Value>
        </AnalysisCode>
      </AnalysisCodes>
      <Activities />
      <Groups />
      <Notes />
    </Customer>
  </Customers>
</Company>
```