---
slug: website-script-based-integration
redirect_from: "/article/462-website-script-based-integration"
title: Website Script Based Integration
---
This article will provide an overview of a typical script based Website to Sage integration (the example Workflow provided is specifically for a Sage 50 based integration but can be replaced by the relevant Sage 200 or ACT! tasks). More information can be found on the connector pages [Sage 50 UK](sage-50-uk), [Sage 200](sage-200) and [ACT!](act). What you will not find in this article is how to develop the website scripts. What the website scripts contain and what (programming) language they are developed in is entirely dependent upon the requirements of the project and what (programming) language the website itself is developed in. Some example scripts of more common e-commerce website integrations are [available here](https://github.com/zynksoftware/samples/tree/master/PHP).
 
 The sample Workflow (Website Script Based Sage 50 Integration) which accompanies this article can be found on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Website%20Script%20Based%20Sage%2050%20Integration/My%20Workflows).The sample Workflow consists of the following tasks
 
 1. [HTTP Task](http-task) - Download Website XML
    GETs any available data from the specified  URL and downloads to the specified Output File on the local disk to be processed by the rest of the Workflow.
    Typically, the website script being called will run queries against the website database, generating any data needing to be downloaded in the Zynk.Connect.Objects XML structure.
    e.g. The script might query the customers table for any Trade accounts who do not yet have an account reference stored on the website (so that these new accounts may be imported into Sage and have an automatic account reference assigned), as well as querying the orders table for any orders matching a status of Pending which are not currently marked as posted (a boolean column to indicate if an order has been previously downloaded into Sage)
2. [Importing Customers into Sage 50 UK](importing-customers-into-sage-50-uk)
    Attempt to import any customers present in the data downloaded from the website script into Sage 50. Outputting customers which failed to import to the  Fail File and any successfully imported customers to the Success File.
3. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk)
    Attempt to import any sales orders present in the data downloaded from the website script into Sage 50. Outputting sales orders which failed to import to the  Fail File and any successfully imported sales orders to the Success File.
4. [HTTP Task](http-task) - Notify Successfully Imported Customers
    POSTs the Import Customers Success File back to the specified  URL, saving the response to the Output File. 
    Typically, the website script being called will need to update certain information in the website database based on the data that is posted back. The website script should be written to accept POST XML data in the Zynk.Connect.Objects XML structure.
    e.g. The script might iterate over the customers contained in the POST XML, using the Id node from the customer XML as the website customer ID and updating the website customer account reference field based on the AccountReference node from the customer XML, writing the successfully ran queries to the output as well as any encountered errors.
5. [HTTP Task](http-task) - Notify Successfully Imported Sales Orders
    POSTs the Import Sales Orders Success File back to the specified  URL, saving the response to the Output File.
    Typically, the website script being called will need to update certain information in the website database based on the data that is posted back. The website script should be written to accept POST XML data in the Zynk.Connect.Objects XML structure.
    e.g. The script might iterate over the sales orders contained in the POST XML, using the Id node from the sales order XML as the website order ID and updating the website order status field to Processed as well as marking the website order as Posted, writing the successfully ran queries to the output as well as any encountered errors.
6. [Splitting XML Files](splitting-xml-files) - Split Exported Stock Records XML Into Smaller Chunks
    Splits the Export Stock Records Output File based on the Zynk Connect Products  XPath Query (/Company/Products/Product) into multiple files in the Output Folder, with each file having no more Product records than the specified Record Limit.
    Typically, as a best practice, we would run any exported data through an XMLSplitTask in order to prevent large amounts of data in the XML from causing the website scripts to exceed their allowed timeout. (i.e. by separating the file into smaller files with less records).
    The original export file being split remains in the Working data directory.
7. [File Repeater](file-repeater) - For Every Stock Record XML File
    Iterates over the files within the Split Exported Stock Records XML Into Smaller Chunks Output Folder.
  1. [HTTP Task](http-task) - Upload Stock Record File To Website
    POSTs the current split file to the specified  URL, saving the response to the Output Folder (will be defaulted to the Working data directory for the current Workflow, with the name of the current file being repeated, appended with '_response.txt').
    Typically, the website script being called will need to insert/update certain information in the website database based on the data that is uploaded. The website script should be written to accept POST XML data in the Zynk.Connect.Objects XML structure.
    e.g. The script might iterate over the product data contained in the POST XML, using the Sku node to look for products with a matching product code on the website and then update the website product's quantity based on the QtyInStock node less the QtyAllocated node (to obtain a true free stock value).
  2. [Delete File](delete-file) - Delete Processed Stock Record Chunk File
    Deletes the current split file. 
    Typically, as a best practice when using the XMLSplitTask to split large files into smaller 'chunks', once a split file has been processed it should be deleted, so that the next time the Workflow runs, only up to date data is being processed.
8. [Archive Workflow Data](archive-workflow-data)
    Compresses all files within the Working data directory for the current Workflow into a single zip file in the Archive Folder with the name of the date and time that the archive was created, appended with '_archive.zip'.
    Typically, as a best practice, we would structure Zynk Workflow's so that all data relating to the Workflow run remains in the Working data directory, meaning that the ArchiveWorkflowData task can be dropped at the end of the Workflow and the data stored for traceability purposes.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.
