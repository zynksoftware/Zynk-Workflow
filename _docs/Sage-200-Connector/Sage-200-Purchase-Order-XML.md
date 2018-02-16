---
slug: sage-200-purchase-order-xml
title: Sage 200 Purchase Order XML
---
Import Purchase Orders allows you to create new purchase orders with Sage 200, and optionally progress the order through the ordering process.  The Id field should be populated by the unique id of the order from the external system, Zynk uses this field to track orders already imported to prevent duplicates being created in Sage.    

Any Sage fields not documented below are not currently supported with our imports.

Sample import file for creating a basic purchase order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <Id>123</Id>
      <AccountReference>INTE001</AccountReference>
      <PurchaseOrderDate>2011-01-01T11:11:11</PurchaseOrderDate>
      <PurchaseOrderAddress>
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
      </PurchaseOrderAddress>
      <PurchaseOrderDeliveryAddress>
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
      </PurchaseOrderDeliveryAddress>
      <PurchaseOrderItems>
        <Item>
          <Sku>TEST01</Sku>
          <QtyOrdered>1</QtyOrdered>
          <UnitPrice>200</UnitPrice>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

In each of the following sections most of the XML has been omitted to make the samples easier to read, you will need to provide the above as a minimum to create a purchase order.  The whole structure of the Company schema is used below as a reference of where fields should be in the object model.

## Order Details - Account selection
To assign the order to a particular account you will need to specify either a SupplierId or an AccountReference in the XML. The SupplierId should correspond to a supplier that has already been imported into Sage via Zynk (see Import Suppliers).  The AccountReference should correspond to the Reference of a Sales Ledger account that exists within Sage.

|  XML Field | Sage Field  | Example  |  Field Type | Field Length  | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| SupplierId | - | 12345 |  string |  255 | Required, unless AccountReference is provided | Only used if an AccountReference is not provided. |
| AccountReference | A/C Ref | INTE001 |  string |  8 | Required, unless SupplierId is provided |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <AccountReference>INTE001</AccountReference>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Order Details - Order detail
All of the fields at the Order detail level are optional.  

Depending on the settings of the import task you can set the Order no of the created order.  If you have enabled Manual Order Numbering at the task level you can specify the PurchaseOrderNumber to use when creating the order, note this must be unique, and if already exists in Sage the order will not be imported.  You can specify the Document date of the order using PurchaseOrderDate.

| XML Field | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Id | - | 123 | string | 255 | Optional | Used for duplicate prevention, if the setting is enabled on the task. It is included in purchase order exports. |
| PurchaseOrderNumber | Order no | 12345 | int | 30 | Optional | Only used when the 'Manual Order Number' setting is enabled on the task, otherwise next number will be used. |
| PurchaseOrderDate | Document date | 2014-01-01T00:00:00 | date |  - | Optional | Will default to the current date if not provided. |
| PurchaseOrderRequestedDate  | Date requested  | 2014-01-01T00:00:00 | date | 11 | Optional | Will default to the current date if not provided. |
| SupplierOrderNumber | Supplier Reference no | 12345 | string | 30 | Optional |
| Currency | - | GBP | string | 3 | Optional | The three letter ISO currency code. It must match the currency of the supplier account. Will default to the currency on the supplier account if not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <Id>123</Id>
      <PurchaseOrderNumber>12345</SalesOrderNumber>
      <PurchaseOrderDate>2011-01-01T11:11:11</SalesOrderDate>
      <PurchaseOrderRequestedDate>2011-01-01T11:11:11</PurchaseOrderRequestedDate>
      <SupplierOrderNumber>12345</SupplierOrderNumber>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Order Details - Items
We currently support all item types within Sage 200.  All item types support the import of analysis codes, see below.

### Standard Items 
Setting the Type to either Stock, NonStock or Miscellaneous will import a standard item.  Depending on the settings on the import task you lookup a product based on either the Sku or Barcode fields.  You can import nominal analysis and project analysis with change lines, see below.

