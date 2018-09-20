---
slug: exporting-sales-orders-from-sage-200
redirect_from: "/article/430-exporting-sales-orders-from-sage-200"
title: Exporting Sales Orders from Sage 200
---
This task will export new, modified or all sales orders in [Sage 200 XML](sage-200-xml) format.

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
  <SalesOrders>
    <SalesOrder>
      <Id>12</Id>
      <UniqueId>1361</UniqueId>
      <SalesOrderNumber>0000000002</SalesOrderNumber>
      <CustomerOrderNumber>12</CustomerOrderNumber>
      <ForeignRate>1</ForeignRate>
      <Currency>GBP</Currency>
      <AccountReference>ZYN0001</AccountReference>
      <CurrencyUsed>false</CurrencyUsed>
      <VatInclusive>false</VatInclusive>
      <SalesOrderDate>2013-10-09T00:00:00</SalesOrderDate>
      <DespatchDate xsi:nil="true" />
      <PromisedDeliveryDate>2013-10-10T00:00:00</PromisedDeliveryDate>
      <RequestedDeliveryDate>2013-10-10T00:00:00</RequestedDeliveryDate>
      <SalesOrderAddress>
        <Company>Zynk Software Limited</Company>
        <Description> - NE2 3AE</Description>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3 />
        <Town>Jesmond</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne & Wear</County>
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
      </SalesOrderAddress>
      <SalesOrderDeliveryAddress>
        <Company>Zynk Software Limited</Company>
        <Description> - NE2 3AE</Description>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3 />
        <Town>Jesmond</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne & Wear</County>
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
      </SalesOrderDeliveryAddress>
      <SalesOrderItems>
        <Item>
          <Sku>PROD001</Sku>
          <Name>Test Product</Name>
          <Description>Test Product</Description>
          <QtyOrdered>5</QtyOrdered>
          <UnitPrice>34.2</UnitPrice>
          <UnitDiscountAmount>0</UnitDiscountAmount>
          <UnitDiscountPercentage>0</UnitDiscountPercentage>
          <TaxRate>20</TaxRate>
          <AnalysisCodes />
          <Batches />
          <TotalNet>171</TotalNet>
          <TotalTax>29.93</TotalTax>
          <TaxCode>1</TaxCode>
          <NominalCode />
          <CostCentre />
          <Department />
          <Location>WAREHOUS</Location>
          <Barcode />
          <Type>Stock</Type>
          <QtyAllocated>0</QtyAllocated>
          <QtyDespatched>5</QtyDespatched>
          <QtyReceived xsi:nil="true" />
          <QtyInvoiced xsi:nil="true" />
          <FulfilmentMethod>From Stock</FulfilmentMethod>
          <PromisedDeliveryDate>2013-10-10T00:00:00</PromisedDeliveryDate>
          <RequestedDeliveryDate>2013-10-10T00:00:00</RequestedDeliveryDate>
        </Item>
      </SalesOrderItems>
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
        <TaxCode xsi:nil="true" />
        <Type>ChargeLine</Type>
        <QtyAllocated xsi:nil="true" />
        <QtyDespatched xsi:nil="true" />
        <QtyReceived xsi:nil="true" />
        <QtyInvoiced xsi:nil="true" />
        <PromisedDeliveryDate xsi:nil="true" />
        <RequestedDeliveryDate xsi:nil="true" />
      </Carriage>
      <SalesOrderType>SopInvoice</SalesOrderType>
      <TakenBy>Website</TakenBy>
      <Courier xsi:nil="true" />
      <SettlementDays>0</SettlementDays>
      <SettlementDiscount>0</SettlementDiscount>
      <GlobalTaxCode>1</GlobalTaxCode>
      <PaymentAmount>0</PaymentAmount>
      <TaxNumber />
      <PaymentType>SalesReceipt</PaymentType>
      <Status>Live</Status>
      <NetValueDiscount xsi:nil="true" />
      <NetValueDiscountPercent>0</NetValueDiscountPercent>
      <DiscountType xsi:nil="true" />
      <Priority />
      <AnalysisCodes />
    </SalesOrder>
  </SalesOrders>
</Company>
```