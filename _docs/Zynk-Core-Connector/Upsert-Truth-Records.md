---
slug: upsert-truth-records
redirect_from: "/article/383-upsert-truth-records"
title: Upsert Truth Records
---
This task will insert or update records in the truth table (as seen on the 'Data' tab) to an XML file. The truth table maps the ID numbers of records imported using Zynk between two systems. The 'Internal ID' is usually the ID of the record in Sage, and the external ID is the ID of the matching record from an external system such as a website or e-commerce platform. Note: the truth table is automatically populated when importing data into Sage, so this task is only required when not importing data into Sage.

For more detailed information on the truth table please visit the [Truth Database](truth-database) page.

## Settings
### External ID
_Required_  
The XPath query to use to access the external ID of each record. This should be relative to the query used in the 'XPath' setting.

### Internal ID
_Required_  
The XPath query to use to access the internal ID of each record. This should be relative to the query used in the 'XPath' setting.

### XPath
_Required_  
The XPath query to use to access each record in the input file.

### Input File
_Required_  
The XML file containing the data to insert or update in the truth table. The data can be stored in any format, the task will read the internal and external IDs based on the XPath settings.

### Record Type
_Required_  
The type of records to import into the truth table. Defaults to 'Contacts'.

### Update ID
_Required_  
The ID to update. Select either 'Internal' or 'External'. Defaults to 'Internal'.

### Workflow ID
_Optional_  
The ID of the workflow to export truth records for. You can view the ID of a workflow from the 'Properties' tab, under 'Workflow Settings'. If left blank, the task will output truth records for the workflow it is on.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, showing a customer:

```xml
<?xml version="1.0"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <Customer>
        <id>1</id>
        <firstname>John</firstname>
        <lastname>Smith</lastname>
        <account_ref>JOHN001</account_ref>
        <email>john.smith@example.com</email>
        <default_billing_address>
            <company>Zynk Software</company>
            <street1>Nelson House</street1>
            <street2>Fleming Business Centre</street2>
            <city>Jesmond</city>
            <region>Tyne and Wear</region>
            <country_id>GB</country_id>
            <postcode>NE2 3AE</postcode>
        </default_billing_address>
    </Customer>
</Customers>
```

Based on this file, the tasks settings would be set as follows:

- XPath - `Customers/Customer`
- Internal Id - `account_ref`
- External Id - `id`
- Record Type - `Customers`