| XML Field | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sku | Code | PROD01 | string | 30 | Required, unless using barcode |
| Barcode |  - | 123456789 | string | 30 | Required, unless using sku | Only used for lookups, if enabled at the task level. |
| Location | Warehouse | Warehouse 1 | string | 30 | Optional | If not provided, will be set to a warehouse associated with the product based on the task settings. |
| Description | Description | Product 01 | string | 60 | Required | Will default to the name of the product if not provided. |
| TaxCode | Tax rate  | 1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitPrice | Unit price | 100 | decimal | - | Required |
| QtyOrdered | Quantity | 1 | decimal | - | Required |
| UnitOfSale | Buying unit | Each | string | 20 | Optional | Will default to the base unit if not provided. |
| UnitDiscountAmount | Unit discount | 10 | decimal | - | Optional | Will default to 0 if this or UnitDiscountPercentage is not provided. |
| UnitDiscountPercentage | Unit discount % | 10 | decimal | - | Optional | Only used if UnitDiscountAmount is not set. Defaults to 0 if this or UnitDiscountAmount is not set. |
|  RequestedDeliveryDate | Delivery dates Requested | 2011-01-01T11:11:11 | date | - | Optional | Will default to the RequestedDeliveryDate at the PurchaseOrder level if not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Type>Stock</Type>
          <Sku>PROD01</Sku>
          <Description>Product 01</Description>
          <Barcode>123456789</Barcode>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
          <TotalNet>100</TotalNet>
          <TotalTax>20</TotalTax>
          <TaxCode>1</TaxCode>
          <TaxRate>20</TaxRate>
          <UnitDiscountAmount>10</UnitDiscountAmount>
          <UnitDiscountPercentage>10</UnitDiscountPercentage>
          <RequestedDeliveryDate>2011-01-01T11:11:11</RequestedDeliveryDate>
          <Location>Warehouse 1</Location>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Service Items
You can import nominal analysis with change lines, see below.

| XML Field  | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sku | Code | SERV01 | string | 30 | Required |
| UnitPrice | Unit price | 100 | decimal | - | Required |
| QtyOrdered | Quantity | 1 | decimal | - | Required |
| TaxCode | Tax rate | 1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitDiscountAmount | Unit discount | 10 | decimal | - | Optional | Will default to 0 if this or UnitDiscountPercentage is not provided. |
| UnitDiscountPercentage* | Unit discount % | 10 | decimal | - | Optional | Only used if UnitDiscountAmount is not set. Defaults to 0 if this or UnitDiscountAmount is not set. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Type>Service</Type>
          <Sku>SERV01</Sku>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
          <TaxCode>1</TaxCode>
          <TaxRate>20</TaxRate>
          <UnitDiscountAmount>10</UnitDiscountAmount>
          <UnitDiscountPercentage>10</UnitDiscountPercentage>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Free Text Items
You can import nominal analysis and project analysis with change lines, see below. 

| XML Field | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Text | Item line description | Product 01 | string | 60 | Required, unless Description is set |
| Description | Item line description | Product 01 | string | 60 | Required, unless Text is set | Will only be used if Text is not set |
| UnitPrice | Unit price | 100 | decimal | - | Required |
| QtyOrdered | Quantity | 1 | decimal | - | Required |
| TaxCode | Tax rate | 1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitDiscountAmount | Unit discount | 10 | decimal | - | Optional | Will default to 0 if this or UnitDiscountPercentage is not provided. |
| UnitDiscountPercentage | Unit discount %  | 10 | decimal | - | Optional | Only used if UnitDiscountAmount is not set. Defaults to 0 if this or UnitDiscountAmount is not set. |
|  RequestedDeliveryDate | Delivery dates Requested | 2011-01-01T11:11:11 | date | - | Optional | Will default to the RequestedDeliveryDate at the PurchaseOrder level if not provided. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
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
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Additional Charge Lines
To import a charge line it must already be setup within Sage.  You can import nominal analysis and project analysis with change lines, see below.

