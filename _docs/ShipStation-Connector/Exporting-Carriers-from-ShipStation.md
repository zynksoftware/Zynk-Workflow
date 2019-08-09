---
slug: exporting-carriers-from-shipstation
title: Exporting Carriers from ShipStation
---
This task will export a list of all carriers you have configured in ShipStation, in XML format.

## Settings
### ShipStation Connection
_Required_  
Select a ShipStation connection to use. See the [Connecting to ShipStation](connecting-to-shipstation) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the carriers to. The data will be exported in XML format, as shown below.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Carriers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Carrier>
    <Name>DHL Express UK</Name>
    <Code>dhl_express_uk</Code>
    <AccountNumber>12345678</AccountNumber>
    <RequiresFundedAccount>false</RequiresFundedAccount>
    <Balance>0.0</Balance>
    <ShippingProviderId>340877</ShippingProviderId>
    <Primary>true</Primary>
  </Carrier>
  <Carrier>
    <Name>DPD</Name>
    <Code>dpd</Code>
    <AccountNumber>12345678</AccountNumber>
    <RequiresFundedAccount>false</RequiresFundedAccount>
    <Balance>0.0</Balance>
    <Nickname>DPD</Nickname>
    <ShippingProviderId>340880</ShippingProviderId>
    <Primary>true</Primary>
  </Carrier>
</Carriers>
```