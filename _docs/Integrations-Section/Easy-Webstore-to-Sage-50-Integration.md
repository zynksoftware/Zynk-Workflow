---
slug: easy-webstore-to-sage-50-integration
redirect_from: "/article/466-easy-webstore-to-sage-50-integration"
title: Easy Webstore to Sage 50 Integration
---
 This tutorial details the basic principles when dealing with an integration between **Easy Webstore** and **Sage**. This workflow will perform two basic tasks, which is the downloading orders from Easy Webstore in to Sage and then passing inventorylevels back up to Easy Webstore. We make the assumption that all orders should be downloaded to a single 'websales' accountin Sage, and that the SKU codes of the products match in both systems. The integration is not designed to handle productswith options or bundled items.

You can download a copy of the workflow    [here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/eBay%20to%20Sage%2050).

## Download Orders to Sage - Phase 1
This part of the process will download any new orders from Easy Webstore and import them in to Sage. If the import was successful,    the order status on the back end of the Easy Webstore site will be updated to prevent the orders from downloading again.    The process consists of the following tasks:

1. [Downloading Orders from Easy Webstore](downloading-orders-from-easy-webstore) - This task will download orders with a particular status from Easy Webstore in XML format. In the sample workflow provided the status is set to 'Payment\_Pending'.
2. [Auto Mapper](auto-mapper) - This auto mapper task will transform the Easy Webstore order XML downloaded by the previous task into the Zynk XML format, ready to be imported into Sage. You can edit the transformation to customise the field mappings between the Easy Webstore orders and Sage sales orders.
3. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk) - This task will take the output file from the previous task and import the orders contained in it into Sage 50. It will write out any failed or successful orders in to separate success and fail files.
4. [Auto Mapper](auto-mapper) - This XSLT Transform task will transform the success file from the import sales orders task in to the format we need to update the order status in Easy Webstore. We have used an XSLT Transform task as the Auto Mapper does not currently support this transform. The transform in the sample workflow sets the status to 'Pending'.
5. [Updating Order Status in Easy Webstore](updating-order-status-in-easy-webstore) - This task will take the        order status updates outputted by the previous task and upload them to Easy Webstore.

## Upload Inventory Levels to Easy Webstore - Phase 2
This part of the process will export any updated products from Sage 50, and update the stock level of the matching product    in Easy Webstore. The process consists of the following tasks:

1. [Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk) - This task will export modified product information from Sage 50 in Zynk XML format.
2. [Auto Mapper](auto-mapper) -This Auto Mapper task will transform the product XML exported by the previous task to the Easy Webstore inventory format, ready to be uploaded to the website.
3. [Updating Inventory in Easy Webstore](updating-inventory-in-easy-webstore) - This task will take the inventory XML outputted by the previous task and upload it to Easy Webstore.

## Archive - Phase 3
This is the final task in the process, and will archive off all data that was used by the workflow process. This allows for    traceability and will assist when debugging the workflow.

1. [Archive Workflow Data](archive-workflow-data) - This task will archive off all data that was used by the workflow process.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone    on 0191 303 7279. Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.