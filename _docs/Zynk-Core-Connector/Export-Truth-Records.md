---
slug: export-truth-records
redirect_from: "/article/372-export-truth-records"
title: Export Truth Records
---
This task will export records from the truth table (as seen on the 'Data' tab) to an XML file.

The truth table is used by Zynk to map the ID numbers of records imported using Zynk between two systems. The 'Internal ID' is usually the ID of the record in Sage, and the external ID is the ID of the matching record from an external system such as a website or e-commerce platform.

For more detailed information on the truth table please visit the [Truth Database](truth-database) page.

## Settings
### Export Modified, New or All
_Required_  
Choose which records should be exported. The available options are: 	  

 * All - Will export all records.
 * New - Will only export records where the created date is greater than the task's last ran date.
 * Modified - Will only export records where the modified date is greater than the task's last ran date.

### Output File
_Required_  
The XML file to output the truth records to.

### Record Type
_Required_  
The type of records to export from the truth table. Defaults to 'Contacts'.

### Workflow ID
_Optional_  
The ID of the workflow to export truth records for. You can view the ID of a workflow from the 'Properties' tab, under 'Workflow Settings'. If left blank, the task will output truth records for the workflow it is on.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<TruthRecords>
  <TruthRecord Type="Zynk.Connect.Objects.SalesOrder" InternalId="0000000156" ExternalId="5230" />
  <TruthRecord Type="Zynk.Connect.Objects.SalesOrder" InternalId="0000000157" ExternalId="5231" />
  <TruthRecord Type="Zynk.Connect.Objects.SalesOrder" InternalId="0000000158" ExternalId="5232" />
  <TruthRecord Type="Zynk.Connect.Objects.SalesOrder" InternalId="0000000160" ExternalId="5233" />
</TruthRecords>
```