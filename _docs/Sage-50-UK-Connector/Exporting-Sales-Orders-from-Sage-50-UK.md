---
slug: exporting-sales-orders-from-sage-50-uk
redirect_from: "/article/402-exporting-sales-orders-from-sage-50-uk"
title: Exporting Sales Orders from Sage 50 UK
---
This task will export sales orders from Sage 50 to Zynk XML format.

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
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesOrders>
        <SalesOrder>
            <UniqueId>5</UniqueId>
            <CustomerId />
            <SalesOrderNumber>5</SalesOrderNumber>
            <CustomerOrderNumber />
            <Notes1 />
            <Notes2 />
            <Notes3 />
            <ForeignRate>1</ForeignRate>
            <AccountReference>BRO001</AccountReference>
            <CurrencyUsed>false</CurrencyUsed>
            <VatInclusive>false</VatInclusive>
            <SalesOrderDate>2009-01-24T00:00:00</SalesOrderDate>
            <DespatchDate>0001-01-01T00:00:00</DespatchDate>
            <DespatchStatus>Complete</DespatchStatus>
            <PromisedDeliveryDate xsi:nil="true" />
            <RequestedDeliveryDate xsi:nil="true" />
            <SalesOrderAddress>
                <Title />
                <Forename>Paul</Forename>
                <Surname>Guy</Surname>
                <Company>Bronson Inc</Company>
                <Description>Paul Guy - </Description>
                <Address1>18989 Royster Road</Address1>
                <Address2>Suite 343</Address2>
                <Address3 />
                <Town>Dallas Texas 769544</Town>
                <Postcode />
                <County>USA</County>
                <Country />
                <Email>newbusinessadvice@sage.com</Email>
                <Birthdate xsi:nil="true" />
                <Notes />
                <TaxCode>1</TaxCode>
                <CustomFields />
                <Activities />
                <Groups />
            </SalesOrderAddress>
            <SalesOrderDeliveryAddress>
                <Company>Bronson Inc</Company>
                <Description> - </Description>
                <Address1>18989 Royster Road</Address1>
                <Address2>Suite 343</Address2>
                <Address3 />
                <Town>Dallas Texas 769544</Town>
                <Postcode />
                <County>USA</County>
                <Country />
                <Email>newbusinessadvice@sage.com</Email>
                <Birthdate xsi:nil="true" />
                <Notes />
                <TaxCode>1</TaxCode>
                <CustomFields />
                <Activities />
                <Groups />
            </SalesOrderDeliveryAddress>
            <SalesOrderItems>
                <Item>
                    <Sku>PRN004</Sku>
                    <Name>JP020 Jet Printer</Name>
                    <Description />
                    <Comments>
                    </Comments>
                    <UnitOfSale>Each</UnitOfSale>
                    <QtyOrdered>6</QtyOrdered>
                    <UnitPrice>171</UnitPrice>
                    <UnitDiscountAmount>0</UnitDiscountAmount>
                    <UnitDiscountPercentage>0</UnitDiscountPercentage>
                    <Reference />
                    <TaxRate>0</TaxRate>
                    <CustomFields />
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>1026</TotalNet>
                    <TotalTax>0</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode>4000</NominalCode>
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>6</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
                <Item>
                    <Sku>PC002</Sku>
                    <Name>PC Combo Pack 2</Name>
                    <Description />
                    <Comments>
                    </Comments>
                    <UnitOfSale>Each</UnitOfSale>
                    <QtyOrdered>5</QtyOrdered>
                    <UnitPrice>617.5</UnitPrice>
                    <UnitDiscountAmount>0</UnitDiscountAmount>
                    <UnitDiscountPercentage>0</UnitDiscountPercentage>
                    <Reference />
                    <TaxRate>0</TaxRate>
                    <CustomFields />
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>3087.5</TotalNet>
                    <TotalTax>0</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode>4000</NominalCode>
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>5</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
                <Item>
                    <Sku>TR004</Sku>
                    <Name>JP020 Jet Printer Cartridge</Name>
                    <Description />
                    <Comments>
                    </Comments>
                    <UnitOfSale>Each</UnitOfSale>
                    <QtyOrdered>2</QtyOrdered>
                    <UnitPrice>14.25</UnitPrice>
                    <UnitDiscountAmount>0</UnitDiscountAmount>
                    <UnitDiscountPercentage>0</UnitDiscountPercentage>
                    <Reference />
                    <TaxRate>0</TaxRate>
                    <CustomFields />
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>28.5</TotalNet>
                    <TotalTax>0</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode>4000</NominalCode>
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>2</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
                <Item>
                    <Sku>TR003</Sku>
                    <Name>JP010 Jet Printer Cartridge</Name>
                    <Description />
                    <Comments>
                    </Comments>
                    <UnitOfSale>Each</UnitOfSale>
                    <QtyOrdered>2</QtyOrdered>
                    <UnitPrice>17.1</UnitPrice>
                    <UnitDiscountAmount>0</UnitDiscountAmount>
                    <UnitDiscountPercentage>0</UnitDiscountPercentage>
                    <Reference />
                    <TaxRate>0</TaxRate>
                    <CustomFields />
                    <AnalysisCodes />
                    <Batches />
                    <TotalNet>34.2</TotalNet>
                    <TotalTax>0</TotalTax>
                    <TaxCode>0</TaxCode>
                    <NominalCode>4000</NominalCode>
                    <Type>Stock</Type>
                    <QtyAllocated>0</QtyAllocated>
                    <QtyDespatched>2</QtyDespatched>
                    <QtyReceived xsi:nil="true" />
                    <QtyInvoiced xsi:nil="true" />
                    <Status>Complete</Status>
                    <PromisedDeliveryDate xsi:nil="true" />
                    <RequestedDeliveryDate xsi:nil="true" />
                </Item>
            </SalesOrderItems>
            <Carriage>
                <Sku />
                <QtyOrdered xsi:nil="true" />
                <UnitPrice>0</UnitPrice>
                <UnitDiscountAmount xsi:nil="true" />
                <UnitDiscountPercentage xsi:nil="true" />
                <TaxRate xsi:nil="true" />
                <CustomFields />
                <AnalysisCodes />
                <Batches />
                <TotalNet>0</TotalNet>
                <TotalTax>0</TotalTax>
                <TaxCode>0</TaxCode>
                <NominalCode />
                <Department>6</Department>
                <Type>ChargeLine</Type>
                <QtyAllocated xsi:nil="true" />
                <QtyDespatched xsi:nil="true" />
                <QtyReceived xsi:nil="true" />
                <QtyInvoiced xsi:nil="true" />
                <PromisedDeliveryDate xsi:nil="true" />
                <RequestedDeliveryDate xsi:nil="true" />
            </Carriage>
            <TakenBy />
            <ConsignmentNo />
            <Courier xsi:nil="true" />
            <SettlementDays xsi:nil="true" />
            <SettlementDiscount>4071.79</SettlementDiscount>
            <GlobalTaxCode xsi:nil="true" />
            <PaymentRef />
            <PaymentAmount>0</PaymentAmount>
            <BankAccount>1200</BankAccount>
            <TaxNumber />
            <Status>Complete</Status>
            <NetValueDiscountComment1 />
            <NetValueDiscountComment2 />
            <NetValueDiscountDescription />
            <NetValueDiscount>0</NetValueDiscount>
            <NetValueDiscountPercent>0</NetValueDiscountPercent>
            <DiscountType xsi:nil="true" />
            <CustomFields />
            <AnalysisCodes />
        </SalesOrder>
    </SalesOrders>
</Company>
```
