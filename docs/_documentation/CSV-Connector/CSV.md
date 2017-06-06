---
slug: csv
redirect_from: "/article/193-introduction-to-the-csv-connector"
title: CSV
---
Comma-Separated Value (CSV) files store data in plain text. Each line of the file is a data record. Each record consists of one or more fields, distinguished by the separator. 

As well as the required separator, an optional delimiter can be provided to denote the start and end of the fields, normally in instances where the separator character can appear in the data itself, i.e. If the comma `,` character were used as the field separator but could also appear in the data itself, then the speech mark `"` character could be used as the field delimiter, enclosing each field value.

The common use of the comma as a field separator is the source of the name for this file format.

The CSV Connector provides tasks that allow you to parse and manipulate CSV files and perform tasks for each record in that CSV file.

### Tasks

[CSV Repeater](csv-repeater)  
[Converting CSV to XML](converting-csv-to-xml)  

### Examples

An example of a simple CSV record using the comma `,` character as the field separator, and not using any field delimiter.

```csv
Order Number, Order Address Line, Order Value
1000000001, Nelson House, 200.00
```

An example of a simple CSV record using the comma `,` character as the field separator and the speech mark `"` as the field delimiter, notice that the second field (Order Address Line) contains the separator `,` character and therefore must be delimited, in this case using the speech mark 

```csv
Order Number, Order Address Line, Order Value
1000000001, "Nelson House, Fleming Business Centre, Jesmond, Newcastle upon Tyne", 200.00
```