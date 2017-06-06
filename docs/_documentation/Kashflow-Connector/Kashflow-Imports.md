---
slug: kashflow-imports
redirect_from: "/article/941-kashflow-uploads"
title: Kashflow Imports
---


Kashflow upload tasks will upload information based on the data you provide.


## Settings

### Connection
_Required_
The Kashflow connection to use.

### Fail File
_Required_
The file that failed records will be written to. 

### Input File
_Required_
The file containing the records you wish to import.

### Success File
_Required_
The file that successful records will be written to.

### Matching


All import records are matched based on the Id field you provide in the XML, as demonstrated in each individual task article. In some cases, additional matching will be supported based on the data you provide and the data that is present in Kashflow. For example, customers can also be matched on code, email address and postcode.



**Invoice Lines** can be matched to their relevant Sub Product or Sales Code/Purchase Code by the Sku field.


### Updating


All import tasks support updating records except the **Upload Purchases**task as their is no suitable way to support this. Please note, that when updating Invoice information (on **Upload Invoices** and **Upload Quotes**) that existing item information is deleted and replaced with the data you import.



For more information on the Kashflow API, please visit [here](https://www.kashflow.com/developers/soap-api/).

