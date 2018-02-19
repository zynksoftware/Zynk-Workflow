---
slug: importing-products-into-act
redirect_from: "/article/144-importing-products-into-act"
title: Importing Products into ACT!
---
This task will import Products into ACT!, updating existing Products and creating new ones where they don't already exist. See the [ACT! Product XML](act-product-xml) page for more information.

This task requires a Connection to ACT!, for more information on setting up and managing ACT! connections, see [Connecting to ACT!](connecting-to-act).

## Connection Settings  
### ACT! Connection
_Required_  
The ACT! connection to import Products into. See the [Connecting to ACT!](connecting-to-act) page if you require more information on how to create/manage Zynk Connections to ACT!.  
Defaulted to the connection marked as the default for ACT!. For more information on managing default connections within Zynk, see the [Connection Manager](connection-manager) page.

## File Settings
### Fail File
_Required_  
An absolute or relative file path on the local computer or network to save any Products which failed to import into ACT! to. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to `act_import_products_fail.xml` in the current working directory.  

### Input File
_Required_  
The absolute or relative file path to the XML file containing the ACT! Products to import. This can also be inline XML, e.g. by generating the data using a razor script or by providing a URI to a script generating the data and specifying 'Read contents of file'. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to use the `Output from the previous task`.

### Success File
_Required_  
An absolute or relative file path on the local computer or network to save all Products which were successfully imported into ACT! to. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to `act_import_products_success.xml` in the current working directory.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Articles and Sample Files
For full documentation and samples, see [ACT! Product XML](act-product-xml).

## Links
- [Introduction to the ACT! Connector](act)
- [Connecting to ACT!](connecting-to-act)
- [Importing Companies into ACT!](importing-companies-into-act)
- [Exporting Companies from ACT!](exporting-companies-from-act)
- [Importing Contacts into ACT!](importing-contacts-into-act)
- [Exporting Contacts from ACT!](exporting-contacts-from-act)
- [Importing Opportunities into ACT!](importing-opportunities-into-act)
- [Exporting Opportunities from ACT!](exporting-opportunities-from-act)
- [Importing Products into ACT!](importing-products-into-act)
- [Exporting Products from ACT!](exporting-products-from-act)



This task will import product information from Connect XML format to ACT!



Each of the ACT! tasks uses an ACT! Connection, for more information on setting up and managing ACT! connections, see the page Connecting to ACT! here.


## Settings


| 	Setting | 	Required | 	Description |
| --- | --- | --- | --- | --- | --- | --- |
| 	Fail File | 	Required | 	The name of a file for failed imports to be sent to. |
| 	Input File | 	Required | 	The source file that you want to import in Connect XML format. |
| 	Success File | 	Required | 	The name of a file for successful imports to be sent to. |
| [Common Task Settings](common-task-settings) | 	Settings common across all tasks.. |


## Examples


There are currently no examples available for this task.

