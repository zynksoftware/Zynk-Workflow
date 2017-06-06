---
slug: export-invoice-as-pdf-from-sage-50
redirect_from: "/article/639-export-invoice-as-pdf-from-sage-50"
title: Export Invoice as PDF from Sage 50
---
In this article, I am going to give an example of how to save invoices locally to your machine as pdf files. You can find a sample workflow for this on our[GitHub site](https://github.com/zynksoftware/samples/blob/master/Workflow%20Samples/Export%20Invoice%20as%20PDF%20from%20Sage%2050.wkf).

Firstly, I am going to export some invoices from Sage 50 and use the resulting file to filter my Export Report task. Then, I am going to use an XML Repeater task to loop over the invoices file. Using InvoiceNumber element from the XML I will assign my criteria to export. 

![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b477a5c697914361565b09/file-ZrcUIYAvmT.png)

[Exporting Invoices from Sage 50 UK](exporting-invoices-from-sage-50-uk)

 * **Output File** - invoices.xml

[XML Repeater](xml-repeater)

 * **Input File** - invoices.xml
 * **XPath** - Company/Invoices/Invoice

[Exporting Reports from Sage 50 UK](exporting-reports-from-sage-50-uk)

 * **Criteria** - You'll need to create one criteria variable. Set the 'Key' setting to INVOICE\_NUMBER and the 'Value' setting to @(Context.Current["InvoiceNumber"]). For the 'Value' setting, make sure you tick the 'Use Razor Engine' option.
 * **Output File** - @(Context.Current["InvoiceNumber"]).pdf - Make sure you tick the 'Use Razor Engine' option.
 * **Output Type** - pdf
 * **Report File** - The Sage layout file to use to generate the invoice, e.g C:\ProgramData\Sage\Accounts\2015\Company.000\Layouts\INVDIS11.layout

Please note, you can access any element from the XML so you can call your Output File anything you like.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.