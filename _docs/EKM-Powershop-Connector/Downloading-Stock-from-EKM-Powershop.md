---
slug: downloading-stock-from-ekm-powershop
redirect_from: "/article/219-downloading-stock-from-ekm-powershop"
title: Downloading Stock from EKM Powershop
---
This task will download details of all stock to an XML file.

## Settings
### Connection
_Required_  
The EKM Powershop connection to use.  See the [Connecting to EKM Powershop](connecting-to-ekm-powershop) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to export the data to.

### Product Code
_Required_  
The product code of the product to download stock data for.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <soap:Body>
        <GetProductStockResponse xmlns="http://publicapi.ekmpowershop.com/">
            <GetProductStockResult>
                <Status>Success</Status>
                <Errors />
                <Date>2012-08-02T11:12:51.1822943+01:00</Date>
                <ProductStock>5</ProductStock>
            </GetProductStockResult>
        </GetProductStockResponse>
    </soap:Body>
</soap:Envelope>
```
