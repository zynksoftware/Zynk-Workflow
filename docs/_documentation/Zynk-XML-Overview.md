---
slug: zynk-xml-overview
title: Zynk XML Overview
---
To integrate with Sage 50, Sage 200 or Sage ACT! with Zynk you will need to import and export data using XML.  We have created a common XML schema to allow you to easily integrate your systems with Sage.

As each application uses the schema in different ways we have documented each one in turn, choose the application you are integrating with for detailed schema information.

 * [Sage 50 UK XML](sage-50-uk-xml)
 * [Sage 200 XML](sage-200-xml)

**Sample XML**  
Our schema consists of a main Company node which contains nodes for each of the data types we support.  Note that not all data types / fields are supported across all of the systems we integrate with, please view the application documentation to see what is supported.

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

**Field Types**  
Date Time Fields - date fields should be specified in XSD format
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <SalesOrderDate>2011-01-01T11:11:11</SalesOrderDate>
    </SalesOrder>
  </SalesOrders>
</Company>
```

Numeric Fields - numeric fields should have a valid number (an empty numeric node will cause an error when being deserialized)
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <ForeignRate>1.5</ForeignRate>
    </SalesOrder>
  </SalesOrders>
</Company>
```

If you don't need/want to specify the value of a numeric field, you can either exclude the node from the XML, or, specify the nodes xsl:nil value as true
```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrders>
    <SalesOrder>
      <ForeignRate xsi:nil="true" />
    </SalesOrder>
  </SalesOrders>
</Company>
```

**Import Errors**  
If there are any errors when importing a record, they will be added to the errors collection on the record and  will be written out to the fail file.  The errors can either be validation issues, import issues, or warnings if some data was skipped during the import.
```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <StockTransactions>
    <StockTransaction>
      <Errors>
        <Error>
          <Date>2013-06-06T09:16:14.5673107+01:00</Date>
          <Name>Stock Transaction Import</Name>
          <Description>Could not find specified Stock Item</Description>
        </Error>
      </Errors>
      <StockTransactionType>MovementOut</StockTransactionType>
      <StockCode>GREENFORK</StockCode>
      <StockTransactionDate>2012-11-23T00:00:00</StockTransactionDate>
      <Reference>123</Reference>
      <SecondReference>456</SecondReference>
      <Details>Exchange from WAREHOUSE1</Details>
      <Qty>3</Qty>
    </StockTransaction>
  </StockTransactions>
</Company>
```