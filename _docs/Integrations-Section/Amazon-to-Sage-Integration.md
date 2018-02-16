---
slug: amazon-to-sage-integration
redirect_from: "/article/458-amazon-to-sage-integration"
title: Amazon to Sage Integration
---
This article will detail the process you will need to go through to develop an integration between your **Amazon Seller Central** account and your package of **Sage**. We will go through how to download your Amazon orders and import them in to Sage. We will also detail how to upload your Inventory and Price feeds to Amazon.

You can find a template workflow for this process on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples).

## Download Sales Orders - Phase 1
This part of the process will detail how to download and then import your Amazon orders in to Sage.

[Downloading Orders from Amazon Marketplace](downloading-orders-from-amazon-marketplace)

This task will download your orders from Amazon in the raw format we receive.

 * **Country** - Your Amazon Seller Central account's county.
 * **Merchant ID** - This will be your unique Merchant ID, there are instructions on how to get this on this link, see [Obtaining a Merchant ID from Amazon](obtaining-a-merchant-id-from-amazon) for more information.
 * **Download From** - This is the date the orders will initially download from and is normally configured when you are first setting up the workflow.
 * **Order Status** - The order status we will download from Amazon, so for example if you were to set this to 'Shipped' we would download any 'Shipped' orders from the date specified in the above setting.
 * **Output File** - The file in which the orders will be dropped in to.

[Auto Mapper](auto-mapper) - Amazon Sales Orders to Zynk Sales Orders

 * **Input File** - This will be Output File from the previous task.
 * **Mapping** - Here you will need to specify your mapping, in this case it would Amazon Orders to Zynk XML Sales Orders.
 * **Output File** - This will be the transformed file, and will be the file that is imported in to Sage.

[Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk)

 * **Fail File** - This will be the file that any failed orders will be dropped in to, we will also specify any errors so that you can pinpoint any wrongdoings and re download the order.
 * **Input File** - This will be the Output File from the previous task.
 * **Success File** - This will be the file that we drop any successful orders in to.

## Upload Inventory Feed - Phase 2
This part of the process will export product information from Sage, transform it in to an Amazon Inventory Feed and then upload it.

[Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk)

This task will output any modified stock records in to an XML file.
 
 * **Output File** - This is the file that will hold the Zynk XML formatted Stock Records.

[Auto Mapper](auto-mapper) - Zynk Stock Records to Amazon Inventory

This task will transform the Zynk XML format of Stock Records in to an Amazon Inventory Feed.

 * **Input File** - This will be the Output File from the previous task and the file that will be transformed.
 * **Mapping** - Here you will need to specify the mapping you require.
 * **Output File** - This file will be in the Amazon Inventory Feed format which will be uploaded in the next task.

[Uploading Inventory Feeds to Amazon Marketplace](uploading-inventory-feeds-to-amazon-marketplace)

This task will actually upload the inventory to your Amazon Seller Central site.

 * **Input File** - This will be the Output File from the previous task, and will be uploaded to update your inventory.

## Upload Price Feed - Phase 3
This part of the process will upload your prices to your Amazon Seller Central site.

[Auto Mapper](auto-mapper) - Zynk Stock Records to Amazon Prices

 * **Input File** - We can use the previous Export Stock Records task here to generate the Amazon Price Feed information.
 * **Mapping** - Here you will need to specify the mapping you require.
 * **Output File** - This will be your transformed file and will uploaded to Amazon.

[Uploading Price Feeds to Amazon Marketplace](uploading-price-feeds-to-amazon-marketplace)

 * **Input File** - This will be the Output File from the previous task.

## Archive - Phase 4
This is the last part of the process and will essentially archive any data used in the workflow in to the folder specified at the Task Settings level.

[Archive Workflow Data](archive-workflow-data)

 * **Archive Folder** - The folder for the files to be archived to.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.