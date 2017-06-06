---
slug: csv-to-sage-integration
redirect_from: "/article/461-csv-to-sage-integration"
title: CSV to Sage Integration
---
This article will detail the process that will you need to go through in order to import data from a **CSV** file in to your **Sage** package. Note, this article is valid for both Sage 200 and Sage 50 integrations however you will need to use different Import and Export tasks depending on which version of Sage you are integrating with. For more detailed information please see the [CSV](csv) section.

What you will not find in this article is how to generate/retrieve the CSV file you are using. This part of the process will solely depend on how your CSV files are generated, whether they are downloaded from a website or imported in to a location on the network on an automated basis, essentially Zynk will be able to work around how the CSV file is generated.

[Converting CSV to XML](converting-csv-to-xml)

This part of the process will take your CSV file and turn it in to XML file based on your configuration at the Task Settings level.

 * **Column Delimiter**This will need to be set based on your CSV file, it means whatever your file is separated on in most cases this will be ','.
 * **File Includes Headers**This can either be set to 'True' or 'False' based on whether or not your CSV file includes headers at the top of the file.
 * **Column**The name of the column you want to exported to the XML file during the transform.
 * **Root**The parent node given to the XML file generated from this task
 * **Row**The child node given to the XML file generated from this task.
 * **Input File**This will be the CSV file you are transforming in to the XML format.
 * **Output File**You will need to set this to the XML file
 * **Export as Elements**This will export the headers in your CSV document as elements in the XML file generated by this task.

[XSLT Transform](xslt-transform)

You can use an XSL file to transform the XML document generated by the **CSV to XML** task as it may not be in the format that Sage requires.

 * **Input File**This will need to be set to the **Output File** from the previous task, the XML file that was previously generated.
 * **Output File**This is where you can specify the name of the file that will be generated by the **XSLT file**.
 * **Parameters**Here you can specify any parameters set in the **XSLT file**.
 * **XSLT File**You will need to specify your transform file here.

[Importing Invoices into Sage 50 UK](importing-invoices-into-sage-50-uk)

This task will actually import your Invoices in to Sage and create them based on the settings you have configured on the task.

 * **Fail File**Here, you can specify a file for any failed orders to be sent to.
 * **Input File**This will need to be set to the **Output File**from the previous task, the XML file containing your Invoices.
 * **Success File**Here, you can specify a file for any successful orders to be sent to.

[Archive Workflow Data](archive-workflow-data)

This part of the process will archive any data used in the workflow for future reference.

 * **Archive Folder**You will need to specify a folder in which you wish to archive your files to.

You can find sample files for this integration on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/CSV%20to%20Sage%2050%20Integration).

These are sample files and may not fit the format of your CSV files, you can use these as a point of reference to see how Zynk will work and then create your own integration around the sample CSV and XSLT files provided by ourselves.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.