---
slug: uploading-services-to-sage-business-cloud
title: Uploading Services to Sage Business Cloud
---
The Import Services task will create new and update existing service items in Sage Business Cloud. The service data must be provided in the [Sage Business Cloud Service XML](sage-business-cloud-service-xml) format.

## Settings
### Sage Business Cloud Connection
_Required_  
The connection to Sage Business Cloud to use. See [Connecting to Sage Business Cloud](connecting-to-sage-business-cloud) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once. This will only work where an `external_id` is provided for a record in the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample input file is shown below. See [Sage Business Cloud Service XML](sage-business-cloud-service-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <services>
    <service>
      <item_code>LABOUR</item_code>
      <description>Labour (Hourly)</description>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
      </sales_ledger_account>
    </service>
  </services>
</sage_one_company>
```