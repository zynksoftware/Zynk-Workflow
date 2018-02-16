---
slug: importing-orders-to-brightpearl
redirect_from: "/article/178-uploading-orders-to-brightpearl"
title: Importing Orders to Brightpearl
---


This task will create new orders in Brightpearl from an XML file. Please note that the task does not support updating existing orders.


## Settings

### Connection 
_Required_
The Brightpearl connection to use. See [Connecting to Brightpearl](connecting-to-brightpearl)

### Fail File
_Required_
The file to save failed records to.

### Input File
_Required_
The file containing records to import.

### Success File
_Required_
The file to save successful records to.

### Default SKU
_Optional_
You can optionally enter a default SKU to use when a matching product is not found in Brightpearl. If left blank, and no match is found, the item line will fail to import to Brightpearl. 

### Prevent Reprocessing
_Required_
Set to true to prevent the same records being processed more than once, based on the value of the `externalId` element in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file containing the minimum information required to create an order:


```xml
<?xml version="1.0"?>
<ArrayOfOrder>
	<Order>
		<externalId>5230</externalId>
		<orderTypeCode>SO</orderTypeCode>
		<reference>Order 1234</reference>
		<placedOn>2014-09-23T15:00:00+01:00</placedOn>
		<delivery>
			<deliveryDate>2014-09-26T00:00:00+01:00</deliveryDate>
		</delivery>
		<currency>
			<accountingCurrencyCode>GBP</accountingCurrencyCode>
			<orderCurrencyCode>GBP</orderCurrencyCode>
		</currency>
		<parties>
			<customer>
				<contact>
					<communication>
						<emails>
							<PRI>
								<email>demo@test.com</email>
							</PRI>
						</emails>
					</communication>
				</contact>
			</customer>
		</parties>
		<orderRows>
			<item>
				<key>1</key>
				<value>
					<product>
						<identity>
							<sku>IPHONE</sku>
						</identity>
					</product>
					<productName>IPhone</productName>
					<quantity>
						<magnitude>1</magnitude>
					</quantity>
					<rowValue>
						<rowNet>
							<currencyCode>GBP</currencyCode>
							<value>200</value>
						</rowNet>
					</rowValue>
				</value>
			</item>
		</orderRows>
	</Order>
</ArrayOfOrder>
```