| XML Field  | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Sku | Charge Code | DELIVERY | string | 30 | Required |
| Name | Charge Name | Delivery Charge | string | 60 | Required |
| TaxCode | Tax rate | 1 | int | - | Optional | If not provided, will be set to the tax code as determined by the Sage settings. |
| UnitPrice | Net Value | 100 | decimal | - | Required |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Type>ChargeLine</Type>
          <Sku>DELIVERY</Sku>
          <Name>Delivery Charge</Name>
          <TaxCode>1</TaxCode>
          <UnitPrice>100</UnitPrice>
          <QtyOrdered>1</QtyOrdered>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Comment Lines
Setting the Type to CommentLine will import a comment line.

| XML Field  | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Text | Item line description | Order comments | string | 60 | Required |
| ShowOnDocs | Show on customer documents | true | boolean | - | Optional | Only supported in Zynk v2.6 and above |
| ShowOnPickingList | Show on picking lists | true | boolean | - | Optional | Only supported in Zynk v2.6 and above |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <Type>CommentLine</Type>
          <Text>Order comments</Text>
          <ShowOnDocs>true</ShowOnDocs>
          <ShowOnPickingList>true</ShowOnPickingList>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Analysis Codes
Analysis codes are imported from a collection, so you can import as many as are setup within Sage 200.  We lookup analysis codes by matching the Name from our XML to the Field Label in Sage.  The values that can be imported depend on how the analysis code is configured, if you need to import any value ensure Enter Free Text is enabled from Accounting System Manager -> Settings -> Maintain Analysis Codes.

| XML Field | Sage Field  | Example  | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name | Analysis Code | Customer Type | string | 60 | Required | The analysis code must already exist, otherwise will not be added. |
| Value  | Value  | A | string | 60 | Optional | The value must already exist, unless Enter Free Text is enabled. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
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
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Nominal Analysis
The nominal specification supplied in the XML must exist within Sage 200.

| XML Field  | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| NominalCode | A/C Ref | 4000 | int | - | Optional |
| CostCentre | CC | 01 | string | 30 | Optional |
| Department | Dept | 01 | string | 30 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <NominalCode>4000</NominalCode>
          <CostCentre>01</CostCentre>
          <Department>01</Department>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

### Project Analysis
The project code and item supplied in the XML must exist within Sage 200.

| XML Field  | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| ProjectRef | Project Code | 0000000001 | string | 30 | Required |
| ProjectItem | Project Item | MATERIAL01 | string | 30 | Required |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderItems>
        <Item>
          <ProjectRef>0000000001</ProjectRef>
          <ProjectItem>MATERIAL01</ProjectItem>
        </Item>
      </PurchaseOrderItems>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Order Details - Exchange rate
The Currency field cannot be set directly on an order as this is set through the associated Purchase Ledger account.  Note that the exchange rate can only be set to 1 if the order is in the base currency.

| XML Field | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| ForeignRate | Rate | 1 | decimal | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <ForeignRate>1</ForeignRate>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Delivery & Invoicing - Delivery address
If a delivery address is provided we will use the data in the XML, otherwise we will fall back to use the invoice address of the customer from Sage.  Note the Address1 field is required, if this is blank we will also fall back to use the invoice address of the customer from Sage.  Note if Use segmented addresses is not enabled in Accounting System Manager -> System Settings certain fields will not be displayed in addresses. 

