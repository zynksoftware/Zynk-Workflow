---
slug: auto-mapper
redirect_from: "/article/367-auto-mapper"
title: Auto Mapper
---
This task will automatically map XML data to and from the Zynk XML format. It is typically used as a simple way to transform data provided by an external system (such as Amazon, Ebay, etc.) into a format which is ready for import into Sage.

The task works using a standard XSL transform, which can be customised to meet your specific requirements using the 'Customise Mapping' button within the mapping settings.

## Settings
### Input File
_Required_  
The input XML file containing the data you would like to transform.

### Mapping
_Required_  
This is where you specify how you would like the data to be mapped. See the 'Configuring the Mapping' section below for more details.

### Output File
_Required_  
The XML file the result should be saved to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Configuring the Mapping
To configure the mapping, click on the ellipsis (...) button on the 'Mapping' setting. You will then see a window like the one below.

[![Zynk Auto Mapper](http://www.zynk.com/images/zynk_auto_mapper.png "Zynk Auto Mapper")](http://www.zynk.com/images/zynk_auto_mapper.png)

1. Select the format of the input file from the drop down menu. For example, if you want to convert orders downloaded from Amazon, you should choose 'Amazon' as the input format.
2. Select the data type of the input file from the drop down menu. For example, if you want to convert orders downloaded from Amazon, you should choose 'Orders' as the data type.
3. Select the format you would like to map the input file to. For example, if you would like to output orders in Zynk's own XML format (Connect XML), you should choose 'Zynk XML' as the output file format.
4. Select the data type you would like to map the input file to. For example, if you would like to output orders in Zynk's own XML format (Connect XML), you should choose 'Orders' as the output file data type.
5. Once you have completed the first four steps, any parameters that are required to perform the mapping will be listed. If there are any parameters, you should enter an appropriate value for them in the 'Value' column. For example, if one of the parameters was 'Currency', you should enter the currency any monetary data is in. You also have the option to encrypt any sensitive data stored in parameters, by checking the 'Encrypt' box.
6. If necessary, you can customise the way the data is mapped by clicking the 'Customise Mapping' button. More details about how to customise the mapping can be found below.
7. Once you are finished setting up the mapping, click the 'Ok' button.

**Note:** If the drop down menus do not list the format or data type you are looking for, then Zynk cannot currently transform your data automatically. As an alternative, you can transform the data yourself using the [XSLT Transform](xslt-transform).

## Customising the Mapping
The mapping provided can be customised to match your specific requirements. You should only use this option if you have a good knowledge of using XSLT to transform XML data, tutorials for writing XSL transforms can be found at [W3 Schools](http://www.w3schools.com/xml/xsl_transformation.asp). Please note that the task only supports XSLT 1.0. Zynk Software cannot provide support for mappings which have been customised.

To customise the mapping, click the 'Customise Mapping' button, and you will see a window like the one below.

[![Zynk Auto Mapper Customise](http://www.zynk.com/images/zynk_auto_mapper_customise.jpg "Zynk Auto Mapper Customise")](http://www.zynk.com/images/zynk_auto_mapper.png)

The XSLT used in the mapping is displayed, and can be edited to match your specific requirements. Once you are finished modifying the XSLT, click the 'Save' button to save the changes. You can also use the 'Revert' button to revert back to the original XSLT. This can be useful if you have made a change to an XSLT that has causes an error to occur when the Auto Mapper task runs.

## Examples

Sample input file containing an Amazon order:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Orders>
  <Order AmazonOrderId="123-1234567-1234567" SellerOrderId="123-1234567-1234567" PurchaseDate="13/01/2013 18:46:35" LastUpdateDate="14/01/2013 15:31:09" OrderStatus="Shipped" FulfillmentChannel="AFN" SalesChannel="Amazon.co.uk" OrderChannel="" ShipServiceLevel="Standard" NumberOfItemsShipped="1" NumberOfItemsUnshipped="0">
    <ShippingAddress Name="Joe Bloggs" AddressLine1="Zynk Software" AddressLine2="Nelson House" AddressLine3="Jesmond" City="Newcastle" County="" District="" StateOrRegion="Tyne & Wear" PostalCode="NE2 3AE" CountryCode="GB" Phone="08451232920" />
    <OrderTotal CurrencyCode="GBP" Amount="5.16" />
    <OrderItems>
      <OrderItem ASIN="B0002JT1Q8" SellerSKU="LACO22103" Title="Laco Regular Soldering Flux 60g 22103" QuantityOrdered="1" QuantityShipped="1" GiftMessageText="">
        <ItemPrice CurrencyCode="GBP" Amount="5.16" />
        <ShippingPrice CurrencyCode="" Amount="0" />
        <GiftWrapPrice CurrencyCode="" Amount="0" />
        <ItemTax CurrencyCode="GBP" Amount="0.00" />
        <ShippingTax CurrencyCode="" Amount="0" />
        <GiftWrapTax CurrencyCode="" Amount="0" />
        <ShippingDiscount CurrencyCode="" Amount="0" />
        <PromotionDiscount CurrencyCode="GBP" Amount="0.00" />
      </OrderItem>
    </OrderItems>
  </Order>
</Orders>
```

Sample output file with the mapping set to Amazon Orders -> Zynk XML Sales Orders:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:zynk="http://www.zynk.com">
  <SalesOrders>
    <SalesOrder>
      <Id>123-1234567-1234567</Id>
      <CustomerId>123-1234567-1234567</CustomerId>
      <AccountReference>AMAZON</AccountReference>
      <SalesOrderNumber>123-1234567-1234567</SalesOrderNumber>
      <CustomerOrderNumber>2123-1234567-1234567</CustomerOrderNumber>
      <Currency>GBP</Currency>
      <TakenBy>Amazon</TakenBy>
      <VatInclusive>false</VatInclusive>
      <SalesOrderDate>2013-01-13T18:46:35</SalesOrderDate>
      <SalesOrderAddress>
        <Forename>Joe Bloggs</Forename>
        <Company>Joe Bloggs</Company>
        <Address1>Zynk Software</Address1>
        <Address2>Nelson House</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne & Wear</County>
        <Country>GB</Country>
        <Telephone>08451232920</Telephone>
      </SalesOrderAddress>
      <SalesOrderDeliveryAddress>
        <Forename>Joe Bloggs</Forename>
        <Company>Joe Bloggs</Company>
        <Address1>Zynk Software</Address1>
        <Address2>Nelson House</Address2>
        <Address3>Jesmond</Address3>
        <Town>Newcastle</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne & Wear</County>
        <Country>GB</Country>
        <Telephone>08451232920</Telephone>
      </SalesOrderDeliveryAddress>
      <SalesOrderItems>
        <Item>
          <Sku>LACO22103</Sku>
          <Name>Laco Regular Soldering Flux 60g 22103</Name>
          <QtyOrdered>1</QtyOrdered>
          <UnitPrice>5.16</UnitPrice>
        </Item>
      </SalesOrderItems>
      <Carriage>
        <Sku>CARRIAGE</Sku>
        <Name>Standard</Name>
        <QtyOrdered>1</QtyOrdered>
        <UnitPrice>0.00</UnitPrice>
      </Carriage>
    </SalesOrder>
  </SalesOrders>
</Company>
```
