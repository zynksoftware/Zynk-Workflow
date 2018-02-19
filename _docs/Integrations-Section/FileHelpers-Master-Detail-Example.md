---
slug: filehelpers-master-detail-example
redirect_from: "/article/711-filehelpers-master-detail-example"
title: FileHelpers   Master Detail Example
---
This article is an introduction to using the FileHelpers Module within Zynk, based on the Master Detail Example on the [FileHelpers site](http://www.filehelpers.com/example_masterdetail.html).  Using a C# class you can read in a flat file format representing nested data (the provided example represents customers and their orders) and convert to XML, which can then be used for further processing within Zynk Workflows e.g. with the XSLT Transform.

The related Zynk support centre article, which provides more information about the task and its properties can be on [Master Detail Converter](master-detail-converter).

## Input File

Save the below to input.txt

```csv
ALFKI|Alfreds Futterkiste|Maria Anders|Sales Representative|Obere Str. 57|Berlin|Germany 
10248|ALFKI|5|04071996|01081996|16071996|3|32.38 
10249|ALFKI|6|05071996|16081996|10071996|1|11.61 
10251|ALFKI|3|08071996|05081996|15071996|1|41.34 
ANATR|Ana Trujillo Emparedados y helados|Ana Trujillo|Owner|Avda. de la Constituci 2222|Meico D.F.|Mexico 
10252|ANATR|4|09071996|06081996|11071996|2|51.3
```

## C# Master Class
Save the below to master.cs

```cs
[DelimitedRecord("|")] 
public class Customers 
{    
    public string CustomerID;    
    public string CompanyName;    
    public string ContactName;    
    public string ContactTitle;    
    public string Address;    
    public string City;    
    public string Country;     
    
    public static FileHelpers.MasterDetail.RecordAction ExampleSelector(string record)     
    {          
    	if (Char.IsLetter(record[0]))             
    		return FileHelpers.MasterDetail.RecordAction.Master;         
    	else             
    		return FileHelpers.MasterDetail.RecordAction.Detail;     
    } 
}
```

## C# Detail Class
Save the below to detail.cs

```cs
[DelimitedRecord("|")] 
public class Orders 
{    
    public int OrderID;    
    public string CustomerID;    
    public int EmployeeID;    
    public DateTime OrderDate;    
    public DateTime RequiredDate;    
    public DateTime ShippedDate;    
    public int ShipVia;    
    public decimal Freight; 
}
```

## Zynk Settings
Create a new Workflow in Zynk, and drag on the Master Detail Converter task from the FileHelpers folder. Set the following settings on the task.

| 	Section | 	Setting | 	Value |
| 	Convert Settings | 	Detail Convert Class | 	Path to detail.cs (ensure this is set to type of File) |
| 	Master Convert File | 	Path to master.cs (ensure this is set to type of File) |
| 	File Settings | 	Error File | 	error.txt |
| 	Input File  | 	Path to input.txt |
| 	Output File  | 	output.xml |

## Output XML

After saving and running the Workflow, the output.xml file should contain the following XML representation of the input file.

```xml
<?xml version="1.0"?>
<ArrayOfMasterDetails xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
	<MasterDetails>
		<Master xsi:type="Customers">
			<CustomerID>ALFKI</CustomerID>
			<CompanyName>Alfreds Futterkiste</CompanyName>
			<ContactName>Maria Anders</ContactName>
			<ContactTitle>Sales Representative</ContactTitle>
			<Address>Obere Str. 57</Address>
			<City>Berlin</City>
			<Country>Germany</Country>
		</Master>
		<Details>
			<anyType xsi:type="Orders">
				<OrderID>10248</OrderID>
				<CustomerID>ALFKI</CustomerID>
				<EmployeeID>5</EmployeeID>
				<OrderDate>1996-07-04T00:00:00</OrderDate>
				<RequiredDate>1996-08-01T00:00:00</RequiredDate>
				<ShippedDate>1996-07-16T00:00:00</ShippedDate>
				<ShipVia>3</ShipVia>
				<Freight>32.38</Freight>
			</anyType>
			<anyType xsi:type="Orders">
				<OrderID>10249</OrderID>
				<CustomerID>ALFKI</CustomerID>
				<EmployeeID>6</EmployeeID>
				<OrderDate>1996-07-05T00:00:00</OrderDate>
				<RequiredDate>1996-08-16T00:00:00</RequiredDate>
				<ShippedDate>1996-07-10T00:00:00</ShippedDate>
				<ShipVia>1</ShipVia>
				<Freight>11.61</Freight>
			</anyType>
			<anyType xsi:type="Orders">
				<OrderID>10251</OrderID>
				<CustomerID>ALFKI</CustomerID>
				<EmployeeID>3</EmployeeID>
				<OrderDate>1996-07-08T00:00:00</OrderDate>
				<RequiredDate>1996-08-05T00:00:00</RequiredDate>
				<ShippedDate>1996-07-15T00:00:00</ShippedDate>
				<ShipVia>1</ShipVia>
				<Freight>41.34</Freight>
			</anyType>
		</Details>
	</MasterDetails>
	<MasterDetails>
		<Master xsi:type="Customers">
			<CustomerID>ANATR</CustomerID>
			<CompanyName>Ana Trujillo Emparedados y helados</CompanyName>
			<ContactName>Ana Trujillo</ContactName>
			<ContactTitle>Owner</ContactTitle>
			<Address>Avda. de la Constitucia 2222</Address>
			<City>Mexico D.F.</City>
			<Country>Mexico</Country>
		</Master>
		<Details>
			<anyType xsi:type="Orders">
				<OrderID>10252</OrderID>
				<CustomerID>ANATR</CustomerID>
				<EmployeeID>4</EmployeeID>
				<OrderDate>1996-07-09T00:00:00</OrderDate>
				<RequiredDate>1996-08-06T00:00:00</RequiredDate>
				<ShippedDate>1996-07-11T00:00:00</ShippedDate>
				<ShipVia>2</ShipVia>
				<Freight>51.3</Freight>
			</anyType>
		</Details>
	</MasterDetails>
</ArrayOfMasterDetails>
```

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279. Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.