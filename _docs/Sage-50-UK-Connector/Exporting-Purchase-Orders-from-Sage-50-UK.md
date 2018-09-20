---
slug: exporting-purchase-orders-from-sage-50-uk
redirect_from: "/article/399-exporting-purchase-orders-from-sage-50-uk"
title: Exporting Purchase Orders from Sage 50 UK
---
This task will export purchase orders from Sage 50 in Zynk XML format.

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
    <PurchaseOrders>
        <PurchaseOrder>
            <UniqueId>1</UniqueId>
            <SupplierId />
            <PurchaseOrderNumber>1</PurchaseOrderNumber>
            <Notes1 />
            <Notes2 />
            <Notes3 />
            <ForeignRate>1</ForeignRate>
            <Currency>USD</Currency>
            <AccountReference>WIS002</AccountReference>
            <CurrencyUsed xsi:nil="true" />
            <NetValueDiscount xsi:nil="true" />
            <NetValueDiscountPercent xsi:nil="true" />
            <TaxNumber />
            <PurchaseOrderDate>2010-01-05T00:00:00</PurchaseOrderDate>
            <PurchaseOrderRequestedDate>0001-01-01T00:00:00</PurchaseOrderRequestedDate>
            <PurchaseOrderAddress>
                <Title />
                <Forename>Kathy</Forename>
                <Surname>Jordan</Surname>
                <Company>Wiseman Paper Products</Company>
                <Description>Kathy Jordan - NE1 2ED</Description>
                <Address1>Wiseman House</Address1>
                <Address2>Freddicks Way, Bell Estate</Address2>
                <Address3 />
                <Town>Newcastle Upon Tyne</Town>
                <Postcode>NE1 2ED</Postcode>
                <County />
                <Country />
                <Telephone />
                <Fax />
                <Mobile />
                <Email />
                <Birthdate xsi:nil="true" />
                <Notes />
                <TaxCode>1</TaxCode>
                <CustomFields />
                <Activities />
                <Groups />
            </PurchaseOrderAddress>
            <PurchaseOrderDeliveryAddress>
                <Company>Wiseman Paper Products</Company>
                <Description> - NE7 7LZ</Description>
                <Address1>Sage House</Address1>
                <Address2>Benton Park Road</Address2>
                <Address3 />
                <Town>Newcastle Upon Tyne</Town>
                <Postcode>NE7 7LZ</Postcode>
                <County />
                <Country />
                <Telephone />
                <Fax />
                <Mobile />
                <Email />
                <Birthdate xsi:nil="true" />
                <Notes />
                <TaxCode>1</TaxCode>
                <CustomFields />
                <Activities />
                <Groups />
            </PurchaseOrderDeliveryAddress>
            <PurchaseOrderItems>
                <Item>
                    <Sku>ENV001</Sku>
                    <Name>Envelope - White (110 x 220) Plain</Name>
                    <Description />
                    <Comments />
                    <UnitOfSale>1000 Box</UnitOfSale>
                    <QtyOrdered>40</QtyOrdered>
                    <UnitPrice>6</UnitPrice>
                    <UnitDiscountAmount>24</UnitDiscountAmount>
                    <UnitDiscountPercentage xsi:nil="true" />
                    <Reference />
                    <TaxRate>17.5</TaxRate>
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>216</TotalNet>
                    <TotalTax>36.86</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode />
                    <Text />
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>40</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
                <Item>
                    <Sku>ENV003</Sku>
                    <Name>Envelope - Brown (110 x 220) Plain</Name>
                    <Description />
                    <Comments />
                    <UnitOfSale>1000 Box</UnitOfSale>
                    <QtyOrdered>20</QtyOrdered>
                    <UnitPrice>6.3</UnitPrice>
                    <UnitDiscountAmount>12.6</UnitDiscountAmount>
                    <UnitDiscountPercentage xsi:nil="true" />
                    <Reference />
                    <TaxRate>17.5</TaxRate>
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>113.4</TotalNet>
                    <TotalTax>19.35</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode />
                    <Text />
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>20</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
                <Item>
                    <Sku>FLIP001</Sku>
                    <Name>Flip Chart - A1 Pad</Name>
                    <Description />
                    <Comments />
                    <UnitOfSale>Each</UnitOfSale>
                    <QtyOrdered>20</QtyOrdered>
                    <UnitPrice>11</UnitPrice>
                    <UnitDiscountAmount>22</UnitDiscountAmount>
                    <UnitDiscountPercentage xsi:nil="true" />
                    <Reference />
                    <TaxRate>17.5</TaxRate>
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>198</TotalNet>
                    <TotalTax>33.78</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode />
                    <Text />
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>20</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
            </PurchaseOrderItems>
            <Carriage>
                <Sku />
                <QtyOrdered xsi:nil="true" />
                <UnitPrice xsi:nil="true" />
                <UnitDiscountAmount xsi:nil="true" />
                <UnitDiscountPercentage xsi:nil="true" />
                <TaxRate xsi:nil="true" />
                <CustomFields />
                <AnalysisCodes />
                <Batches />
                <TotalNet>0</TotalNet>
                <TotalTax>0</TotalTax>
                <TaxCode xsi:nil="true" />
                <Type>Stock</Type>
                <QtyAllocated xsi:nil="true" />
                <QtyDespatched xsi:nil="true" />
                <QtyReceived xsi:nil="true" />
                <QtyInvoiced xsi:nil="true" />
                <PromisedDeliveryDate xsi:nil="true" />
                <RequestedDeliveryDate xsi:nil="true" />
            </Carriage>
            <Courier xsi:nil="true" />
            <SettlementDays xsi:nil="true" />
            <SettlementDiscount xsi:nil="true" />
            <InvoiceDate xsi:nil="true" />
            <GlobalTaxCode xsi:nil="true" />
            <PaymentAmount xsi:nil="true" />
            <AnalysisCodes />
            <CustomFields>
                <CustomField>
                    <Name>Tester</Name>
                    <Value>1</Value>
                </CustomField>
            </CustomFields>
        </PurchaseOrder>
    </PurchaseOrders>
</Company>
```