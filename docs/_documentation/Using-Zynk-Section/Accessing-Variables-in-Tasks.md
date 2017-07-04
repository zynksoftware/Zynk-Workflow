---
slug: accessing-variables-in-tasks
redirect_from: "/article/50-accessing-variables-in-tasks"
title: Accessing Variables in Tasks
---
Variables can be used as the value for any task setting which accepts a [Zynk Object](zynk-objects). Variables can also be accessed in templates. How to access the variable depends on the type of the variable:

## Accessing System, Global and Workflow Variables
You can use system, global and workflow variables for task settings using the 'Use a variable from the list below' option on the Zynk Object Editor. Simply select the name of the variable from the list provided, and it's value will be used as the value for the setting.

## Accessing Other Variable Types With Razor
Razor can be used to access any type of variable in Zynk (except for system variables), and it's value can be used for a task setting or in a template. To use a variable for a task setting, you must enable the 'Use Razor Engine' option in the Zynk Object Editor. To access a variable with razor, reference the system Context and then choose the correct collection within that context, depending on the type of the variable.

Types of Variables and how to access them:-

| Type | Description | Example |
| --- | --- | --- |
| 	 Application | 	 A setting contained in the Global Variables collection in Zynk | 	 @Context.Application["EmailAddress"] |
| 	 Workflow | 	 A setting contained in the Workflow Variables collection | 	 @Context.Workflow["ServerPath"] |
| 	 Template | 	 A setting contained in the Template Variables collection | 	 @Context.Template["CompanyName"] |
| 	 Current | 	 A value from the current record in a Repeater task     | 	 @Context.Current["id"]                      |
| 	 Object | 	 Access to the current record in a Repeater task | 	 @Context.Object.SelectSingleNode("Name").InnerText	  
	(Assuming an XML Repeater Task) |

## Context Object for Repeater Tasks
A context object will contain a .NET object representing the current record within a repeater task. The type of the object will depend on the repeater task being used, the following table describes the different supported repeater tasks:

| Task | Object Type | Example | Documentation |
| --- | --- | --- | --- |
| 	 File Repeater | 	 System.IO.FileInfo | 	 @Context.Object.FullName | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.io.fileinfo.aspx) |
| 	 XML Repeater | 	 System.Xml.XmlNode | 	 @Context.Object.SelectSingleNode("Name").InnerText | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.xml.xmlnode.aspx) |
| 	 Excel Repeater | 	 System.Data.DataRow | 	 @Context.Object[0].ToString() | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.data.datarow.aspx) |
| 	 CSV Repeater | 	 System.Data.DataRow | 	 @Context.Object[0].ToString() | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.data.datarow.aspx) |
| 	 ODBC Repeater | 	 System.Data.DataRow | 	 @Context.Object["NAME"].ToString() | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.data.datarow.aspx) |
| 	 OleDB Repeater | 	 System.Data.DataRow | 	 @Context.Object[0].ToString() | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.data.datarow.aspx) |
| 	 MSSQL Repeater | 	 System.Data.DataRow | 	 @Context.Object[0].ToString() | 	 	[MSDN Documentation](http://msdn.microsoft.com/en-us/library/system.data.datarow.aspx) |

## Example
In this example the current variables from a [CSV Repeater](csv-repeater) task are used to dynamically set the output filename on a sub-task, based on the order numbers in this CSV file:

```csv
OrderNumber,CustomerId,Total 
1250,32343,25.90 
1251,74322,129.99 
1252,87036,42.50
```

In the Zynk Object Editor for the output file setting on the sub-task, select the 'Use the following file' option and enter @(Context.Current["OrderNumber"]).csv in the box below. Remember to also select the 'Use Razor Engine' option. This will result in the sub-task creating the following output files in the workflow's data directory: `1250.csv`, `1251.csv`, `1252.csv`.

Please note that if you are using a period in the file name, you must encase the Razor variable in brackets eg. `@(Context.Current["OrderNumber"]).csv`
