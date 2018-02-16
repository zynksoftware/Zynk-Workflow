---
slug: xml-repeater
redirect_from: "/article/357-xml-repeater"
title: XML Repeater
---
The XML Repeater task can be used to loop through an XML file and call a number of sub-tasks with the results from each row of data that was specified. For e.g. providing `Company/Customers/Customer` as the XPath Query would loop through all Customer records within the XML file.

## Settings
### Input File
_Required_  
The XML file to be processed.

### XPath Query
_Required_  
Enter an XPath query that specifies the rows of data to repeat over e.g. `Company/Products/Product`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The value of each node and attribute in the XML is available to each sub-task as a variable. To use these variables, reference them in templates as `@Context.Current["NodeName"]`, or within other task settings using the Razor option. Using the following XML sample, and an XPath of `Company/Customers/Customer`, you will be able to access all top level nodes from the customer node using `@Context.Current["AccountReference"]`.  

| Node Name | Razor Code | Data |
| --- | --- | --- |
| AccountReference | @Context.Current["AccountReference"] | A1D001 |
| CompanyName | @Context.Current["CompanyName"] | A1 Design Services |
| Balance | @Context.Current["Balance"] | 0 |

Note, we do not currently support reading child nodes, in this example you will not be able to access the Forename from CustomerInvoiceAddress. If you need to access child nodes you can use `@Context.Object` to get access to the current XmlNode, e.g. `@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Forename").InnerText`.

| Node Name | Razor Code | Data |
| --- | --- | --- |
| Forename | @Context.Object.SelectSingleNode("CustomerInvoiceAddress/Forename").InnerText | 	Jim |
| 	Surname | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Surname").InnerText | 	Thomas |
| 	Company | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Company").InnerText | 	A1 Design Services |
| 	Address1 | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Address1").InnerText | 	67a Station Road |
| 	Address2 | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Address2 ").InnerText |
| 	Town | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Town").InnerText | 	Blackpool |
| 	Postcode | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Postcode").InnerText | 	BP12 7HT |
| 	County | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/County").InnerText | 	Lancashire |
| 	Country | 	@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Country").InnerText | 	GB |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <AccountReference>A1D001</AccountReference>
      <CompanyName>A1 Design Services</CompanyName>
      <Balance>0</Balance>
      <CustomerInvoiceAddress>
        <Forename>Jim</Forename>
        <Surname>Thomas</Surname>
        <Company>A1 Design Services</Company>
        <Address1>67a Station Road</Address1>
        <Address2 />
        <Town>Blackpool</Town>
        <Postcode>BP12 7HT</Postcode>
        <County>Lancashire</County>
        <Country>GB</Country>
      </CustomerInvoiceAddress>
    </Customer>
    <Customer>
      <AccountReference>BBS001</AccountReference>
      <CompanyName>Bobs Building Supplies</CompanyName>
      <Balance>4309.77</Balance>
      <CustomerInvoiceAddress>
        <Forename>Susan</Forename>
        <Surname>Livingstone</Surname>
        <Company>Bobs Building Supplies</Company>
        <Address1>Timber Yard</Address1>
        <Address2>123 Prescot Way</Address2>
        <Town>Alnwick</Town>
        <Postcode>AL12 6GH</Postcode>
        <County>Northumberland</County>
        <Country>GB</Country>
      </CustomerInvoiceAddress>
    </Customer>
  </Customers>
</Company>
```

## Examples
For usage of the XML Repeater task please see our [XML / XSLT Examples](create-an-xslt-file) tutorial. 