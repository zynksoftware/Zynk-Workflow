---
slug: exporting-sales-orders-from-volo
title: Exporting Sales Orders from Volo
---
This task will export orders from Volo to an XML file.

## Settings
### Connection
_Required_  
The Volo connection to use. See the [Connecting to Volo](connecting-to-volo) article if you require more information on how to create/manage connections.

### Export Credits
_Required_  
Set to true to include information about any credits associated with each of the orders. Defaults to false.

### Export Customers
_Required_  
Set to true to include information about the customers associated with each of the orders. Defaults to false.

### Export Settings > Date Created
_Required_  
The date to export orders from when the task is set to export new orders. This setting will update automatically each time an order is downloaded.

### Export Settings > Date Modified
_Required_  
The date to export orders from when the task is set to export modified orders. This setting will update automatically each time an order is downloaded.

### Export Settings > Export Modified, New or All Records
_Required_  
Choose which orders should be exported from Volo. The available options are:

* __All__ - Exports all orders.
* __Modified__ - Exports new and updated orders since the date shown in the Date Modified setting.
* __New__ - Exports new orders since the date shown in the Date Created setting.

### Order Status
_Optional_  
Enter an order status name to filter the orders on, or leave blank to export orders regardless of their status.

### Page Size
_Required_  
The number of orders to export per page. Increasing this value will speed up the export, but will consume more memory. Defaults to 50.

### Payment Status
_Required_  
Select a payment status to filter the orders on, or choose 'Any' to export orders regardless of their merchant type.

### Sale Type
_Required_  
Select a sale type to filter the orders on, or choose 'Any' to export orders regardless of their merchant type.

### Output File
_Required_  
The name of the XML file to export the orders to. Defaults to 'volo_export_sales_orders.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Order>
    <externalId />
    <orderType>Order</orderType>
    <orderSource>Manual</orderSource>
    <espOrderNo>1002</espOrderNo>
    <invoiceNumber>41220</invoiceNumber>
    <externalReference />
    <date>2017-02-28T13:49:10+00:00</date>
    <customerCompany>Zynk Software Ltd</customerCompany>
    <customerName>John Smith</customerName>
    <customerAddress1>i6 Building</customerAddress1>
    <customerAddress2>Charlotte Square</customerAddress2>
    <customerCity>Newcastle</customerCity>
    <customerCounty>Tyne &amp; Wear</customerCounty>
    <customerPostcode>NE1 4XF</customerPostcode>
    <customerCountry>UK</customerCountry>
    <customerEmail>support@zynk.com</customerEmail>
    <customerTelephone>0191 303 7279</customerTelephone>
    <deliveryCompany>Zynk Software Ltd</deliveryCompany>
    <deliveryName>John Smith</deliveryName>
    <deliveryAddress1>i6 Building</deliveryAddress1>
    <deliveryAddress2>Charlotte Square</deliveryAddress2>
    <deliveryCity>Newcastle</deliveryCity>
    <deliveryCounty>Tyne &amp; Wear</deliveryCounty>
    <deliveryPostcode>NE1 4XF</deliveryPostcode>
    <deliveryCountry>UK</deliveryCountry>
    <deliveryTelephone>0191 303 7279</deliveryTelephone>
    <shippingCost>1.99</shippingCost>
    <insurance>0</insurance>
    <discount>0.6</discount>
    <orderTotal>7.38</orderTotal>
    <paymentComplete>true</paymentComplete>
    <payments>
      <payment>
        <paymentMethod>Cash</paymentMethod>
        <paymentReference>1002</paymentReference>
        <payPalProtectionEligibility>false</payPalProtectionEligibility>
        <amount>11.38</amount>
        <paymentDate>2017-02-28T00:00:00+0000</paymentDate>
        <paymentId>2</paymentId>
        <postedBatchId>1234</postedBatchId>
      </payment>
      <payment>
        <paymentMethod>Cash</paymentMethod>
        <paymentReference>1002 Refund</paymentReference>
        <payPalProtectionEligibility>false</payPalProtectionEligibility>
        <amount>-4</amount>
        <paymentDate>2017-02-28T00:00:00+0000</paymentDate>
        <paymentId>3</paymentId>
        <postedBatchId>1234</postedBatchId>
      </payment>
    </payments>
    <currencyCode>GBP</currencyCode>
    <sellerId>0</sellerId>
    <buyerId />
    <orderItems>
      <item>
        <webProductID>3</webProductID>
        <stockNumber>100101#BLUE</stockNumber>
        <itemNumber>0</itemNumber>
        <productTitle>Esellerpro Executive Pen (BLUE)</productTitle>
        <quantity>1</quantity>
        <unitCost>5.99</unitCost>
        <taxRate>20</taxRate>
        <unitCostIncludesTax>Y</unitCostIncludesTax>
        <weight>0</weight>
        <productFolderName>Stationary</productFolderName>
        <locationId>2</locationId>
        <supplierId>1</supplierId>
        <kitType />
        <kitMaster />
      </item>
      <item>
        <webProductID>2</webProductID>
        <stockNumber>100101#RED</stockNumber>
        <itemNumber>0</itemNumber>
        <productTitle>Esellerpro Executive Pen (RED)</productTitle>
        <quantity>1</quantity>
        <unitCost>4</unitCost>
        <taxRate>20</taxRate>
        <unitCostIncludesTax>Y</unitCostIncludesTax>
        <weight>0</weight>
        <productFolderName>Stationary</productFolderName>
        <locationId>2</locationId>
        <supplierId>1</supplierId>
        <kitType />
        <kitMaster />
      </item>
    </orderItems>
    <orderCredits>
      <orderCredit>
        <creditNoteNumber>9000001</creditNoteNumber>
        <creditNoteDate>2017-02-28T00:00:00+0000</creditNoteDate>
        <shippingRefunded>0</shippingRefunded>
        <insuranceRefunded>0</insuranceRefunded>
        <discountRefunded>0</discountRefunded>
        <price>4</price>
        <cancelReason />
        <stockNumber>100101#RED</stockNumber>
        <quantityRefunded>1</quantityRefunded>
      </orderCredit>
    </orderCredits>
    <orderStatus>Waiting for Delivery</orderStatus>
    <fulfilmentType>MERCHANT</fulfilmentType>
    <webOrderID>0</webOrderID>
    <invoiceDate>2017-02-28</invoiceDate>
    <tradeSale>false</tradeSale>
    <customer>
      <externalId />
      <id>2</id>
      <name>John Smith</name>
      <accountsCode>ZYN001</accountsCode>
      <creditLimit>1000</creditLimit>
      <availableCredit>500</availableCredit>
      <companyName>Zynk Software Ltd</companyName>
      <emailAddress>support@zynk.com</emailAddress>
      <phoneNumber>0191 303 7279</phoneNumber>
      <addressLine1>i6 Building</addressLine1>
      <addressLine2>Charlotte Square</addressLine2>
      <city>Newcastle</city>
      <county>Tyne &amp; Wear</county>
      <postcode>NE1 4XF</postcode>
      <country>UK</country>
    </customer>
  </Order>
</Orders>
```