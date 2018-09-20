---
slug: exporting-purchase-orders-from-sage-200
redirect_from: "/article/428-exporting-purchase-orders-from-sage-200"
title: Exporting Purchase Orders from Sage 200
---
This task will export new, modified or all purchase orders in [Sage 200 XML](sage-200-xml) format.

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
  <PurchaseOrders>
    <PurchaseOrder>
      <UniqueId>1665</UniqueId>
      <PurchaseOrderNumber>0000000001</PurchaseOrderNumber>
      <ForeignRate>1</ForeignRate>
      <AccountReference>INT001</AccountReference>
      <CurrencyUsed xsi:nil="true" />
      <NetValueDiscount xsi:nil="true" />
      <NetValueDiscountPercent>0</NetValueDiscountPercent>
      <TaxNumber />
      <PurchaseOrderDate>2013-10-15T00:00:00</PurchaseOrderDate>
      <PurchaseOrderRequestedDate>0001-01-01T00:00:00</PurchaseOrderRequestedDate>
      <PurchaseOrderAddress>
        <Company>Internetware</Company>
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
      </PurchaseOrderAddress>
      <PurchaseOrderDeliveryAddress>
        <Company />
        <Description> - </Description>
        <Address1 />
        <Address2 />
        <Address3 />
        <Town />
        <Postcode />
        <County />
        <Country> </Country>
        <CountryName><Non-European></CountryName>
        <Telephone />
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
      </PurchaseOrderDeliveryAddress>
      <PurchaseOrderItems>
        <Item>
          <Sku>PROD001</Sku>
          <Name>Test Product</Name>
          <Description>Test Product</Description>
          <QtyOrdered>1200</QtyOrdered>
          <UnitPrice>1</UnitPrice>
          <UnitDiscountAmount>0</UnitDiscountAmount>
          <UnitDiscountPercentage>0</UnitDiscountPercentage>
          <TaxRate>20</TaxRate>
          <AnalysisCodes />
          <Batches />
          <ProjectRef>0000000001</ProjectRef>
          <ProjectItem>MATERIAL01</ProjectItem>
          <TotalNet>1200</TotalNet>
          <TotalTax>240</TotalTax>
          <TaxCode>1</TaxCode>
          <NominalCode />
          <CostCentre />
          <Department />
          <Location>WAREHOUS</Location>
          <Barcode />
          <Type>Stock</Type>
          <QtyAllocated xsi:nil="true" />
          <QtyDespatched xsi:nil="true" />
          <QtyReceived>1200</QtyReceived>
          <QtyInvoiced>0</QtyInvoiced>
          <PromisedDeliveryDate xsi:nil="true" />
          <RequestedDeliveryDate xsi:nil="true" />
        </Item>
      </PurchaseOrderItems>
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
      <PurchaseOrderType>PopInvoice</PurchaseOrderType>
      <TakenBy>ADAM</TakenBy>
      <Courier xsi:nil="true" />
      <SettlementDays>0</SettlementDays>
      <SettlementDiscount>0</SettlementDiscount>
      <InvoiceDate xsi:nil="true" />
      <GlobalTaxCode>1</GlobalTaxCode>
      <PaymentAmount xsi:nil="true" />
      <Status>Live</Status>
      <AnalysisCodes />
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```