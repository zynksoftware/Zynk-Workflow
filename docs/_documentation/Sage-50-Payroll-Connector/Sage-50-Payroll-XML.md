---
slug: sage-50-payroll-xml
redirect_from: ""
title: Sage 50 Payroll XML
---
To integrate with [Sage 50 Payroll](sage-50-payroll) using Zynk you will need to import and export data using XML. We have created a common XML schema to allow you to easily integrate your systems with Sage 50 Payroll.

## Understanding the XML Documentation
The Sage 50 Payroll documentation consists of XML samples and field descriptions. Each field description will state whether the field is _Required_ or _Optional_ and will also provide the field name as it appears in Sage 50 Payroll in **bold**.

## Record Operations
The Sage 50 Payroll import tasks allow you to specify a `RecordOperation` on each record being processed. This allows you to stipulate if records should:
- only be inserted where they don't exist (`Insert`) and fail if they do already exist.
- only be updated if they already exist (`Update`) and fail if they don't already exist.
- update if the record already exists, otherwise insert a new record (`Upsert`).  

You will find examples of each type of `RecordOperation` within the Samples section of each XML documentation page.

We recommend that you read the [Zynk XML Overview](zynk-xml-overview) before continuing as this contains some generic information on the XML object model, alternatively, choose the task relevant to your integration:

 * [Sage 50 Payroll Employee Absences XML](sage-50-payroll-employee-absences-xml)
 * [Sage 50 Payroll Employee Deductions XML](sage-50-payroll-employee-deductions-xml)
 * [Sage 50 Payroll Employee Payments XML](sage-50-payroll-employee-payments-xml)
 
## Task Links
- [Introduction to the Sage 50 Payroll Connector](sage-50-payroll))
- [Connecting to Sage 50 Payroll](connecting-to-sage-50-payroll)
- [Importing Employee Absences Into Sage 50 Payroll](importing-employee-absences-into-sage-50-payroll)
- [Importing Employee Deductions Into Sage 50 Payroll](importing-employee-deductions-into-sage-50-payroll)
- [Importing Employee Payments Into Sage 50 Payroll](importing-employee-payments-into-sage-50-payroll)

## XML Links
- [Sage-50-Payroll-XML](sage-50-payroll-xml)
- [Sage 50 Payroll Employee Absences XML](sage-50-payroll-employee-absences-xml)
- [Sage 50 Payroll Employee Deductions XML](sage-50-payroll-employee-deductions-xml)
- [Sage 50 Payroll Employee Payments XML](sage-50-payroll-employee-payments-xml)