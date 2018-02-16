---
slug: updating-orders-in-magento
redirect_from: "/article/266-updating-orders-in-magento"
title: Updating Orders in Magento
---
This task will update the status of orders in Magento, and optionally add comments and notify the customer by email.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The XML file to save failed order updates to. The data is stored in the same format as the input file.

### Input File
_Required_  
The XML file containing the orders to be updated in Magento.

### Success File
_Required_  
The XML file to save successful order updates to. The data is stored in the same format as the input file.

### Default Comment
_Optional_  
The comment to leave against the order status update. This setting is overridden if a comment is provided for an order in the input file.

### Notify Customer
_Required_  
Set to true to notify the customer of the update by email, set to false to not notify the customer.

### Notify Stage
_Required_  
Sets the status the order should be changed to, and be shown in the notification (e.g. pending, processed, complete).

### Prevent Reprocessing
_Required_  
Set to true to prevent the same record being processed more than once.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file, which will update the status of order 100025838, and add a comment in the order history:
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfOrderInfo>
  <OrderInfo>
    <increment_id>100025838</increment_id>
    <comment>Tracking number: 852308</comment>
  </OrderInfo>
</ArrayOfOrderInfo>
```

Sample XSLT file to use to transform orders exported from Sage in the Zynk XML Sales Orders format, to the Magento order update format. This is also available in the [Auto Mapper](auto-mapper).
```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

  <xsl:output method="xml" indent="yes"/>

  <xsl:template match="Company">
    <ArrayOfOrderInfo>
      <xsl:for-each select="SalesOrders/SalesOrder">
        <xsl:call-template name="OrderInfo" />
      </xsl:for-each>
    </ArrayOfOrderInfo>
  </xsl:template>

  <xsl:template name="OrderInfo">
    <OrderInfo>
      <increment_id><xsl:value-of select="CustomerOrderNumber"/></increment_id>
    </OrderInfo>
  </xsl:template>

</xsl:stylesheet>
```