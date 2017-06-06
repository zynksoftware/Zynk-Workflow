---
slug: importing-currencies-into-sage-200
redirect_from: "/article/675-importing-currencies-into-sage-200"
title: Importing Currencies into Sage 200
---
This task will import currencies in [Sage 200 XML](sage-200-xml) format into Sage 200. If the currency already exists (based on finding a matching currency code), it will be updated, otherwise a new currency will be created.

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Input File
_Required_  
The source file for importing in Zynk XML format.

### Fail File
_Required_  
The name of the file to store failed currencies in Zynk XML format.

### Success File
_Required_  
The name of the file to store the successfully imported currencies in Zynk XML format.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file for updating or updating a currency is shown below. See our [Sage 200 XML](sage-200-xml) for more details on the Zynk XML Currency format for Sage 200.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company>
  <Currencies>
    <Currency>
      <Code>EUR</Code>
      <Name>Euro</Name>
      <ExchangeRate>1.26</ExchangeRate>
    </Currency>
  </Currencies>
</Company>
```