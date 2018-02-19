---
slug: importing-projects-into-sage-50-uk
redirect_from: "/article/414-importing-projects-into-sage-50-uk"
title: Importing Projects into Sage 50 UK
---
This task will import projects to Sage 50 that is supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.  

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Project XML](sage-50-uk-project-xml):  


```xml
<?xml version="1.0" encoding="utf-8">
<Company>
  <Projects>
    <Project>
      <Id>1</Id>
      <Reference>ZYNK</Reference>
      <Name>ZYNK PROJECT</Name>
      <Description>ZYNK PROJECT - INTEGRATION</Description>
      <StartDate>2014-01-13T00:00:00</StartDate>
      <EndDate>2014-01-14T00:00:00</EndDate>
      <Status>ACTIVE</Status>
      <AccountReference>CUST0001</AccountReference>
      <SecondReference>SECONDREF</SecondReference>
      <ProjectAddress>
        <ContactName>Mr Chris Hotchkiss</ContactName>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne &amp;amp; Wear</County>
        <Postcode>NE2 3AE</Postcode>
        <Telephone>0845 123 2920</Telephone>
        <Fax>0845 123 2921</Fax>
        <Email>support@zynk.com</Email>
        <Country>GB</Country>
      </ProjectAddress>
      <QuotedPrice>6778</QuotedPrice>
      <Analysis1>ANALYSIS1</Analysis1>
      <Analysis2>ANALYSIS2</Analysis2>
      <Analysis3>ANALYSIS3</Analysis3>
    </Project>
  </Projects>
</Company>
```
