---
slug: sage-200-sales-order-xml
title: Sage 200 Sales Order XML
---
Import Sales Orders allows you to create new orders with Sage 200, and optionally progress the order through the ordering process.  The Id field should be populated by the unique id of the order from the external system, Zynk uses this field to track orders already imported to prevent duplicates being created in Sage.  The Id is also included when the order is exported from Sage.  

Any Sage fields not documented below are not currently supported with our imports.  

Sample import file for creating a basic order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Id>12345</Id>
      <AccountReference>INTE001</AccountReference>
      <SalesOrderDate>2011-01-01T11:11:11</SalesOrderDate>
      <SalesOrderAddress>
        <Title>Mr</Title>
        <Forename>Test</Forename>
        <Surname>Person</Surname>
        <Company>Internetware</Company>
        <Address1>i6 Building</Address1>
        <Address2>6-8 Charlotte Square</Address2>
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
      </SalesOrderAddress>
      <SalesOrderDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Test</Forename>
        <Surname>Person</Surname>
        <Company>Internetware</Company>
        <Address1>i6 Building</Address1>
        <Address2>6-8 Charlotte Square</Address2>
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
      </SalesOrderDeliveryAddress>
      <SalesOrderItems>
        <Item>
          <Sku>TEST01</Sku>
          <QtyOrdered>1</QtyOrdered>
          <UnitPrice>200</UnitPrice>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create an order.  The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Order Details - Account selection
To assign the order to a particular account you will need to specify either a CustomerId or an AccountReference in the XML.  The CustomerId should correspond to a customer that has already been imported into Sage via Zynk, see Import Customer.  The AccountReference should correspond to the Reference of a Sales Ledger account that exists within Sage.

|  XML Field | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| CustomerId | - | 12345 | string | 255 | Required, unless AccountReference is provided | Only used if an AccountReference is not provided. |
| AccountReference | A/C Ref | INTE001 | string | 8 | Required, unless CustomerId is provided |
| DefaultWarehouse | By default supply from | Warehouse 1 | string | 20 | Optional | If not specified, this will be picked up from the task settings. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <CustomerId>12345</CustomerId>
      <AccountReference>INTE001</AccountReference>
      <DefaultWarehouse>Warehouse 1</DefaultWarehouse>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Order Details - Order detail
All of the fields at the Order detail level are optional.  

Depending on the settings of the import task you can set the Order no of the created order.  If you have enabled Manual Order Numbering at the task level you can specify the SalesOrderNumber to use when creating the order, note this must be unique, and if already exists in Sage the order will not be imported.  You can specify the Document date of the order using SalesOrderDate.

|  XML Field | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 12345 | string | 255 | Optional | Used for duplicate prevention, if the setting is enabled on the task. It is included in sales order exports.  |
| SalesOrderNumber | Order no | 12345 | int | 30 | Optional  | Only used when the 'Manual Order Number' setting is enabled on the task, otherwise next number will be used. |
| SalesOrderDate | Document date | 2011-01-01T11:11:11 | date | - | Optional | Will default to the current date if not provided.  |
| SalesOrderType | Type | ProductInvoice | enum | - | Optional | Can be set to ProductInvoice, SopReturn, SopQuote or SopProforma. Will default to ProductInvoice if not provided. |
| RequestedDeliveryDate  | Date requested  | 2011-01-01T11:11:11 | date | - | Optional  | Will default to the current date if not provided. |
| PromisedDeliveryDate | Date promised  | 2011-01-01T11:11:11 | date | - | Optional | Will default to the current date if not provided. |
| CustomerOrderNumber | Customer order no  | ABC12345 | string |  30 | Optional |
| Currency | - | GBP | string |  30 | Optional | The three letter ISO currency code. It must match the currency of the customers account. Will default to the currency on the customer account if not provided. |
| GenerateBackToBackPurchaseOrder | - | false | boolean | - | Optional | A purchase order can only be generated when one or more items has the fulfilment method 'Supplier Via Stock' or 'Direct To Customer'. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Id>12345</Id>
      <SalesOrderNumber>12345</SalesOrderNumber>
      <SalesOrderDate>2011-01-01T11:11:11</SalesOrderDate>
      <SalesOrderType>ProductInvoice</SalesOrderType>
      <RequestedDeliveryDate>2011-01-01T11:11:11</RequestedDeliveryDate>
      <PromisedDeliveryDate>2011-01-01T11:11:11</PromisedDeliveryDate>
      <CustomerOrderNumber>12345</CustomerOrderNumber>
      <Currency>GBP</Currency>
      <GenerateBackToBackPurchaseOrder>false</GenerateBackToBackPurchaseOrder>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Order Details - Items
