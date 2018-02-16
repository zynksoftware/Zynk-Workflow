---
slug: using-xml-split
redirect_from: "/article/628-using-xml-split"
title: Using XML Split
---
The XML Split task will allow you to separate out a large XML file into a set of smaller XML files. The following properties are available to configure the XML Split task

## Settings
### Input File 
Use the following file: product_export.xml 

### Output Folder 
Use the following file: Stock Export 

### Record Limit
200  

### XPath Query  
Use the following text or script: /Company/Products/Product 

Typically, the XML Split task will be used in conjunction with a File Repeater task, which will loop over each of the smaller "chunked" files and perform some operation with each of the files in sequence.

A common use case that we come across is when integrating with websites which are running scripts expecting XML data via a HTTP POST. In some of these scenarios, when uploading data which grows over time (such as stock records), it is necessary to firstly limit the amount of data that will be contained within the files to be posted (using the XML Split task).



Our [Website Script Based Integration](website-script-based-integration) article covers integrating with a simple website running integration scripts, and contains a sample workflow can be found on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples) (which makes use of the XML Split and File Repeater tasks).