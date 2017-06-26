---
slug: shopify-to-sage-50-integration
redirect_from: "/article/712-shopify-to-sage-50-integration"
title: Shopify to Sage 50 Integration
---
This is a tutorial detailing the basic principles when building an integration between **Shopify** and **Sage 50**. This workflow will perform the standard tasks when considering this type of integration, which is the downloading of orders from Shopify into Sage 50.

You can download a sample integration for this process [here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Shopify%20to%20Sage%2050%20Integration).

## Download Sales Orders - Phase 1
This part of the process will download any new order form Shopify and then be taken through the standard process of importing them into Sage.

[Downloading Orders from Shopify](downloading-orders-from-shopify)

This task will download orders created/updated since the last time the taks was ran. The results can be filtered by status if required.

 * **Output File** - The name of the file to export orders to.
 * **Status** - You can optionally filter the order download by the status of the order.
 * **Connection** - The connection to Shopify.
 * **Download All** - You can optionally download all orders from Shopify.

[Auto Mapper](auto-mapper)

This task will transform the Shopify orders into the standard Zynk Sales Order XML format.

 * **Input File**- This will be the output file from the previous task, the order file in Shopify XML format.
 * **Mapping**- This is the setting to determine which mapping you are looking for, with the below parameters.
   * **AccountReference** - The customer account assigned for web orders.
   * **BankAccount** - The bank account assigned for web orders.
   * **TaxCode** - The tax code used for web ordes
   * **CarriageTaxCode** - The tax code used for shipping on web orders.

 * **Output File**- This will be the name of the transformed file and will contain the data you import into Sage.

[Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk)

This task will import your Sales Orders into Sage and write out any successful or failed orders as part of the process.

 * **Fail File**- This is the file that any failed sales orders will be written to.
 * **Input File**- This will be the output from the previous task, the file containing Zynk Sales Order XML data.
 * **Success File**- This is the file that any successful orders will be written to.

[Archive Workflow Data](archive-workflow-data)

This task will save any files used during the process to a .zip in a location of your choice.

 * **Archive Folder**- The folder you wish to save archived records to.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.