We currently support most item types within Sage 200 with the exception of Sales Order Items (Sales Order Processing -> SOP Maintenance -> Sales Order Items).  Zynk determines the type of each item based on the Type provided in the XML. If no Type is provided, it will default to Stock (a standard item). All item types support the import of analysis codes, see below.

### Standard Items
Setting the Type to either Stock, NonStock or Miscellaneous will import a standard item.  Depending on the settings on the import task you lookup a product based on either the Sku or Barcode fields.  Depending on the settings on the import task you can optionally auto create products during the import if they do not exist.  You can import nominal analysis with standard item lines, see below.

| XML Field | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sku | Code | PROD01 | string | 30 | Required, unless using barcodes |
| Barcode | - | 123456789 | string | 30 | Required, unless using sku | Only used for lookups, if enabled at the task level. |
| Location | Warehouse | Warehouse 1 | string | 20 | Optional | If not provided, will be set to a warehouse associated with the product based on the task settings. |
| Description | Description | Product 01 | string | - | Optional | Will default to the name of the product if not provided. |
| TaxCode | Tax rate  | 1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitPrice | Unit price | 100 | double | - | Required |
| QtyOrdered | Quantity | 1 | double | - | Required |
| UnitOfSale | Selling unit  | Each | string | 20 | Optional | Will default to the base unit if not provided. |
| PricingUnit | Selling price unit | Each | string | 20 | Optional | Will default to the base unit if not provided. |
| UnitDiscountAmount | Unit discount | 10 | double | - | Optional | Will default to 0 if this or UnitDiscountPercentage is not provided.  |
| UnitDiscountPercentage | Unit discount % | 10 | double | - | Optional | Only used if UnitDiscountAmount is not set. Defaults to 0 if this or UnitDiscountAmount is not set. |
| RequestedDeliveryDate | Delivery dates Requested | 2011-01-01T11:11:11 | date | - | Optional | Will default to the RequestedDeliveryDate at the SalesOrder level if not provided. |
| PromisedDeliveryDate | Delivery dates Promised | 2011-01-01T11:11:11 | date | - | Optional | Will default to the PromisedDeliveryDate at the SalesOrder level if not provided. |
| FulfilmentMethod | Fulfilment Method | From Stock | enum | - | Optional | Available values are: 'From Stock', 'Supplier Via Stock' and 'Direct To Customer'. Defaults to 'From Stock'. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Type>Stock</Type>
          <Sku>PROD01</Sku>
          <Barcode>123456789</Barcode>
          <Location>Warehouse 1</Location>
          <Description>Product 01</Description>
          <TaxCode>1</TaxCode>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
          <UnitDiscountAmount>10</UnitDiscountAmount>
          <UnitDiscountPercentage>10</UnitDiscountPercentage>
          <RequestedDeliveryDate>2011-01-01T11:11:11</RequestedDeliveryDate>
          <PromisedDeliveryDate>2011-01-01T11:11:11</PromisedDeliveryDate>
          <FulfilmentMethod>From Stock</FulfilmentMethod>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Service Items
Setting the Type to Service will import a service item. You can import nominal analysis with service lines, see below.

| XML Field  | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sku | Code | SERV01 | string | 30 | Required |
| UnitPrice | Unit price |  100 | double | - | Required |
| QtyOrdered | Quantity |  1 | double | - | Required |
| TaxCode | Tax Rate |  1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitDiscountAmount | Unit discount | 10 | double | - | Optional | Will default to 0 if this or UnitDiscountPercentage is not provided. |
| UnitDiscountPercentage | Unit discount % | 10 | double | - | Optional | Only used if UnitDiscountAmount is not set. Defaults to 0 if this or UnitDiscountAmount is not set. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Type>Service</Type>
          <Sku>SERV01</Sku>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
          <TaxCode>1</TaxCode>
          <UnitDiscountAmount>10</UnitDiscountAmount>
          <UnitDiscountPercentage>10</UnitDiscountPercentage>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Free Text Items
Setting the Type to FreeText will import a free text item. You can import nominal analysis with free text lines, see below.

| XML Field | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Text | Item line description | Product 01 | string | 60 | Required, unless Description is set |
| Description | Item line description | Product 01 | string | 60 | Required, unless Text is set | Will only be used if Text is not set |
| UnitPrice | Unit price |  100 | double | - | Required |
| QtyOrdered | Quantity |  1 | double | - | Required |
| TaxCode | Tax rate |  1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitDiscountAmount | Unit discount | 10 | double | - | Optional | Will default to 0 if this or UnitDiscountPercentage is not provided. |
| UnitDiscountPercentage | Unit discount %  | 10 | double | - | Optional | Only used if UnitDiscountAmount is not set. Defaults to 0 if this or UnitDiscountAmount is not set. |
| RequestedDeliveryDate | Delivery dates Requested | 2011-01-01T11:11:11 | date | - | Optional | Will default to the RequestedDeliveryDate at the SalesOrder level if not provided, |
| PromisedDeliveryDate | Delivery dates Promised | 2011-01-01T11:11:11 | date | - | Optional | Will default to the PromisedDeliveryDate at the SalesOrder level if not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Type>FreeText</Type>
          <Text>Product 01</Text>
          <Description>Product 01</Description>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
          <TaxCode>1</TaxCode>
          <UnitDiscountAmount>10</UnitDiscountAmount>
          <UnitDiscountPercentage>10</UnitDiscountPercentage>
          <RequestedDeliveryDate>2011-01-01T11:11:11</RequestedDeliveryDate>
          <PromisedDeliveryDate>2011-01-01T11:11:11</PromisedDeliveryDate>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Additional Charge Lines
