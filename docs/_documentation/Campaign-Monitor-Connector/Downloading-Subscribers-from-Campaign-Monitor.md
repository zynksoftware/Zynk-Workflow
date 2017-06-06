---
slug: downloading-subscribers-from-campaign-monitor
redirect_from: "/article/453-downloading-subscribers-from-campaign-monitor"
title: Downloading Subscribers from Campaign Monitor
---
This task will provide a list of subscribers from whichever list you specify from Campaign Monitor in an XML format.

### Settings
### Connection
_Required_  
The Campaign Monitor Connection to download lists from.  See the [Connecting to Campaign Monitor](connecting-to-campaign-monitor) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The file to save all downloaded records to, in XML format.

### List API Key
_Required_  
The API Key of the list you wish to integrate with, you can find this if you open the list and click 'change name/type'.

### Zynk Settings
See [Common Task Settings](common-task-settings)

### Examples
Sample output file:

```xml
<?xml version="1.0"?>
<ArrayOfSubscriberDetail>
  <SubscriberDetail>
    <EmailAddress>accounts@zynk.com</EmailAddress>
    <Date>2016-01-12T14:27:00</Date>
    <State>Active</State>
    <Name />
    <CustomFields>
      <SubscriberCustomField>
        <Key>[DOB]</Key>
        <Value>1994-08-01</Value>
        <Clear>false</Clear>
      </SubscriberCustomField>
      <SubscriberCustomField>
        <Key>[Connector]</Key>
        <Value>Sage 50</Value>
        <Clear>false</Clear>
      </SubscriberCustomField>
    </CustomFields>
    <ReadsEmailWith />
  </SubscriberDetail>
  <SubscriberDetail>
    <EmailAddress>sales@zynk.com</EmailAddress>
    <Date>2016-01-12T14:27:00</Date>
    <State>Active</State>
    <Name />
    <CustomFields>
      <SubscriberCustomField>
        <Key>[DOB]</Key>
        <Value>1979-08-05</Value>
        <Clear>false</Clear>
      </SubscriberCustomField>
      <SubscriberCustomField>
        <Key>[Connector]</Key>
        <Value>Sage 200</Value>
        <Clear>false</Clear>
      </SubscriberCustomField>
    </CustomFields>
    <ReadsEmailWith />
  </SubscriberDetail>
  <SubscriberDetail>
    <EmailAddress>support@zynk.com</EmailAddress>
    <Date>2016-01-12T14:27:00</Date>
    <State>Active</State>
    <Name />
    <CustomFields>
      <SubscriberCustomField>
        <Key>[DOB]</Key>
        <Value>1967-03-07</Value>
        <Clear>false</Clear>
      </SubscriberCustomField>
      <SubscriberCustomField>
        <Key>[Connector]</Key>
        <Value>Sage 50</Value>
        <Clear>false</Clear>
      </SubscriberCustomField>
    </CustomFields>
    <ReadsEmailWith />
  </SubscriberDetail>
</ArrayOfSubscriberDetail>
```