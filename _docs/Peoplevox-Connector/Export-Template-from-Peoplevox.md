---
slug: export-template-from-peoplevox
title: Export Template from Peoplevox
---

This task allows you to export any template configured on your Peoplevox instance, and control the format of the output XML file.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to `1`.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_template.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Template
_Required_  
Specify the template name to export from. Defaults to `Carriers`.

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to `10`.

## XML Settings
### Export As Elements
_Required_  
Setting to True will output fields as elements in the XML file, setting to False output the fields as attributes. Defaults to `True`.

### Root
_Required_  
Used to specify the root element of the output XML file. Defaults to `Carriers`.

### Row
_Required_  
Used to specify the name of the element for each record in the output file. Defaults to `Carrier`.

## Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example output file using the default task settings referencing the Carriers template.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Carriers>
  <Carrier>
    <Name>DHL</Name>
    <Reference_x0020_2>D0001</Reference_x0020_2>
  </Carrier>
  <Carrier>
    <Name>FedEx</Name>
    <Reference_x0020_2> F0002</Reference_x0020_2>
  </Carrier>
  <Carrier>
    <Name>Joe Harrison</Name>
    <Reference_x0020_2 />
  </Carrier>
</Carriers>
```