Setting the Type to ChargeLine will import an additional charge item.  To import an additional charge line, an additional charge must already be set up within Sage with a matching code.  This can be configured under Sales Order Processing -> SOP Maintenance -> Additional Charges.  You can import nominal analysis with charge lines, see below.

| XML Field  | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sku | Charge Code | CARRIAGE | string | 30 | Required |
| Name | Charge Name | Carriage Charge | string | 60 | Required |
| TaxCode | Tax rate | 1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitPrice | Net value | 100 | double | - | Required |
| TotalTax | Tax value | 20 | double | - | Optional | Will only be set if a tax code is not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Type>ChargeLine</Type>
          <Sku>CARRIAGE</Sku>
          <Name>Carriage Charge</Name>
          <TaxCode>1</TaxCode>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
          <TotalTax>20</TotalTax>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Comment Lines
Setting the Type to CommentLine will import a comment line.

| XML Field  | Sage Field  | Example |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Text | Item line description | Order comments | string | 60 | Required |
| ShowOnDocs | Show on customer documents | true | boolean | - | Optional | Only supported in Zynk v2.6 and above |
| ShowOnPickingList | Show on picking lists | true | boolean | - | Optional | Only supported in Zynk v2.6 and above |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <Type>CommentLine</Type>
          <Text>Order comments</Text>
          <ShowOnDocs>true</ShowOnDocs>
          <ShowOnPickingList>true</ShowOnPickingList>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Analysis Codes
Analysis codes are imported from a collection, so you can imported as many as are setup within Sage 200.  We lookup analysis codes by matching the Name from the XML to the Field Label in Sage.  The values that can be imported depend on how the analysis code is configured, if you need to import any value ensure Enter Free Text is enabled in Sage from Accounting System Manager -> Settings -> Maintain Analysis Codes.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name | Analysis Code | Customer Type | string | 60 | Required | The analysis code must already exist, otherwise will not be added. |
| Value | Value | A | string | 60 | Optional | The value must already exist, unless Enter Free Text is enabled. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <AnalysisCodes>
            <AnalysisCode>
              <Name>Customer Type</Name>
              <Value>A</Value>
            </AnalysisCode>
            <AnalysisCode>
              <Name>Order Source</Name>
              <Value>Web</Value>
            </AnalysisCode>
          </AnalysisCodes>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

### Nominal Analysis
The nominal specification supplied in the XML must exist within Sage 200.

| XML Field | Sage Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| NominalCode | A/C Ref | 4000 | int | - | Optional |
| CostCentre | CC | 01 | string | 3 | Optional |
| Department | Dept | 01 | string | 3 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderItems>
        <Item>
          <NominalCode>4000</NominalCode>
          <CostCentre>01</CostCentre>
          <Department>01</Department>
        </Item>
      </SalesOrderItems>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Order Details - Exchange rate
The Currency field cannot be set directly on an order as this is set through the associated Sales Ledger account. Note that the exchange rate can only be set to 1 if the order is in the base currency.

