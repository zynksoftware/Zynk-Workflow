---
slug: exporting-customers-from-volo
title: Exporting Customers from Volo
---
This task will export customers from Volo to an XML file.

## Settings
### Connection
_Required_  
The Volo connection to use. See the [Connecting to Volo](connecting-to-volo) article if you require more information on how to create/manage connections.

### Email
_Optional_  
Enter an email address to filter the customers on. Use this option if you only want to export specific customers.

### Merchant Type
_Required_  
Select a merchant type to filter the customers on, or choose 'Any' to export customers regardless of their merchant type.

### Name
_Optional_  
Enter a name to filter the customers on. Use this option if you only want to export specific customers.

### Page Size
_Required_  
The number of customers to export per page. Increasing this value will speed up the export, but will consume more memory. Defaults to 50.

### Phone
_Optional_  
Enter a phone number to filter the customers on. Use this option if you only want to export specific customers.

### Postcode
_Optional_  
Enter a post code to filter the customers on. Use this option if you only want to export specific customers.

### Output File
_Required_  
The name of the XML file to export the customers to. Defaults to 'volo_export_customers.xml'. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
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
  </Customer>
</Customers>
```