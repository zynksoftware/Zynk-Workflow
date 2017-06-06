---
slug: sage-50-us-sales-order-xml
title: Sage 50 US Sales Order XML
---
Import Sales Orders allows you to create new sales orders in Sage 50 US.  We recommend that the ExternalId field be populated by the unique id of the customer from the external system, Zynk uses this field to track sales orders already imported to prevent duplicates being created in Sage.  

Any Sage fields not documented below are not supported with our imports, if there are additional fields you need contact us at support@zynk.com.  

Complete import file for creating a sales orders:-

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSalesOrder>
  <SalesOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>123</ExternalId>
    <CustomerReference>ARMSTRONG</CustomerReference>
    <ShipToAddress>
      <Name>Harding Consulting</Name>
      <Address>
        <Address1>2300 Club Drive</Address1>
        <Address2>Suite A</Address2>
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30093</Zip>
        <Country />
      </Address>
    </ShipToAddress>
    <Date>2015-03-02T00:00:00</Date>
    <ShipByDate>2015-03-02T00:00:00</ShipByDate>
    <ReferenceNumber>10322</ReferenceNumber>
    <IsDropShip>false</IsDropShip>
    <CustomerPurchaseOrderNumber />
    <ShipVia>None</ShipVia>
    <AccountReference>11000-00</AccountReference>
    <SalesTaxCodeReference>GAGWINN</SalesTaxCodeReference>
    <FreightAmount>0</FreightAmount>
    <FreightAccountReference>57500-00</FreightAccountReference>
    <CustomerNote />
    <PrintCustomerNoteAfterLineItems>false</PrintCustomerNoteAfterLineItems>
    <StatementNote>Thank you for choosing Bellwether Garden Supply!</StatementNote>
    <InternalNote />
    <SalesOrderLines>
      <SalesOrderLine>
        <Quantity>2.00</Quantity>
        <InventoryItemReference>BOOK-11010</InventoryItemReference>
        <Description>Bell-Grow Series: Gardening Handbook (Madison)</Description>
        <AccountReference>40000-BK</AccountReference>
        <UnitPrice>29.95</UnitPrice>
        <SalesTaxType>1</SalesTaxType>
  <JobReference>SHARP</JobReference>  
      </SalesOrderLine>
    </SalesOrderLines>
  </SalesOrder>
</ArrayOfSalesOrder>  
```

## Specifying Customer Record
When importing orders you have two options to specify the related customer record.  If you are importing customers and orders at the same time from a third party system you can use the AccountExternalId field to set the ExternalId of the customer.  As long as the customer record has been imported by Zynk, either on a different run or further up in the workflow, Zynk will be able to match the external id to the Sage assigned id.  Note any lookups done by Zynk are done per workflow, if you have multiple workflows importing data they will each have their own unique database so lookups will not work between the two.  Alternatively if you know the customer reference you can specify this in the order XML, but this account must already exist in Sage.  

The following samples show the two different methods.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>456</ExternalId> <!-- Third party database id of customer -->
    <Id>ALDRED</Id> <!-- Either third party generated or Sage generated customer id -->
  </Customer>
</ArrayOfCustomer>
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSalesOrder>
  <SalesOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>123</ExternalId>
    <AccountExternalId>456</AccountExternalId> <!-- If the customer reference is not known you can specify the related third party database id of the customer -->
    <CustomerReference>ALDRED</CustomerReference> <!-- Either third party generated or Sage generated customer id -->
  </SalesOrder>
</ArrayOfSalesOrder>  
```

In each of the following sections most of the XML has been omitted to make the samples easier to read.  The sections have been broken up into the various sections of the sales order record as viewed within Sage 50 US.

