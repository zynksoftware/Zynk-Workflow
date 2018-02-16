---
slug: excel-to-sage-integration
redirect_from: "/article/460-excel-to-sage-integration"
title: Excel to Sage Integration
---
This tutorial will step through how to perform a basic integration between an **Excel** document and **Sage**, all necessary files can be found within the download section of this site, there is also a workflow for your provision.

Note however, none of the documents includes any tax information. So if you were to use these as they are currently set up, the data will be imported in to Sage depending on how your package is currently configured to handle tax.

[Converting Excel to XML](converting-excel-to-xml)

This task will convert your Excel spreadsheet in to XML format.

 * **Include Headers**Set this to true if the task should export column headers in the XLS file
 * **Input File**Name of the Excel file you are looking to process.
 * **Worksheet Name**Name of the worksheet to query *e.g sheet1*
 * **Output File**The name of the XML file to create containing the XML representation of the Excel worksheet

[XSLT Transform](xslt-transform)

This task will transform the data outputted from the previous task in to the appropriate format.

 * **Input File**The name of the XML file created in the previous task by Zynk.
 * **Output File**The name of the XML file that will be transformed the XSLT file.
 * **Parameters**Contains any Parameters set in the XSLT file (none in this case).
 * **XSLT File**The name of the file used to transform the Input File in to the Output File of this task.

[Importing Invoices into Sage 50 UK](importing-invoices-into-sage-50-uk)

This task will import your transformed invoices in to Sage .

 * **Input File**The Output File of the previous task.
 * **Fail File**A file for any unsuccessful invoices to be posted to.
 * **Success File**A file for any successful invoices to be posted to.

[Archive Workflow Data](archive-workflow-data)

 * **Archive Folder**The folder for all files used in this task to be archived to.

You can download all the necessary files to perform this integration from our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Excel%20to%20XML%20to%20Sage%2050).

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.