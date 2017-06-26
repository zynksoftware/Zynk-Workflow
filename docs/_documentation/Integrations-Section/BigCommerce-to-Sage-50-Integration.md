---
slug: bigcommerce-to-sage-50-integration
redirect_from: "/article/463-bigcommerce-to-sage-50-integration"
title: BigCommerce to Sage 50 Integration
---
This tutorial details the basic principles when dealing with an integration between **BigCommerce** and **Sage**. This workflow will perform two basic tasks, which is the downloading orders from BigCommerce in to Sage and then passing inventory levels back up to BigCommerce. We make the assumption that all orders should be downloaded to a single 'websales' account in Sage, and that the SKU codes of the products match in both systems. The integration is not designed to handle products with options.

You can download a copy of the workflow from our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/BigCommerce%20to%20Sage50).

## Download Sales Orders - Phase 1
This part of the process will download any new orders from BigCommerce and import them in to Sage. If the import was successful, the order status on the back end of the BigCommerce site will be updated to prevent the orders from downloading again. The process consists of the following tasks:

1. [Downloading Orders from BigCommerce](downloading-orders-from-bigcommerce) - This task will download orders with a particular status from BigCommerce in XML format.
2. [Auto Mapper](auto-mapper) - This task will transform the BigCommerce order XML into the Zynk XML format ready to be imported into Sage.
3. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk) - This task will import your orders in to Sage 50 and write out any failed or successful orders in to separate files.
4. [Auto Mapper](auto-mapper) - This task will transform the success file from the import sales orders task in to the format we need to update the order status in BigCommerce.
5. [Updating Orders in BigCommerce](updating-orders-in-bigcommerce) - This task will assign any successfully imported orders in BigCommerce to the status specified on the task settings.

## Upload Inventory Levels - Phase 2
This part of the process will export any modified products from Sage 50, and update the stock level of the matching product in BigCommerce. The process consists of the following tasks:

1. [Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk) - This task will export modified product information from Sage 50 in Zynk XML format.
2. [Auto Mapper](auto-mapper) -This task will transform the product XML exported by the previous task to the BigCommerce inventory format, ready to be uploaded to the website.
3. [Updating Inventory in BigCommerce](updating-inventory-in-bigcommerce) - This task will update the stock level of the products in BigCommerce.

## Archive - Phase 3
This is the final task in the process, and will archive off all data that was used by the workflow process. This allows for traceability and will assist when debugging the workflow.

1. [Archive Workflow Data](archive-workflow-data) - This task will archive off all data that was used by the workflow process.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.
