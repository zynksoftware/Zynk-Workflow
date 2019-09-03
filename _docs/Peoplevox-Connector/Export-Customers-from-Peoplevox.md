---
slug: export-customers-from-peoplevox
title: Export Customers from Peoplevox
---

This task will export customer information from Peoplevox in XML format, for detailed information see [Peoplevox Customer XML](peoplevox-customer-xml).  The information is exported using the "Customers" integration template that can be ran through your Peoplevox web application.  You can add filters and search clauses to limit the data that is returned.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to 1.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_customers.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to 10.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example input file, for detailed information see [Peoplevox Customer XML](peoplevox-customer-xml).

```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <CustomerType>2</CustomerType>
    <Name>Zynk Software Ltd</Name>
    <Reference>joe.harrison@zynk.com</Reference>
    <FirstName>Joe</FirstName>
    <LastName>Harrison</LastName>
    <Phone>0191 303 7279</Phone>
    <Mobile>0773 862 6085</Mobile>
    <Email>joe.harrison@zynk.com</Email>
    <CreditStatus>false</CreditStatus>
    <Wholesaler>false</Wholesaler>
    <CustomerAddresses>
      <CustomerAddress>
        <CustomerReference>joe.harrison@zynk.com</CustomerReference>
        <AddressLine1>i6 Business Centre</AddressLine1>
        <AddressLine2>6 Charlotte Square</AddressLine2>
        <AddressCity>Newcastle upon-Tyne</AddressCity>
        <AddressRegion>Tyne and Wear</AddressRegion>
        <AddressPostcode>NE1 4XF</AddressPostcode>
        <AddressCountry />
        <AddressReference>NE1 4XF</AddressReference>
      </CustomerAddress>
    </CustomerAddresses>
  </Customer>
</Customers>
```