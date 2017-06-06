---
slug: downloading-countries-from-sage-one
redirect_from: "/article/850-download-countries"
title: Downloading Countries from Sage One
---
This task will download Countries from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Download Type
_Required_  
Select All, New or Modified.

### Record Id
_Optional_  
Optionally download a specific record by specifying the Sage One id.

### Output File
_Required_  
The file to save the downloaded records to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below.
```xml
<?xml version="1.0"?>
<ArrayOfCountry xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Country>
    <SageOneRecordId>218</SageOneRecordId>
    <Code>GB</Code>
    <Name>United Kingdom</Name>
  </Country>
</ArrayOfCountry>
```