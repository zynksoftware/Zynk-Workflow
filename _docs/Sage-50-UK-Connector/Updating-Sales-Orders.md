---
slug: updating-sales-orders
redirect_from: "/article/966-updating-sales-orders"
title: Updating Sales Orders
---
This task will update fields on existing Sales Orders in Sage 50, based on data supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Update Sales Order XML](sage-50-uk-update-sales-order-xml):

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <Id>123</Id>
      <SalesOrderNumber>2014</SalesOrderNumber>
      <CustomerOrderNumber>123</CustomerOrderNumber>
      <SalesOrderAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>i6 Building</Address1>
        <Address2>Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
        <Telephone>0191 123 2920</Telephone>
      </SalesOrderAddress>
      <SalesOrderDeliveryAddress>
        <Title>Mr</Title>
        <Forename>Joe</Forename>
        <Surname>Harrison</Surname>
        <Company>Zynk Software Limited</Company>
        <Address1>i6 Building</Address1>
        <Address2>Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
      </SalesOrderDeliveryAddress>
      <TakenBy>Frank</TakenBy>
      <Notes1>a note</Notes1>
      <Notes2>a note</Notes2>
      <Notes3>a note</Notes3>
      <Custom1>Analysis 1</Custom1>
      <Custom2>Analysis 2</Custom2>
      <Custom3>Analysis 3</Custom3>
    </SalesOrder>
  </SalesOrders>
</Company>
```