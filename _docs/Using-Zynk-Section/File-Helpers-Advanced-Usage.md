---
slug: file-helpers-advanced-usage
redirect_from: "/article/632-file-helpers-advanced-usage"
title: File Helpers   Advanced Usage
---
This article is an introduction to using the FileHelpers Module within Zynk, based on the examples on the [FileHelpers site](http://www.filehelpers.com/).  

## Delimited Record
Using a C# class you can read in a flat file format representing nested data (the provided example represents customers and their orders) and convert to XML, which can then be used for further processing within Zynk Workflows e.g. with the XSLT Transform.

More information can be found on our [Master Detail Converter](master-detail-converter) article.

### Input File
Save the below to input.txt

```csv
ALFKI|Alfreds Futterkiste|Maria Anders|Sales Representative|Obere Str. 57|Berlin|Germany 
10248|ALFKI|5|04071996|01081996|16071996|3|32.38 
10249|ALFKI|6|05071996|16081996|10071996|1|11.61 
10251|ALFKI|3|08071996|05081996|15071996|1|41.34 
ANATR|Ana Trujillo Emparedados y helados|Ana Trujillo|Owner|Avda. de la Constitucia 2222|Mexico D.F.|Mexico 
10252|ANATR|4|09071996|06081996|11071996|2|51.3 
ANTON|Antonio Moreno Taquer­a|Antonio Moreno|Owner|Mataderos 2312|Mexico D.F.|Mexico
```

### C# Master Class
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

### C# Detail Class
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

### Zynk Settings
Create a new Workflow in Zynk, and drag on the Master Detail Converter task from the FileHelpers folder. Set the following settings on the task.

#### Detail Convert Class
Path to detail.cs (ensure this is set to type of File)

#### Master Convert File
Path to master.cs (ensure this is set to type of File)

#### Error File
error.txt

#### Input File 
Path to input.txt (ensure this is set to type of File)

#### Output File 
output.xml

## Fixed Length Record
Furthermore, using a C# class you can read in a fixed file format and convert to XML, which can then be used for further processing within Zynk Workflows e.g. with the XSLT Transform.

## Input File
Save the below to input.txt

The format is customer ID (5 characters), customer name (20 characters), balance (8 characters, 000000.00 format) and date created (8 characters, ddMMyyyy format).

```csv
01732Juan Perez           004350011052002 00554Pedro Gomez          123423406022004 
00112Ramiro Politti       000000001022000 00924Pablo Ramirez        033213024112002
```

### C# Master Class
Save the below to class.cs

```cs
[FixedLengthRecord()]  
public class Customer 
{      
    [FieldFixedLength(5)]      
    public int CustId;       
    
    [FieldFixedLength(20)]      
    // Trim any spaces to the right of the name     
    [FieldTrim(TrimMode.Right)]     
    public string Name;           
    
    [FieldFixedLength(8)]      
    // Convert this field using the custom converter TwoDecimalConverter     
    [FieldConverter(typeof(TwoDecimalConverter))]      
    public decimal Balance;           
    
    [FieldFixedLength(8)]      
    // Convert this field using the built in date converter     
    [FieldConverter(ConverterKind.Date, "ddMMyyyy")]      
    public DateTime AddedDate;           
    
    // A custom converter - converts a number stored in the form 00000000 to 000000.00     
    internal class TwoDecimalConverter: ConverterBase      
    {          
    	public override object StringToField(string from)          
    	{              
    		decimal res = Convert.ToDecimal(from);              
    		return res / 100;          
    	}                   
    
    	public override string FieldToString(object from)          
    	{              
    		decimal d = (decimal) from;              
    		return Math.Round(d * 100).ToString();          
    	}     
    }  
}
```

### Zynk Settings
Create a new Workflow in Zynk, and drag on the Basic Converter task from the FileHelpers folder. Set the following settings on the task.

#### Convert Class
Path to class.cs (ensure this is set to type of File)

#### Error File
error.txt (ensure this is set to type of File)

#### Input File
Path to input.txt (ensure this is set to type of File)

#### Output File
output.xml (ensure this is set to type of File)

### Output XML
After saving and running the Workflow, the output.xml file should contain the following XML representation of the input file.

```xml
<?xml version="1.0"?>
<ArrayOfAnyType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
	<anyType xsi:type="Customer">
		<CustId>1732</CustId>
		<Name>Juan Perez</Name>
		<Balance>435</Balance>
		<AddedDate>2002-05-11T00:00:00</AddedDate>
	</anyType>
	<anyType xsi:type="Customer">
		<CustId>554</CustId>
		<Name>Pedro Gomez</Name>
		<Balance>12342.34</Balance>
		<AddedDate>2004-02-06T00:00:00</AddedDate>
	</anyType>
	<anyType xsi:type="Customer">
		<CustId>112</CustId>
		<Name>Ramiro Politti</Name>
		<Balance>0</Balance>
		<AddedDate>2000-02-01T00:00:00</AddedDate>
	</anyType>
	<anyType xsi:type="Customer">
		<CustId>924</CustId>
		<Name>Pablo Ramirez</Name>
		<Balance>3321.3</Balance>
		<AddedDate>2002-11-24T00:00:00</AddedDate>
	</anyType>
</ArrayOfAnyType>
```