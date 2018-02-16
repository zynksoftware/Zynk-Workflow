---
slug: basic-converter
redirect_from: "/article/244-basic-converter"
title: Basic Converter
---
This task accepts a text file and converts it to an an XML file, using a class written in C#. This task supports converting flat data, if the file you need to convert contains hierarchical data (such as orders and their associated item lines), use the [Master Detail Converter](master-detail-converter) instead.


## Settings
### Convert Class
_Required_  
The class written in the C# programming language to use to parse the input file, see below for an example. Attributes are used to define how each field in the class is parsed from the input file. See	[here](http://filehelpers.sourceforge.net/attributes.html) for a full list of the available attributes. See [here](http://filehelpers.sourceforge.net/converter_args.html) for a full list of the built in data conversions that can be used with the FieldConverter attribute.

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
To introduce the usage of File Helpers within Zynk we have based our tutorial on the data from the File Helpers website.

[Easy Example](file-helpers-basics) - simple example of reading in a pipe delimited file