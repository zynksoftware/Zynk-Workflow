---
slug: uploading-subscribers-to-campaign-monitor
redirect_from: "/article/454-uploading-subscribers-to-campaign-monitor"
title: Uploading Subscribers to Campaign Monitor
---
This task will take an XML file in the format specified below and update or add to your specified list in Campaign Monitor.

## Settings
### Connection
_Required_  
The Campaign Monitor Connection to download lists from.  See the [Connecting to Campaign Monitor](connecting-to-campaign-monitor) article if you require more information on how to create/manage connections.

### Input File
_Required_  
The file containing records you wish to upload to your list in Campaign Monitor.

### Response File
_Required_  
A response from Campaign Monitor will be written to this file.

### List API Key
_Required_  
The API Key of the list you wish to integrate with, you can find this if you open the list and click 'change name/type'.

### Resubscribe
_Required_  
If set to True will allow you to re-add subscribers to lists, regardless of unsubscribe status or suppression list.  Should be used with caution and only where suitable.  Defaults to False.

### Zynk Settings
See [Common Task Settings](common-task-settings)

### Examples
Sample input file:

```xml
<?xml version="1.0"?>
<ArrayOfSubscriberDetail>
  <SubscriberDetail>
    <EmailAddress>test@zynk.com</EmailAddress>
    <Date>2016-01-12T14:37:00</Date>
    <State>Active</State>
    <CustomFields>
      <SubscriberCustomField>
        <Key>DOB</Key>
        <Value>1994-08-01</Value>
      </SubscriberCustomField>
      <SubscriberCustomField>
        <Key>Connector</Key>
        <Value>Sage 200</Value>
      </SubscriberCustomField>
    </CustomFields>
  </SubscriberDetail>
</ArrayOfSubscriberDetail>
```