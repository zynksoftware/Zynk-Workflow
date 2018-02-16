---
slug: converting-json-to-xml
redirect_from: "/article/255-converting-json-to-xml"
title: Converting JSON to XML
---
This task will automatically convert a JSON file to an equivalent XML format.

## Settings

### Root Element Name
_Optional_  
The root element name to use in the output XML. Only required when the input JSON does not have a single root.

### Input File
_Required_  
An absolute or relative file path on the local computer or network to the file containing the JSON to convert. 

See the [Zynk Objects](zynk-objects) if you require more information on how the Zynk Object file value works. 

This will be defaulted to the 'Output from the previous task'

### Output File
_Required_  
An absolute or relative file path on the local computer or network to save the converted XML file to. 

See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works. 

This will be defaulted to `json_to_xml.xml` in the current working directory.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the[Converting Between JSON and XML](json-and-xml-integration) article.

Sample input file:

```json
{
    "Customer":
    [
    {
        "firstName": "John",
        "lastName": "Smith",
        "age": 25,
        "address":
        {
        "streetAddress": "21 2nd Street",
        "city": "New York",
        "state": "NY",
        "postalCode": "10021"
        },
        "phoneNumber":
        [
        {
            "type": "home",
            "number": "212 555-1234"
        },
        {
            "type": "fax",
            "number": "646 555-4567"
        }
        ]
    },
    {
        "firstName": "Joe",
        "lastName": "Bloggs",
        "age": 32,
        "address":
        {
        "streetAddress": "Nelson House",
        "city": "Jesmond",
        "state": "Tyne &amp; Wear",
        "postalCode": "NE2 3AE"
        },
        "phoneNumber":
        [
        {
            "type": "home",
            "number": "212 555-1234"
        },
        {
            "type": "fax",
            "number": "646 555-4567"
        }
        ]
    }
    ]
}
```

Sample output file (when Root Element is set to 'Customers'):

```xml
<?xml version="1.0"?>
<Customers>
  <Customer>
    <firstName>John</firstName>
    <lastName>Smith</lastName>
    <age>25</age>
    <address>
      <streetAddress>21 2nd Street</streetAddress>
      <city>New York</city>
      <state>NY</state>
      <postalCode>10021</postalCode>
    </address>
    <phoneNumber>
      <type>home</type>
      <number>212 555-1234</number>
    </phoneNumber>
    <phoneNumber>
      <type>fax</type>
      <number>646 555-4567</number>
    </phoneNumber>
  </Customer>
  <Customer>
    <firstName>Joe</firstName>
    <lastName>Bloggs</lastName>
    <age>32</age>
    <address>
      <streetAddress>Nelson House</streetAddress>
      <city>Jesmond</city>
      <state>Tyne & Wear</state>
      <postalCode>NE2 3AE</postalCode>
    </address>
    <phoneNumber>
      <type>home</type>
      <number>212 555-1234</number>
    </phoneNumber>
    <phoneNumber>
      <type>fax</type>
      <number>646 555-4567</number>
    </phoneNumber>
  </Customer>
</Customers>
```