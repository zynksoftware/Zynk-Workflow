---
slug: using-data-repeaters
redirect_from: "/article/622-using-data-repeaters"
title: Using Data Repeaters
---
In this tutorial we will create a more advanced workflow that queries an XML data set using the [XML Repeater](xml-repeater) (you could also use the [CSV Repeater](csv-repeater), [Excel Repeater](excel-repeater-task), [MS SQL Repeater](ms-sql-repeater), [ODBC Repeater](odbc-repeater), [OLEDB Repeater](oledb-repeater) or [File Repeater](file-repeater)) and we want to output each of the records to our PC as personalised letters which could then be Emailed or sent to PDF for printing. 

First we need to create some support files for the tutorial, open your text editor and create the two files at the end of this topic and save them to your C drive as Accounts.xml and Template.xml (Tip you can just copy and paste the info below)

Building the Workflow


1. Open Zynk and click on the New Workflow button or choose File > New from the main menu
2. You should now see the Task Library pane displayed, Click on the XML Library and then Double-click (or Drag and drop) the XML Repeater to copy that task into the Tasks List
3. Set Input File to `C:\accounts.xml`
4. Set XPath Query to QueryResult/records this is basically mimics the directory structure of the XML file, the root element being QueryResult and the rows being records elements
5. Next, locate the Razor Template task in the Zynk library and you need to drag it and drop it *on top* of the XML Repeater - don not worry if you get this wrong, just delete the task and try again.
6. Set Output File to `c:\output.txt`
7. Set Prepend Timestamp to True this will prepend the timestamp to each file so the filename is unique,
8. Set Template File to `c:\template.txt`
9. Set Timestamp format to `yyyyMMddHHmmssffff`
10. Locate the Zynk Library in the Task Library pane and add the Start Process task to the Task Builder
11. Click on the Save button and enter the name Tutorial 2 for the name of the Workflow and click OK
12. Click on the Run Workflow button
13. Look in the My Computer > C drive and you find 3 files have been created `namedyyyyMMddHHmmssffff\output.txt`
14. Congratulations you have just completed the Advanced workflow tutorial

TIP: You can also use a Context variable for the Output File and set the Output File to `c:\output_for_@(Context.Current["Id"]).txt` which will create files using the Account Id rather than a random timestamp, ensure when you do this you tick the box to tell Zynk to render the Output File through the Razor engine.

Accounts.xml - Save to your C drive

```xml
<?xml version="1.0" encoding="utf-8"?>
<QueryResult>
	<records type="Account">
		<Id>0014000000LfPszAAF</Id>
		<Name>Sian Jones</Name>
	</records>
	<records type="Account">
		<Id>0014000000HuWNqAAN</Id>
		<Name>Jeans Point Limited</Name>
	</records>
	<records type="Account">
		<Id>0014000000HuWNtAAN</Id>
		<Name>Waterside Communications Limited</Name>
	</records>
</QueryResult>
```

Template.txt - Save to your C drive

```csv
Dear @Context.Current["Name"]  <br>Thank you for your recent email, we have one of our team looking into the situation now.<br>  For your reference, your Account number is @Context.Current["Id"] Kind Regards,<br>Jennifer Becksworth<br>Office Manager
```