---
slug: using-pdf-connector
redirect_from: "/article/642-using-pdf-connector"
title: Using PDF Connector
---
The PDF Documents connector in Zynk allows you to generate PDF documents from a range of different sources. The generated PDF could then be used with another task, such as the Send Email task to send it as an attachment.

The sample workflow and files for the tasks below can be downloaded from our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/PDF%20Example).

## HTML to PDF
Use the HTML to PDF task to convert a web page or HTML formatted document to PDF. In this example we convert this article to PDF format. The task settings are configured as follows:

 * **Input URI** - This is set to the URL of this article.
 * **Output File** - This is the PDF file to save the document to, and is set to `Generating PDFs Article.pdf`.
 * **Template File** - This setting is used for adding letterheads/watermarks to the generated document, and is not used in this example.

This task is particularly useful given that HTML is an XML based language. This means you can generate HTML using other tasks in Zynk, such as the [XSLT Transform](xslt-transform). For example, you could use an XSLT transform to generate a HTML formatted report, which could then converted to PDF and sent as an email attachment.

## Excel to PDF
Use the Excel to PDF task to convert an Excel spreadsheet to PDF format. The task settings are configured as follows:

 * **Input File** - This is set to the Excel spreadsheet file, `customer_spreadsheet.xls`.
 * **Output File** - This is the PDF file to save the document to, and is set to `Customer Spreadsheet.pdf`.

## Word to PDF
Use the Word to PDF task to convert a Word document to PDF format. The task settings are configured as follows:

 * **Input File** - This is set to the Word document file, `zynk_article.doc`.
 * **Output File** - This is the PDF file to save the document to, and is set to `Zynk Article.pdf`.