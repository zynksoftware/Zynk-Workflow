---
slug: sage-50-us-xml
title: Sage 50 US XML
---
**NOTE - The Sage 50 US Connector is currently in BETA - if you are interested in getting early access please contact us at support@zynk.com**  

 * [Sage 50 US Customer XML](sage-50-us-customer-xml)
 * [Sage 50 US Sales Order XML](sage-50-us-sales-order-xml)
 * [Sage 50 US Inventory XML](sage-50-us-inventory-xml)

To integrate with Sage 50 US using Zynk you will need to import and export data using XML. While each task uses its own specific format there are some nodes they have in common, as described below.   

## External Id
The ExternalId field is used when importing data, and should be the unique id of the record from the third party system you are importing from. For example if you are downloading orders from a website this should be the id of the order from the websites database. This field is used to track which records have been imported by Zynk to prevent duplicate data entry. 

## Key
The Key field will contain the unique id of the record from the Sage 50 US database. This can be used to ensure the third party system does not reprocess records, or can be used to identify records if the id changes e.g. you change the id of an inventory record. 

## Import Messages
The output files for import tasks can contain messages to inform of the result, success files can contain Warning messages, while fail files can contain Error and Validation messages. If you are processing the results of an import you should check the ImportMessages collection in the XML.  

The following is an example of the above fields within a customer record.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfCustomer>
  <Customer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ExternalId>1234</ExternalId>
    <Key>9f5a1e3f-c61e-41ab-ac1d-90060c79aaac</Key>
    <ImportMessages>
      <ImportMessage>
        <Type>Error</Type>
        <Field>Custom Field: Sales Contact</Field>
        <Message>Record not found</Message>
      </ImportMessage>
      <ImportMessage>
        <Type>Error</Type>
        <Field>SalesRepresentativeReference</Field>
        <Message>No employee with ID 'DGROSS11' was found.</Message>
      </ImportMessage>
    </ImportMessages>
  </Customer>
</ArrayOfCustomer>
```