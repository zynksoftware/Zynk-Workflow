---
slug: importing-contacts-to-brightpearl
redirect_from: "/article/177-uploading-contacts-to-brightpearl"
title: Importing Contacts to Brightpearl
---


This task will create new contacts in Brightpearl from an XML file. Please note that the task does not support updating existing contacts.


## Settings

### Connection 
_Required_
The Brightpearl connection to use. See [Connecting to Brightpearl](connecting-to-brightpearl)

### Fail File
_Required_
The file to save failed records to.

### Input File
_Required_
The file containing records to import.

### Success File
_Required_
The file to save successful records to.

### Prevent Reprocessing
_Required_
Set to true to prevent the same records being processed more than once, based on the value of the `externalId` element in the XML.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


Sample input file containing the minimum information required to create a contact:


```xml
    <?xml version="1.0"?>
    <ArrayOfContact>
      <Contact>
        <externalId>734</externalId>
        <salutation>Mr.</salutation>
        <firstName>John</firstName>
        <lastName>Smith</lastName>
        <postalAddresses>
          <defaultAddress>
            <addressId>106</addressId>
          </defaultAddress>
          <billingAddress>
            <addressId>106</addressId>
          </billingAddress>
          <deliveryAddress>
            <addressId>106</addressId>
          </deliveryAddress>
        </postalAddresses>
      </Contact>
    </ArrayOfContact>
```