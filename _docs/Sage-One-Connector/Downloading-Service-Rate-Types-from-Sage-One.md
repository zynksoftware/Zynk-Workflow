---
slug: downloading-service-rate-types-from-sage-one
redirect_from: "/article/857-download-services"
title: Downloading Services from Sage One
---
This task will download services rate types from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set to true to export all records from Sage One, or false to only export those updated since the date specified in the 'Export From' setting.

### Export From
_Required_  
The date to export new/modified records from. This setting only takes effect when 'Export All' is set to false. The date will update automatically each time the task runs.

### Output File
_Required_  
The file to save the downloaded records to.

### Items Per Page
_Required_  
The number records to fetch per request to Sage One. Increasing this value will reduce the number of requests needed to export the records, which may reduce the time taken.

### Search
_Optional_  
Enter a search to filter the records returned.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <service_rate_types>
    <service_rate_type>
      <legacy_id>1052120</legacy_id>
      <id>7a34c355175011e691e20a5d7cf84c3e</id>
      <displayed_as>Rate</displayed_as>
      <path>/service_rate_types/7a34c355175011e691e20a5d7cf84c3e</path>
      <created_at>2015-06-22T08:33:54Z</created_at>
      <updated_at>2015-06-22T08:33:54Z</updated_at>
      <name>Rate</name>
      <active>true</active>
    </service_rate_type>
  </service_rate_types>
</sage_one_company>
```