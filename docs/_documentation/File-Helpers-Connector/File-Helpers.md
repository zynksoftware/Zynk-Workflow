---
slug: file-helpers
redirect_from: "/article/243-introduction-to-the-file-helpers-connector"
title: File Helpers
---
FileHelpers is an easy to use .NET library written in C# to read/write data from fixed length or delimited files or streams.

The FileHelpers Connector for Zynk allows you to use this functionality within your workflows to allow integration with custom file formats. The tasks use classes written in C# to read the input files, which will map each record to XML. You can use custom logic to convert data e.g. date/time fields, as well as support master/detail input formats where the input contains multiple related records.

A knowledge of the C# programming language is required to use the FileHelpers Connector, full documentation on the library can be found on the [FileHelpers](http://www.filehelpers.com/) site.

## Tasks
 * [Basic Converter](basic-converter)
 * [Master Detail Converter](master-detail-converter)

## Examples
To introduce the usage of FileHelpers within Zynk we have based our tutorials on the data from the FileHelpers website.

 * [Easy Example](file-helpers-basics) - simple example of reading in a pipe delimited file
 * [Master Details](master-detail-converter) - simple example reading a master / detail file
 * [Advanced Usage](file-helpers-advanced-usage) - example showing custom converters and fixed length files