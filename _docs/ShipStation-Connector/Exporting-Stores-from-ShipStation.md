---
slug: exporting-stores-from-shipstation
title: Exporting Stores from ShipStation
---
This task will export a list of all stores you have configured in ShipStation, in XML format.

## Settings
### ShipStation Connection
_Required_  
Select a ShipStation connection to use. See the [Connecting to ShipStation](connecting-to-shipstation) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the stores to. The data will be exported in XML format, as shown below.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Stores xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Store>
    <Id>227725</Id>
    <StoreName>Manual Orders</StoreName>
    <MarketplaceId>0</MarketplaceId>
    <MarketplaceName>ShipStation</MarketplaceName>
    <Active>true</Active>
    <CompanyName>Zynk Software Limited</CompanyName>
    <RefreshDate>2019-07-12T06:25:44.797</RefreshDate>
    <LastRefreshAttempt>2019-07-12T06:25:45.53</LastRefreshAttempt>
    <CreateDate>2017-12-15T07:14:36.887</CreateDate>
    <ModifyDate>2017-12-15T07:14:36.887</ModifyDate>
    <AutoRefresh>false</AutoRefresh>
  </Store>
</Stores>
```