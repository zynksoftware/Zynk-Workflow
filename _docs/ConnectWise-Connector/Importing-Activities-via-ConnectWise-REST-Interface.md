---
slug: importing-activities-via-connectwise-rest-interface
title: Importing Activities via ConnectWise REST Interface
---
This task will import activities into ConnectWise from an XML file. See below for a sample input file. 

Activities are created/updated based on the following rules:
* If an `<id>` is specified, the task will update the company with this ID.
* If an `<externalId>` is specified, and a corresponding entry is found in Zynk's truth table, the task will update the company with this ID.
* If none of the above conditions are met, the task will create a new company.

When updating existing activities, only writeable fields specified in the input file will be updated. Any other fields will keep their existing values.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the file to output any activities that failed to import. The error messages will be included in the file.

### Input File
_Required_  
The name of the file containing the activities to upload to ConnectWise. A sample file is provided below.

### Success File
_Required_  
The name of the file to output any successfully imported activities to.

### Prevent Reprocessing
_Required_  
Set this option to 'True' to prevent the same activity being processed more than once by Zynk. An `<externalId>` must be provided in the input file for this to work.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Activities xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Activity>
    <id>79</id>
    <externalId>124314</externalId>
    <name>Test Activity</name>
    <company>
      <id>2</id>
      <identifier>YourCompany</identifier>
    </company>
    <contact>
      <id>84</id>
      <name>Marc Mosiman</name>
    </contact>
    <phoneNumber>76342155</phoneNumber>
    <email>marcm@arcadministration.com</email>
    <status>
      <id>1</id>
      <name>Open</name>
    </status>
    <dateStart>2018-08-15T00:00:00</dateStart>
    <dateEnd xsi:nil="true" />
    <assignTo>
      <id>176</id>
      <identifier>Admin2</identifier>
    </assignTo>
    <scheduleStatus>
      <id>2</id>
      <name>Firm</name>
    </scheduleStatus>
    <where>
      <id>1</id>
      <name>On-Site</name>
    </where>
    <notifyFlag>false</notifyFlag>
    <currency>
      <id>3</id>
      <name>Euro</name>
      <symbol>€</symbol>
      <isoCode>EUR</isoCode>
    </currency>
  </Activity>
</Activities>
```
