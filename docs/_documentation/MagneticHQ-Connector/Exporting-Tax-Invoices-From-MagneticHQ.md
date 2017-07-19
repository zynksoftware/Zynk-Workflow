---
slug: exporting-tax-invoices-from-magnetichq
title: Exporting Tax Invoices from Magnetic HQ
---
This task will export tax invoices from Magnetic HQ and store them in an XML file.

## Settings
### Connection
_Required_  
The MagneticHQ connection to use. See the ![Connecting to MagentoHQ](connecting-to-magnetichq) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set this option to true to export all customers, or set to false to download only new or modified customers since this task last ran. Defaults to False.

### Status
_Required_
Select a status to filter the purchase orders on. Options are; 'Draft', 'Cancelled', 'Issued', 'Credited', 'Part_Credited', 'Paid', 'Part_Paid'

### Output File
_Required_  
The name of the XML file to export the data to (e.g. tax_invoices.xml).

### Zynk Settings
See [Common Task Settings](common-task-settings).

