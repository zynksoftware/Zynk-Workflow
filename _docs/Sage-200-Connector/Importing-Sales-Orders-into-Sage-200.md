---
slug: importing-sales-orders-into-sage-200
redirect_from: "/article/440-import-sales-orders"
title: Importing Sales Orders into Sage 200
---
This task will import new Sales Orders into Sage 200 from an XML file formatted in Zynk XML format.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Match Accounts On
_Optional_  
The settings to use to match customer accounts when an account reference is not provided in the input file.

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed sales orders in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported sales orders in Zynk XML format.

### Auto Acknowledge Order
_Required_  
Will automatically mark the order as acknowledged on saving the Sales Order.

### Auto Despatch Order
_Required_  
Will automatically mark the order as despatched on saving the Sales Order.

### Auto Post Invoice
_Required_  
Will automatically post the invoice on saving the Sales Order.

### Auto Print Order Invoice
_Required_  
Will automatically print the order invoice on saving the Sales Order.

### Auto Print Picking List
_Required_  
Choose whether picking lists should be printed. The following options are available:	

 * **Disabled** - Picking lists are never printed.
 * **AsSage** - Picking lists will be printed if enabled in Sage under SOP Settings > Automatically print picking list as part of order entry allocation.
 * **Always** - Picking lists will be printed regardless of the settings in Sage.

### Invoice Payments
_Required_  
Will automatically invoice payments on saving the Sales Order.

### Validate Delivery Dates
_Required_  
Set to true to validate the RequestedDeliveryDate and PromisedDeliveryDate provided in the input file. Validation will fail if either of these dates is in the past. Set to false to import the orders even if the delivery dates are in the past.

### Credit Check Limit
_Required_  
If accepting the order will place the account over their credit limit the order will be placed on hold.

### Manual Order Number
_Required_  
Specifies if the sales order number specified in the XML should be used or if Sage 200 should allocate the order numbers.

### Ready for Invoice Printing
_Required_  
If set to true marks the order as ready for invoice printing.

### VAT Settings
_Optional_  
Configure custom VAT settings to use when importing the orders.

### Auto Allocate Stock
_Required_  
Choose whether to allocate stock to the sales orders. The following options are available:	

 * **Disabled** - Stock will not be allocated to the sales order, even when 'Allocate stock on order entry' is enabled in the SOP settings.
 * **AsSage** - Stock will be allocated if 'Allocate stock on order entry' is enabled in the SOP settings.
 * **Always** - Stock will be allocated to the sales order, even when 'Allocate stock on order entry' is disabled in the SOP settings

### Auto Create Products
_Required_  
Will automatically create products if they do not exist in Sage 200.

### Default Carriage SKU
_Required_  
Allows you to specify a default stock code for carriage line.

### Default Category
_Required_  
Allows you to specify a default category for newly created items.

### Default Warehouse
_Required_  
Allows you to specify the default warehouse to use for newly created products.

### Product Lookup
_Required_  
Allows you to specify the field to use when searching for products. Acceptable fields are Sku or Barcode.

### Use Multiple Warehouses
_Required_  
Causes the allocation process to allocate from multiple warehouses rather than a single warehouse.

### Use Sales Trading Warehouse
_Required_  
Allows you specify only to use Warehouses marked for sales trading.

### Warehouse Sort Type
_Required_  
Allows you to override which warehouse to use e.g. Default, Highest Quantity or Lowest Quantity.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Printing Picking Lists
If you have the 'Auto Print Picking List' setting enabled on the task, Zynk will automatically print the picking list for the orders imported. In some cases, Zynk will not be able to print picking lists due to the following error: 'A Linq Data Model named 'Sage 200 Accounts' could not be found. Check the Data Model parameter in the connection string, and ensure a model with that name exists in the model repository.' If this occurs, you will need to copy the following files:

 * C:\Program Files\Sage200\Unity.config
 * C:\Users\[*your user name*]\AppData\Local\Sage\Sage200\AssemblyCache\Sage.Accounting.DataModel.dll

into the Zynk install directory (by default this is C:\Program Files\Internetware\Zynk).

## Examples
A sample input file for creating a sales order is shown below. See [Sage 200 Sales Order XML](sage-200-sales-order-xml) for more details on the Zynk XML Sales Order format for Sage 200.

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
        <Company>Zynk Software</Company>
        <Address1>Nelson House</Address1>
        <Address2>Fleming Business Centre</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle Upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
      </SalesOrderAddress>
      <SalesOrderDeliveryAddress>
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