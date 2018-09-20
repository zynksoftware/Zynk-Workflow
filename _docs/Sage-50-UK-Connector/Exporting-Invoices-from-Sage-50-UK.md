---
slug: exporting-invoices-from-sage-50-uk
redirect_from: "/article/396-exporting-invoices-from-sage-50-uk"
title: Exporting Invoices from Sage 50 UK
---
This task will export invoices from Sage 50 in Zynk XML format.

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

### Use Base Currency
_Required_  
Set to true to export all monetary values in the base currency, or false to use the account currency.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Invoices>
    <Invoice>
      <UniqueId>58</UniqueId>
      <CustomerId />
      <InvoiceNumber>58</InvoiceNumber>
      <CustomerOrderNumber />
      <AccountReference>ABS001</AccountReference>
      <OrderNumber>4545</OrderNumber>
      <ForeignRate>1</ForeignRate>
      <Notes1 />
      <Notes2 />
      <Notes3 />
      <CurrencyUsed xsi:nil="true" />
      <InvoiceDate>2009-04-24T00:00:00</InvoiceDate>
      <InvoiceAddress>
        <Title />
        <Forename>Mike</Forename>
        <Surname>Hall</Surname>
        <Company>ABS Garages Ltd</Company>
        <Description>Mike Hall - NE31 1VB</Description>
        <Address1>Unit 34</Address1>
        <Address2>Holystone Ind Estate</Address2>
        <Address3 />
        <Town>Hebburn</Town>
        <Postcode>NE31 1VB</Postcode>
        <County>Tyne & Wear</County>
        <Country />
        <Email>newbusinessadvice@sage.com</Email>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </InvoiceAddress>
      <InvoiceDeliveryAddress>
        <Title />
        <Forename>ABS Garages</Forename>
        <Surname>Ltd</Surname>
        <Company>ABS Garages Ltd</Company>
        <Description>ABS Garages Ltd - NE56 4ER</Description>
        <Address1>Swanson Industries</Address1>
        <Address2>Dukes Industrial Estate</Address2>
        <Address3 />
        <Town>Whitley Bay</Town>
        <Postcode>NE56 4ER</Postcode>
        <County>North Tyneside</County>
        <Country />
        <Email>newbusinessadvice@sage.com</Email>
        <Birthdate xsi:nil="true" />
        <Notes />
        <TaxCode>1</TaxCode>
        <CustomFields />
        <Activities />
        <Groups />
      </InvoiceDeliveryAddress>
      <InvoiceItems>
        <Item>
          <Sku>BOOKS002</Sku>
          <Name>A4 Carbon Copy Book - Triplicate</Name>
          <Description />
          <Comments>
          </Comments>
          <UnitOfSale>Each</UnitOfSale>
          <QtyOrdered>12</QtyOrdered>
          <UnitPrice>2.69</UnitPrice>
          <UnitDiscountAmount>4.84</UnitDiscountAmount>
          <UnitDiscountPercentage>15</UnitDiscountPercentage>
          <Reference />
          <TaxRate>17.5</TaxRate>
          <CustomFields />
          <AnalysisCodes />
          <Batches />
          <TotalNet>27.44</TotalNet>
          <TotalTax>4.68</TotalTax>
          <TaxCode>1</TaxCode>
          <NominalCode>4000</NominalCode>
          <Department>1</Department>
          <Text />
          <Type>Stock</Type>
          <QtyAllocated xsi:nil="true" />
          <QtyDespatched xsi:nil="true" />
          <QtyReceived xsi:nil="true" />
          <QtyInvoiced xsi:nil="true" />
          <PromisedDeliveryDate xsi:nil="true" />
          <RequestedDeliveryDate xsi:nil="true" />
        </Item>
        <Item>
          <Sku>BOOKS003</Sku>
          <Name>Shorthand Notebook - 80 Sheets</Name>
          <Description />
          <Comments>
          </Comments>
          <UnitOfSale>Pack</UnitOfSale>
          <QtyOrdered>10</QtyOrdered>
          <UnitPrice>4.05</UnitPrice>
          <UnitDiscountAmount>6.07</UnitDiscountAmount>
          <UnitDiscountPercentage>15</UnitDiscountPercentage>
          <Reference />
          <TaxRate>17.5</TaxRate>
          <CustomFields />
          <AnalysisCodes />
          <Batches />
          <TotalNet>34.43</TotalNet>
          <TotalTax>5.87</TotalTax>
          <TaxCode>1</TaxCode>
          <NominalCode>4000</NominalCode>
          <Department>1</Department>
          <Text />
          <Type>Stock</Type>
          <QtyAllocated xsi:nil="true" />
          <QtyDespatched xsi:nil="true" />
          <QtyReceived xsi:nil="true" />
          <QtyInvoiced xsi:nil="true" />
          <PromisedDeliveryDate xsi:nil="true" />
          <RequestedDeliveryDate xsi:nil="true" />
        </Item>
      </InvoiceItems>
      <ItemsNet>61.87</ItemsNet>
      <ItemsTax>10.55</ItemsTax>
      <ItemsTotal>72.42</ItemsTotal>
      <Carriage>
        <Sku />
        <QtyOrdered>0</QtyOrdered>
        <UnitPrice>0</UnitPrice>
        <UnitDiscountAmount xsi:nil="true" />
        <UnitDiscountPercentage xsi:nil="true" />
        <TaxRate>0</TaxRate>
        <CustomFields />
        <AnalysisCodes />
        <Batches />
        <TotalNet>0</TotalNet>
        <TotalTax>0</TotalTax>
        <TaxCode>1</TaxCode>
        <NominalCode />
        <Department>1</Department>
        <Type>Stock</Type>
        <QtyAllocated xsi:nil="true" />
        <QtyDespatched xsi:nil="true" />
        <QtyReceived xsi:nil="true" />
        <QtyInvoiced xsi:nil="true" />
        <PromisedDeliveryDate xsi:nil="true" />
        <RequestedDeliveryDate xsi:nil="true" />
      </Carriage>
      <CustomFields />
      <InvoiceType>ProductInvoice</InvoiceType>
      <TakenBy />
      <ConsignmentNo />
      <Courier>1</Courier>
      <SettlementDays>30</SettlementDays>
      <NetValueDiscount>0</NetValueDiscount>
      <NetValueDiscountPercent>0</NetValueDiscountPercent>
      <DiscountType xsi:nil="true" />
      <SettlementDiscount>2.5</SettlementDiscount>
      <GlobalTaxCode>0</GlobalTaxCode>
      <GlobalDepartment>1</GlobalDepartment>
      <PaymentRef />
      <PaymentAmount xsi:nil="true" />
      <BankAccount>1200</BankAccount>
      <PostedDate xsi:nil="true" />
      <PostedFlag>true</PostedFlag>
      <PrintedFlag>false</PrintedFlag>
      <PaidFlag xsi:nil="true" />
      <AmountPaid>0</AmountPaid>
      <TaxNumber />
    </Invoice>
  </Invoices>
</Company>
```