| XML Field | Sage Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| ForeignRate | Rate | 1 | double | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <ForeignRate>1</ForeignRate>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Delivery address
The Address1 field is used to check if the delivery address is provided in the XML, and if so Zynk will use the data provided.  If Address1 is blank and the customer has a default delivery address configured in Sage, Zynk will use that, otherwise it will fall back to the invoice address of the customer in Sage.  Note if 'Use Segmented Addresses' is not enabled in Accounting System Manager -> System Settings certain fields will not be displayed in addresses.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Company | Postal name | Internetware | string | 60 | Optional | If not provided, will be built up from the Title, Forename and Surname. |
| Address1 | Address 1 | i6 Building | string | 60 | Optional |
| Address2 | Address 2 | 6-8 Charlotte Square | string | 60 | Optional |
| Address3 | Address 3 | string | 60 | Optional |
| Address4 | Address 4 | string | 60 | Optional |
| Town | City | Newcastle Upon Tyne | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings.|
| County | County | Tyne and Wear | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| Postcode  | Postcode | NE1 4XF | string | 10 | Optional |
| Country | Country  | GB | string | 2 | Optional | Should be the ISO2 country code. If a country name is provided, Zynk will try to map it to the appropriate county code.
If a value is not provided, it will be taken from the customer's invoice address in Sage. |
| ContactName  | Contact | Test Person | string | 50 | Optional |
| Telephone  | Telephone | 0845 123 2920 | string | 30 | Optional |
| Fax  | Fax | 0845 123 2921 | string | 30 | Optional |
| Email  | E-mail | support@internetware.co.uk | string | 255 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderDeliveryAddress>
        <Company>Internetware</Company>
        <Title>Mr</Title>
        <Forename>Test</Forename>
        <Surname>Person</Surname>
        <Address1>i6 Building</Address1>
        <Address2>6-8 Charlotte Square</Address2>
        <Town>Newcastle Upon Tyne</Town>
        <County>Tyne and Wear</County>
        <Postcode>NE1 4XF</Postcode>
        <Country>GB</Country>
        <ContactName>Test Person</ContactName>
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Email>support@internetware.co.uk</Email>
      </SalesOrderDeliveryAddress>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Tax details

| XML Field | Sage Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| TaxNumber | Tax number | 12345 | string | 30 | Optional |
| GlobalTaxCode | Tax code | 1 | int | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <TaxNumber>12345</TaxNumber>
      <GlobalTaxCode>1</GlobalTaxCode>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Invoice address
We currently only support standard customer accounts (not cash accounts), so we do not set the invoice address per order.  The invoice address is read from the associated customer account.

## Delivery & Invoicing - Early settlement discount

| XML Field | Sage Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| SettlementDiscount | Discount % | 10 | double | - | Optional |
| SettlementDays | if paid within | 10 | short | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SettlementDiscount>10</SettlementDiscount>
      <SettlementDays>10</SettlementDays>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Order discount / surcharge
We currently only support adding order discounts.  You can provide either an amount or a percentage, and the percentage discount will be calculated based on the given values.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| NetValueDiscount | Discount % | 10 | double | - | Optional | If both the NetValueDiscount and NetValueDiscountPercent are provided, the NetValueDiscountPercent will be used. Defaults to 0 if neither is provided. |
| NetValueDiscountPercent | Discount % | 10 | double | - | Optional | If both the NetValueDiscount and NetValueDiscountPercent are provided, the NetValueDiscountPercent will be used. Defaults to 0 if neither is provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <NetValueDiscount>10</NetValueDiscount>
      <NetValueDiscountPercent>10</NetValueDiscountPercent>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Order taken by

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| TakenBy | Name | ZYNK | string | 30 | Optional | Will default to the username that Zynk connects to Sage with if not provided. |
| Priority | Name | A | string | 1 | Optional | Must be a single letter. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <TakenBy>ZYNK</TakenBy>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Delivery & Invoicing - Analysis codes
Analysis codes are imported from a collection, so you can import as many as are setup within Sage 200.  We lookup analysis codes by matching the Name from our XML to the Field Label in Sage.  The values that can be imported depend on how the analysis code is configured, if you need to import any value ensure Enter Free Text is enabled from Accounting System Manager -> Settings -> Maintain Analysis Codes.

|  XML Field | Sage Field  | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name | Analysis Code | Customer Type | string | 60 | Required | The analysis code must already exist, otherwise will not be added. |
| Value  | Value  | A | string | 60 | Optional | The value must already exist, unless Enter Free Text is enabled. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <AnalysisCodes>
        <AnalysisCode>
          <Name>Customer Type</Name>
          <Value>A</Value>
        </AnalysisCode>
        <AnalysisCode>
          <Name>Order Source</Name>
          <Value>Web</Value>
        </AnalysisCode>
      </AnalysisCodes>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Payment with Order - Record payment and invoice
To be able to import payments with orders you must ensure that you set PaymentRef to the Payment Method to use, and this must already exist in Sage.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| PaymentRef | Method  | Credit Card | string | 20 | Optional | Payment with order will not be used if a PaymentRef is not provided. |
| PaymentSecondRef | Reference  | Auth Code: 12345 | string | 20 | Optional | Will be set to PaymentRef if not provided|
| PaymentAmount | Payment  | 100 | double | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <PaymentRef>Credit Card</PaymentRef>
      <PaymentSecondRef>Auth Code: 12345</PaymentSecondRef>
      <PaymentAmount>100</PaymentAmount>
    </SalesOrder>
  </SalesOrders>
</Company>
```

## Additional Fields
If the external system you are integrating with does not provide the net and tax values for items you can optionally import orders as VAT inclusive.

| XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| VatInclusive | - | true | boolean | - | Optional | Will default to false if not provided.|

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <VatInclusive>true</VatInclusive>
    </SalesOrder>
  </SalesOrders>
</Company>
```
