---
slug: exporting-couriers-from-sage-50-uk
redirect_from: "/article/901-exporting-couriers-from-sage-50-uk"
title: Exporting Couriers from Sage 50 UK
---
This task will export courier information from Sage 50 in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Couriers>
    <Courier>
      <UniqueId>1</UniqueId>
      <Number>1</Number>
      <Name>DHL</Name>
      <Website>dhl.com</Website>
      <TrackingUrl>dhl.com/track</TrackingUrl>
    </Courier>
  </Couriers>
</Company>
```