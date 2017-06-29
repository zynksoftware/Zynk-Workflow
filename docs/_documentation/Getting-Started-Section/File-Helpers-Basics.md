---
slug: file-helpers-basics
redirect_from: "/article/630-file-helpers-basics"
title: File Helpers   Basics
---
 This article is an introduction to using the FileHelpers Module within Zynk, based on the Easy Example on the [FileHelpers site](http://www.filehelpers.net/example/QuickStart/ReadFileDelimited/).  Using a C# class you can read in data from a flat file format and convert to XML, which can then be used for further processing within Zynk Workflows e.g. with the XSLT Transform.        

More information on this task can be found on the [Basic Converter](http://workflow.zynk.com/converting-xml-files-to-csv) article.

## Input File
Save the below to input.txt

```CSV
10248|VINET|04071996|32.38 10249|TOMSP|05071996|11.61  
10250|HANAR|08071996|65.83 10251|VICTE|08071996|41.34
```

## C# Class
Save the below to class.cs

```cs
[DelimitedRecord("|")] 
public class Orders  
{ 	
    public int OrderID; 	
    public string CustomerID; 	
    
    [FieldConverter(ConverterKind.Date, "ddMMyyyy")]    	
    public DateTime OrderDate;  	
    
    public decimal Freight; 
}
```

## Zynk Settings
Create a new Workflow in Zynk, and drag on the Basic Converter task from the File Helpers folder.  Set the following            settings on the task.

### Convert Settings
Path to class.cs (ensure the data type is changed to File)      

### Error File 
error.txt

### Input File
Path to input.txt 

### Output File 
output.xml

## Output XML
After saving and running the Workflow, the output.xml file should contain the following XML representation of the data from            the input file.

```xml
<?xml version="1.0"?>
<ArrayOfAnyType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
	<anyType xsi:type="Orders">
		<OrderID>10248</OrderID>
		<CustomerID>VINET</CustomerID>
		<OrderDate>1996-07-04T00:00:00</OrderDate>
		<Freight>32.38</Freight>
	</anyType>
	<anyType xsi:type="Orders">
		<OrderID>10249</OrderID>
		<CustomerID>TOMSP</CustomerID>
		<OrderDate>1996-07-05T00:00:00</OrderDate>
		<Freight>11.61</Freight>
	</anyType>
	<anyType xsi:type="Orders">
		<OrderID>10250</OrderID>
		<CustomerID>HANAR</CustomerID>
		<OrderDate>1996-07-08T00:00:00</OrderDate>
		<Freight>65.83</Freight>
	</anyType>
	<anyType xsi:type="Orders">
		<OrderID>10251</OrderID>
		<CustomerID>VICTE</CustomerID>
		<OrderDate>1996-07-08T00:00:00</OrderDate>
		<Freight>41.34</Freight>
	</anyType>
</ArrayOfAnyType>
```

## Errors
If there are any errors during the convert they will be written out to the errors file if one is provided.  For example            introducing an invalid character to the date column would cause the following output.

FileHelpers - Errors Saved at 13 February 2015 11:23:19 
LineNumber | LineString |ErrorDescription 
4|"10251|VICTE|0807Z1996|41.34"|In the field 'OrderDate': Line: 4. Column: 13. Field: OrderDate. Error Converting '0807Z1996' to type: 'DateTime'.  There are more chars than in the format string: 'ddMMyyyy'
