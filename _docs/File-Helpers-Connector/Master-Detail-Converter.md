---
slug: master-detail-converter
redirect_from: "/article/245-master-detail-converter"
title: Master Detail Converter
---
This task accepts a text file and converts it to a XML file, using classes written in C#. This task supports converting hierarchical data (such as orders and their associated item lines), if the file you need to convert contains flat data, use the [Basic Converter](basic-converter) instead. Please note that this task only supports input files with two hierarchy levels, with master (i.e. parent) and detail (i.e. child) rows.

## Settings
### Detail Convert Class
_Required_  
The class written in the C# programming language to use to parse detail rows in the input file, see below for an example.	  
  
Attributes are used to define how each field in the class is parsed from the input file. See	[here](http://filehelpers.sourceforge.net/attributes.html) for a full list of the available attributes. See [here](http://filehelpers.sourceforge.net/converter_args.html) for a full list of the built in data conversions that can be used with the FieldConverter attribute.

### Master Convert Class
_Required_  
The class written in the C# programming language to use to parse master rows the input file, see below for an example.	  
  
This class must contain a public static method with a return type of FileHelpers.MasterDetail.RecordAction, and a single parameter of type string. Each row in the input file will be passed to this method, and it should return RecordAction.Master if the row is a master, and RecordAction.Detail if it is a detail row.	  
  
Attributes are used to define how each field in the class is parsed from the input file. See	[here](http://filehelpers.sourceforge.net/attributes.html) for a full list of the available attributes. See [here](http://filehelpers.sourceforge.net/converter_args.html) for a full list of the built in data conversions that can be used with the FieldConverter attribute. 

### Error File
_Required_  
The file to output any records to which did not convert successfully.

### Input File
_Required_  
The text file to be converted to XML.

### Output File
_Required_  
The output XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
To introduce the usage of the FileHelpers module within Zynk, we have based our tutorial on the data from the FileHelpers website.

[Easy Master/Details Example](filehelpers-master-detail-example) - simple example reading a master / detail file