---
slug: update-orders-in-manta
title: Update Orders in Manta
---

This task will update orders within Manta using provided XML.

## Settings
### Connection Settings
#### Manta Connection
_Required_  
The connection to Manta to use. See the [Connecting to Manta](connecting-to-manta) article if you require further information on how to create/manage the connection to Manta.

### File Settings
#### Fail File
_Required_  
The file containing the orders that failed to be uploaded to Manta.

#### Input File
_Required_  
The file containing the orders to update in Manta.

#### Success File
_Required_  
The file containing the orders that were successfully uploaded to Manta.

### Import Settings
#### Prevent Reprocessing
_Required_   
Set to 'True' to prevent the same record being processed more than once. In order for this setting to work, an `<ExternalId>` element must be provided within the XML document.

### Zynk Settings
See [Common Task Settings](common-task-settings).

### Examples
Sample input file for updating Manta orders.

```xml
<?xml version="1.0" encoding="utf-8"?>
<OrderUpdates>
    <OrderUpdate>
        <OrderId>166941</OrderId>
        <OrderIdBrand>PO-549862</OrderIdBrand>
        <CompanyBrandCode>ZYNK001</CompanyBrandCode>
        <Process>
            <ProcessStatus>SUCCESS</ProcessStatus>
        </Process>
    </OrderUpdate>
</OrderUpdates>
```