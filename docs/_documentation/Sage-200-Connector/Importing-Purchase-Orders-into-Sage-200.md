---
slug: importing-purchase-orders-into-sage-200
redirect_from: "/article/439-import-purchase-orders"
title: Importing Purchase Orders into Sage 200
---
This task will import new Purchase Orders into Sage 200 from an XML file formatted in Zynk XML format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Match Accounts On
_Optional_  
The settings to use to match supplier accounts when an account reference is not provided in the input file.

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed purchase orders in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported purchase orders in Zynk XML format.

### Auto Invoice Orders
_Required_  
Will automatically invoice the imported orders. You must also set the Auto Receive Orders setting to true for this to work.

### Auto Receive Orders
_Required_  
Will automatically receive the imported orders.

### Credit Check Limit
_Required_  
If accepting the order will place the account over their credit limit the order will be placed on hold.

### Manual Order Number
_Required_  
Specifies if the purchase order number specified in the XML should be used or if Sage 200 should allocate the order numbers.

### Prevent Duplicates
_Required_  
If set to true will prevent a prevent Sales Orders with the same Id as a previously imported Sales Order from importing into Sage 200 .

### Prices Include Tax
_Required_  
If set to true if the price in the XML are tax inclusive.

### Vat Settings
_Optional_  
Configure custom VAT settings to use when importing the orders.

### Auto Create Products
_Required_  
Set to 'True' to automatically create a product in Sage if an item specified on the purchase order does not already exist.

### Default Category
_Optional_  
The default category for newly created products.

### Default Warehouse
_Optional_  
Allows you to specify the default warehouse to use when the location is not specified in the input file.

### Product Lookup
_Required_  
Allows you to specify the field to use when searching for products. Acceptable fields are Sku or Barcode.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for creating a purchase order is shown below. See our [Sage 200 Purchase Order XML](sage-200-purchase-order-xml) for more details on the Zynk XML Purchase Order format for Sage 200.

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
        <Company>Zynk Software</Company>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
      </PurchaseOrderAddress>
      <PurchaseOrderDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Test</Forename>
        <Surname>Person</Surname>
        <Company>Zynk Software</Company>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
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