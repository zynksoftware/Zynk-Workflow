---
slug: importing-contacts-into-act
redirect_from: "/article/140-importing-contacts-into-act"
title: Importing Contacts into ACT!
---
This task will import Contacts into ACT!, updating existing Contacts and creating new ones where they don't already exist. See the [ACT! Contact XML](act-contact-xml) page for more information.

This task requires a Connection to ACT!, for more information on setting up and managing ACT! connections, see [Connecting to ACT!](connecting-to-act).

## Connection Settings  
### ACT! Connection
_Required_  
The ACT! connection to import Contacts into. See the [Connecting to ACT!](connecting-to-act) page if you require more information on how to create/manage Zynk Connections to ACT!.  
Defaulted to the connection marked as the default for ACT!. For more information on managing default connections within Zynk, see the [Connection Manager](connection-manager) page.

## File Settings
### Fail File
_Required_  
An absolute or relative file path on the local computer or network to save any Contacts which failed to import into ACT! to. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to `act_import_contacts_fail.xml` in the current working directory.  

### Input File
_Required_  
The absolute or relative file path to the XML file containing the ACT! Contacts to import. This can also be inline XML, e.g. by generating the data using a razor script or by providing a URI to a script generating the data and specifying 'Read contents of file'. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to use the `Output from the previous task`.

### Success File
_Required_  
An absolute or relative file path on the local computer or network to save all Contacts which were successfully imported into ACT! to. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to `act_import_contacts_success.xml` in the current working directory.

## Import Settings
### Create Follow Up
_Required_  
Set to `true` to create a To Do follow up against every new ACT! Contact. The created Activity in ACT! will have the name 'Follow-up' and the details will read 'Follow-up newly created contact.'  
Defaulted to `false`.

### Group Name
_Optional_  
Provide a group name to associate every successfully processed ACT! Contact with. The group should already be set up in ACT! (Groups that don't exist will not be automatically created).  
Defaulted to `empty`, processed ACT! Contacts will not be associated with a Group.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Articles and Sample Files
For full documentation and samples, see [ACT! Contact XML](act-contact-xml).

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