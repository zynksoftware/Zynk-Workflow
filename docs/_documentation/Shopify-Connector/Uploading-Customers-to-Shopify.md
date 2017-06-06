---
slug: uploading-customers-to-shopify
redirect_from: "/article/311-uploading-customers-to-shopify"
title: Uploading Customers to Shopify
---
This task will upsert (insert or update) customers to your Shopify store, using the customer data in an XML file. If no customer ID is provided for a customer in the input file, the task will insert a new customer into Shopify. If an ID is provided, the existing customer will be updated.

## Settings
### Connection
_Required_  
The Shopify connection to use. See [Connecting to Shopify](connecting-to-shopify) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to output any failed uploads to.

### Input File
_Required_  
The XML file containing the new customers. They should be stored in the same format as the results returned by the Download Customers task.

### Success File
_Required_  
The XML file to output successful uploads to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below, showing two customers. The first is an example of updating an existing customer, and the second is an example of creating a new customer.
```xml
<?xml version="1.0" encoding="utf-8"?>
<customers type="array">
    <customer>
        <id type="integer">96430088</id>
        <accepts-marketing type="boolean">false</accepts-marketing>
        <note>Update</note>
    </customer>
    <customer>
        <first-name>New</first-name>
        <last-name>Customer3</last-name>
        <email>cust3@example.com</email>
        <addresses type="array">
            <address>
                <address1>123 Oak St</address1>
                <city>Ottawa</city>
                <province>ON</province>
                <phone>555-1212</phone>
                <zip>123 ABC</zip>
                <last-name>Lastnameson</last-name>
                <first-name>Mother</first-name>
                <country>CA</country>
            </address>
        </addresses>
    </customer>
</customers>
```