|  XML FIeld | Sage Field  | Example  | Field Type  | Field Length  | Input  | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Company | Postal name | Internetware | string | 60 | Optional | If not provided, will be built up from the Title, Forename and Surname. |
| Address1 | Address 1 | i6 Building | string | 60 | Optional |
| Address2 | Address 2 | 6-8 Charlotte Square | string | 60 | Optional |
| Address3 | Address 3 | string | 60 | Optional |
| Address4 | Address 4 | string | 60 | Optional |
| Town | City | Newcastle Upon Tyne | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| County | County | Tyne and Wear | string | 60 | Optional | Available in Sage 200 V6 and greater. Can only be set if 'Use Segmented Addresses' is enabled in Accounting System Manager -> System Settings. |
| Postcode | Postcode | NE1 4XF | string | 60 | Optional |
| Country | Country | GB | string | 2 | Optional | Should be the ISO2 country code. If a country name is provided, Zynk will try to map it to the appropriate county code. |
| ContactName | Contact | Test Person | string | 60 | Optional |
| Telephone | Telephone | 0845 123 2920 | string | 30 | Optional |
| Fax | Fax | 0845 123 2921 | string | 30 | Optional |
| Email | E-mail | support@internetware.co.uk | string | 60 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <PurchaseOrderDeliveryAddress>
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
      </PurchaseOrderDeliveryAddress>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Delivery & Invoicing - Tax details

| XML Field | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| TaxNumber | Tax number | 12345 | int | - | Optional |
| GlobalTaxCode | Tax code  | 1 | int | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <TaxNumber>12345</TaxNumber>
      <GlobalTaxCode>1</GlobalTaxCode>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Delivery & Invoicing - Invoice address
The invoice address is read from the associated supplier account.

## Delivery & Invoicing - Early settlement discount

| XML Field  | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| SettlementDiscount | Discount % | 10 | decimal | - | Optional |
| SettlementDays | if paid within  | 10 | int | - | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <SettlementDiscount>10</SettlementDiscount>
      <SettlementDays>10</SettlementDays>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Delivery & Invoicing - Order discount / surcharge
We currently only support adding order discounts.  You can provide either an amount or a percentage, and the percentage discount will be calculate based on the given values.

| XML Field  | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| NetValueDiscount | Discount % | 10 | decimal | - | Optional | Defaults to 0 if neither the NetValueDiscount or NetValueDiscountPercent is provided. |
| NetValueDiscountPercent | Discount % | 10 | decimal | - | Optional | If both nodes are provided the NetValueDiscount will be used. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <NetValueDiscount>10</NetValueDiscount>
      <NetValueDiscountPercent>10</NetValueDiscountPercent>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Delivery & Invoicing - Order taken by
If this field is not provided it will be set to the user setup within Zynk.

|  XML Field | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| TakenBy | Name | ZYNK | string | 30 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <TakenBy>ZYNK</TakenBy>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Delivery & Invoicing - Analysis codes
Analysis codes are imported from a collection, so you can import as many as are setup within Sage 200.  We lookup analysis codes by matching the Name from our XML to the Field Label in Sage.  Zynk will not automatically create analysis codes that do not exist in Sage, and will log a warning if an analysis code provided in the XML does not exist.  The values that can be imported depend on how the analysis code is configured, if you need to import any value ensure Enter Free Text is enabled from Accounting System Manager -> Settings -> Maintain Analysis Codes.

|  XML Field | Sage Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Name | Analysis Code | Customer Type | string | 30 | Optional | The analysis code must already exist, otherwise will not be added. |
| Value | Value | A | string | 30 | Optional | The value must already exist, unless Enter Free Text is enabled. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
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
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```

## Purchase Invoice Transaction
You can optionally generate a Purchase Invoice (PI) transaction on the Supplier account when importing purchase orders. To do this, make sure the Auto Receive Orders and Auto Invoice Orders settings on the Import Purchase Orders task are set to true.

|  XML Field | Sage Field  | Example  | Field Type  | Field Length  | Input  |
| --- | --- | --- | --- | --- | --- |
| InvoiceNumber | Reference | 123 | string | 20 | Required |
| InvoiceDate | Trans. Date | 2014-05-09T00:00:00 | dateTime | - | Required |
| InvoiceSecondReference | 2nd Reference | 456 | string | 20 | Optional |

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <PurchaseOrders>
    <PurchaseOrder>
      <InvoiceNumber>123</InvoiceNumber>
      <InvoiceDate>2014-05-09T00:00:00</InvoiceDate>
      <InvoiceSecondReference>456</InvoiceSecondReference>
    </PurchaseOrder>
  </PurchaseOrders>
</Company>
```