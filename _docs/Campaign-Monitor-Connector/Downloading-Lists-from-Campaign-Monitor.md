---
slug: downloading-lists-from-campaign-monitor
redirect_from: "/article/506-downloading-lists-from-campaign-monitor"
title: Downloading Lists from Campaign Monitor
---
This task will allow you to download a collection of your lists in Campaign Monitor in an XML format. You will need to specify your Campaign Monitor Client ID as part of the task.

## Settings
### Connection
_Required_  
The Campaign Monitor Connection to download lists from.  See the [Connecting to Campaign Monitor](connecting-to-campaign-monitor) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The file to save all downloaded records to, in XML format.

### Client ID
_Required_  
The Client ID of your account, this can be found if you go to Manage My Account underneath your account name and then go to Managing API Keys.

### Zynk Settings
See [Common Task Settings](common-task-settings)

### Examples
Sample output file:

```xml
<?xml version="1.0"?>
<ArrayOfBasicList>
  <BasicList>
    <ListID>aba81325b114110c445a798457755231</ListID>
    <Name>Test</Name>
  </BasicList>
  <BasicList>
    <ListID>1831b68524487831ae9c7b31f3d7d049</ListID>
    <Name>Test List</Name>
  </BasicList>
</ArrayOfBasicList>
```