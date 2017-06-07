---
slug: importing-employee-payments-into-sage-50-payroll
redirect_from: "/article/670-importing-payments-into-sage-payroll"
title: Importing Employee Payments Into Sage 50 Payroll
---
This task will import Employee Payments into Sage 50 Payroll, updating existing Employee Payments and creating new ones where they don't already exist. See the [Sage 50 Payroll Employee Payments XML](sage-50-payroll-employee-payments-xml) page for more information.

This task requires a Connection to Sage 50 Payroll, for more information on setting up and managing Sage 50 Payroll, see [Connecting to Sage 50 Payroll](connecting-to-sage-50-payroll).

## Connection Settings  
### Sage 50 Payroll Connection
_Required_  
The Sage 50 Payroll connection to import Employee Payments into. See the [Connecting to Sage 50 Payroll](connecting-to-sage-50-payroll) page if you require more information on how to create/manage Zynk Connections to Sage 50 Payroll.  
Defaulted to the connection marked as the default for Sage 50 Payroll. For more information on managing default connections within Zynk, see the [Connection Manager](connection-manager) page.

## File Settings
### Fail File
_Required_  
An absolute or relative file path on the local computer or network to save any Employee Payments which failed to import into Sage 50 Payroll to. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to `sage_50_payroll_import_employee_payments_fail.xml` in the current working directory.  

### Input File
_Required_  
The absolute or relative file path to the XML file containing the Sage 50 Payroll Employee Payments to import. This can also be inline XML, e.g. by generating the data using a razor script or by providing a URI to a script generating the data and specifying 'Read contents of file'. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to use the `Output from the previous task`.

### Success File
_Required_  
An absolute or relative file path on the local computer or network to save all Employee Payments which were successfully imported into Sage 50 Payroll to. See the [Zynk Objects](zynk-objects) page if you require more information on how the Zynk Object file value works.  
Defaulted to `sage_50_payroll_import_employee_payments_success.xml` in the current working directory.

## Zynk Settings
See [Common Task Settings](common-task-settings).

## Articles and Sample Files
For full documentation and samples, see [Sage 50 Payroll Employee Payments XML](sage-50-payroll-employee-payments-xml).

## Task Links
- [Introduction to the Sage 50 Payroll Connector](sage-50-payroll)
- [Connecting to Sage 50 Payroll](connecting-to-sage-50-payroll)
- [Importing Employee Absences Into Sage 50 Payroll](importing-employee-absences-into-sage-50-payroll)
- [Importing Employee Deductions Into Sage 50 Payroll](importing-employee-deductions-into-sage-50-payroll)
- [Importing Employee Payments Into Sage 50 Payroll](importing-employee-payments-into-sage-50-payroll)

## XML Links
- [Sage-50-Payroll-XML](sage-50-payroll-xml)
- [Sage 50 Payroll Employee Absences XML](sage-50-payroll-employee-absences-xml)
- [Sage 50 Payroll Employee Deductions XML](sage-50-payroll-employee-deductions-xml)
- [Sage 50 Payroll Employee Payments XML](sage-50-payroll-employee-payments-xml)