---
slug: creating-chart-of-accounts-in-xero
redirect_from: "/article/908-creating-chart-of-accounts-in-xero"
title: Creating Chart of Accounts in Xero
---


This task will create the chart of accounts in Xero using an XML file. This task can only be used on new Xero companies, where the chart of accounts hasn't been set up yet.


## Settings 

### Connection 
_Required_
The connection entry you'd like to use to run the task.

### Input File
_Required_
The file containing the chart of accounts to upload to Xero.

### Output File
_Required_
The file to save the create setup summary to.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file containing showing some accounts:


```xml
<?xml version="1.0" encoding="utf-8"?>
<Setup xmlns:ms="urn:schemas-microsoft-com:xslt" xmlns:zynk="http://www.zynk.com">
  <Accounts>
    <Account>
      <Code>0010</Code>
      <Name>Freehold Property</Name>
      <Type>Fixed</Type>
      <TaxType>NONE</TaxType>
    </Account>
    <Account>
      <Code>0011</Code>
      <Name>Leasehold Property</Name>
      <Type>Fixed</Type>
      <TaxType>NONE</TaxType>
    </Account>
    <Account>
      <Code>0020</Code>
      <Name>Plant and Machinery</Name>
      <Type>Fixed</Type>
      <TaxType>NONE</TaxType>
    </Account>
  </Accounts>
</Setup>
```
