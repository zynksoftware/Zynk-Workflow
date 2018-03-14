---
slug: exporting-country-codes-from-sage-200-online
redirect_from: "/article/exporting-country-codes-from-sage-200-online"
title: Exporting Country Codes From Sage 200 Online
---

This task will export country codes from Sage 200 Online in [Sage 200 Online Country Code XML](sage-200-online-country-code-xml) format to a file.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified or All Records' setting is set to 'Modified', only records modified after this date will be downloaded. The date will update automatically each time the task runs, to ensure that only records modified since the task last ran will be downloaded.

### Export Settings > Export Modified or All Records
_Required_  
Used to choose which records should be included in the download. The available options are:

* __All__ - All records will be downloaded, regardless of whether or not they have been updated since the task last ran.
* __Modified__ - Only records created or updated since the task last ran will be downloaded.

### Filter
_Optional_  
Allows a filter to be set to limit the data that is returned. For example, you can return currencies where the name field equals 'Euro' using: `name eq 'Euro'`

Sage 200 Online uses the OData protocol, and expects the filter to be specified in this format. You can find more information on OData filters [here](http://www.odata.org/getting-started/basic-tutorial/#queryData).

### Output File
_Required_  
The name of the file to save the downloaded records to.

### Page Size
_Required_  
The number of records to include in each page of results downloaded from Sage. Increasing this value will speed up the download, but will use more memory. Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<CountryCodes xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <CountryCode>
  <CountryCode>
    <id>2</id>
    <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
    <name>Austria</name>
    <code>AT</code>
    <eu_member>true</eu_member>
  </CountryCode>
  <CountryCode>
    <id>3</id>
    <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
    <name>Belgium</name>
    <code>BE</code>
    <eu_member>true</eu_member>
  </CountryCode>
</CountryCodes>
```