## Main Sales Order Fields
The below will let you specify the main fields required for a sales order record.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| N/A | ExternalId | 123 | string | 255 | Optional |
| N/A  | AccountExternalId  | 456 | string | 255 | Optional |
| Customer ID | CustomerReference | ARMSTRONG | string | 20 | Required, must exist in Sage as a customer |
| Name | ShipToAddress/Name | Harding Consulting  | string | 39 | Optional |
| Address Line 1 | ShipToAddress/Address1 | 2300 Club Drive | string | 30 | Optional |
| Address Line 2 | ShipToAddress/Address2 | Suite A | string | 30 | Optional |
| City | ShipToAddress/City | Norcross | string | 20 | Optional |
| St | ShipToAddress/State | GA | string | 2 | Optional |
| Zip | ShipToAddress/Zip | 30093 | string | 12 | Optional |
| Country  | Country  | string | 15 | Optional |
| Date | Date | 2015-03-02T00:00:00  | datetime | - | Optional, defaults to day of import |
| Ship by | ShipByDate  | 2015-03-02T00:00:00  | datetime  | - | Optional, defaults to day of import   |
| SO No | ReferenceNumber | 10322 | Optional, if provided must be unique, if left out will use the next available number from Sage |
| Drop ship | IsDropShip  | false | bool | - | Optional |
| Customer PO | CustomerPurchaseOrderNumber  | string | 20 | Optional |
| Ship via* | ShipVia | None | string | 20 | Optional |
| A/R account* | AccountReference  | 11000-00  | string | 15 | Optional |
| Sales tax*   | SalesTaxCodeReference  | GAGWINN  | string | 8 | Optional |
| Freight | FreightAmount | 0 | decimal | - | Optional |
| Freight account | FreightAccountReference  | 57500-00  | string   | 15 | Optional |
| Customer Note | CustomerNote  | string | 2000 |
| Print* | PrintCustomerNoteAfterLineItems  | false| bool | - | Optional |
| Statement Note | StatementNote | string | 160 |
| Internal Note | InternalNote | string | 2000 |

*   Ship via* - can only be what you have setup in Inventory Item Defaults on the Taxes/Shipping tab
*   A/R account* - can only be what you have setup in Sage under Maintain Chart of Accounts.
*   Sales Tax* - can only be what you have setup in Sage under Maintain -> Sales Taxes
*   Print* - set to false to use print Before Line Items, set to true to use print After Line Items

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSalesOrder>
  <SalesOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>123</ExternalId>
    <CustomerReference>ARMSTRONG</CustomerReference>
    <ShipToAddress>
      <Name>Harding Consulting</Name>
      <Address>
        <Address1>2300 Club Drive</Address1>
        <Address2>Suite A</Address2>
        <City>Norcross</City>
        <State>GA</State>
        <Zip>30093</Zip>
        <Country />
      </Address>
    </ShipToAddress>
    <Date>2015-03-02T00:00:00</Date>
    <ShipByDate>2015-03-02T00:00:00</ShipByDate>
    <ReferenceNumber>10322</ReferenceNumber>
    <IsDropShip>false</IsDropShip>
    <CustomerPurchaseOrderNumber />
    <ShipVia>None</ShipVia>
    <AccountReference>11000-00</AccountReference>
    <SalesTaxCodeReference>GAGWINN</SalesTaxCodeReference>
    <FreightAmount>0</FreightAmount>
    <FreightAccountReference>57500-00</FreightAccountReference>
    <CustomerNote />
    <PrintCustomerNoteAfterLineItems>false</PrintCustomerNoteAfterLineItems>
    <StatementNote>Thank you for choosing Bellwether Garden Supply!</StatementNote>
    <InternalNote />
  </SalesOrder>
</ArrayOfSalesOrder>  
```

## Item Line Fields
The below will let you specify the item line fields required for a sales order line.  You can provide multiple SalesOrderLine entries in the SalesOrderLines node.

| Sage Field | XML Field | Example | Field Type | Field Length | Input |
| --- | --- | --- | --- | --- | --- |
| Quantity | Quantity | 2 | decimal | - | Optional |
| Item | InventoryItemReference | BOOK-11010 | string | 20 | Required |
| Description | Description | Bell-Grow Series: Gardening Handbook (Madison) | string | 30 | Optional |
| GL Account* | AccountReference | 40000-BK | string | 15 | Optional |
| Unit Price | UnitPrice | 29.95 | decimal | - | Optional, must be 0 if Quantity is 0 |
| Tax | SalesTaxType | 1 | int | - | Optional |
| Job* | JobReference | SHARP  | string | 20 | Optional |

*   GL Account* - can only be what you have setup in Sage under Maintain Chart of Accounts. 
*   Job* - can only be what you have setup in Sage under Maintain Jobs.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfSalesOrder>
  <SalesOrder xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesOrderLines>
      <SalesOrderLine>
        <Quantity>2.00</Quantity>
        <InventoryItemReference>BOOK-11010</InventoryItemReference>
        <Description>Bell-Grow Series: Gardening Handbook (Madison)</Description>
        <AccountReference>40000-BK</AccountReference>
        <UnitPrice>29.95</UnitPrice>
        <SalesTaxType>1</SalesTaxType>
  <JobReference>SHARP</JobReference>  
      </SalesOrderLine>
    </SalesOrderLines>
  </SalesOrder>
</ArrayOfSalesOrder>  
```