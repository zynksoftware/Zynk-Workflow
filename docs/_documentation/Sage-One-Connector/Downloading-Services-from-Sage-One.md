---
slug: downloading-services-from-sage-one
redirect_from: "/article/857-download-services"
title: Downloading Services from Sage One
---
This task will download Services from your instance of Sage One.

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
A sample output file is shown below. See [Sage One Service XML](sage-one-service-xml) for full documentation of the XML format.
```xml
<?xml version="1.0"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <services>
    <service>
      <legacy_id>1757583</legacy_id>
      <id>c7e44932271a11e691e20a5d7cf84c3e</id>
      <displayed_as>Bringing It All Back Home</displayed_as>
      <path>/services/c7e44932271a11e691e20a5d7cf84c3e</path>
      <created_at>2016-05-31T10:31:05Z</created_at>
      <updated_at>2016-05-31T10:39:10Z</updated_at>
      <deleted_at xsi:nil="true" />
      <description>Bringing It All Back Home</description>
      <notes>Bob Dylan's first electric album includes tracks It's All Over Now Baby Blue, Maggie's Farm and Subterranean Homesick Blues.</notes>
      <sales_ledger_account>
        <legacy_id>9081395</legacy_id>
        <id>8a970c12271611e691e20a5d7cf84c3e</id>
        <displayed_as>Sales Type B (4001)</displayed_as>
        <path>/ledger_accounts/8a970c12271611e691e20a5d7cf84c3e</path>
      </sales_ledger_account>
      <sales_tax_rate>
        <legacy_id>1</legacy_id>
        <id>GB_STANDARD</id>
        <displayed_as>Standard 20.00%</displayed_as>
        <path>/tax_rates/GB_STANDARD</path>
      </sales_tax_rate>
      <active>true</active>
      <sales_rates>
        <sales_rate>
          <legacy_id>4406868</legacy_id>
          <id>c7e4eff3271a11e691e20a5d7cf84c3e</id>
          <displayed_as>Rate</displayed_as>
          <rate>16</rate>
          <rate_includes_tax>false</rate_includes_tax>
          <rate_name>Rate</rate_name>
          <service_rate_type>
            <legacy_id>1052120</legacy_id>
            <id>7a34c355175011e691e20a5d7cf84c3e</id>
            <displayed_as>Rate</displayed_as>
            <path>/service_rate_types/7a34c355175011e691e20a5d7cf84c3e</path>
          </service_rate_type>
        </sales_rate>
      </sales_rates>
    </service>
  </services>
</sage_one_company>
```