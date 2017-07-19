---
slug: exporting-purchase-orders-from-magnetichq
title: Exporting Purchase Orders from Magnetic HQ
---
This task will export purchase orders from Magnetic HQ and store them in an XML file.

## Settings
### Connection
_Required_  
The MagneticHQ connection to use. See the ![Connecting to MagentoHQ](connecting-to-magnetichq) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set this option to true to export all purchase orders, or set to false to download only new or modified purchase orders since this task last ran. Defaults to False.

### Status
_Required_
Select a status to filter the purchase orders on. Options are; 'Draft', 'Cancelled', 'Checked', 'Invoiced', Part_invoiced', 'Issued'.

### Output File
_Required_  
The name of the XML file to export the data to (e.g. purchase_orders.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).