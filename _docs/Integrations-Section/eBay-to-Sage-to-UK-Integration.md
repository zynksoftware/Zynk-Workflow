---
slug: ebay-to-sage-to-uk-integration
redirect_from: "/article/457-ebay-to-sage-to-uk-integration"
title: eBay to Sage to UK Integration
---
This article will detail the process you need to go through to integrate your **eBay** and **Sage** systems. We will go through the standard process of downloading your orders and what is involved from your point of view.

You can find a template workflow for this process on our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples).

## Download Sales Orders - Phase 1
This phase will download and import any new eBay orders in to Sage.

[Downloading Orders from eBay](downloading-orders-from-ebay)

This task will download any new orders created in eBay according to the configuration you have set up at the Task Settings level in your workflow.

 * **Download Date** The date when you want to start downloading orders from, can be used to stop the import of older eBay orders if they have already be manually imported into your systems
 * **Download From** The date used to check for modified orders, only orders modified after this date will be downloaded (as well as the date specified above)
 * **Order ID** Can be used to download a single order from eBay, generally used during development
 * **Output File** The name of the file to export the data to

[Auto Mapper](auto-mapper) - eBay Sales Orders to Zynk Sales Orders

This task will map your eBay Sales Orders in to the standard Zynk format we require to import successfully in to Sage.

 * **Input File**This will be the Output File from the previous task.
 * **Mapping**You will need to amend this feature to meet your requirements, and when doing so you populate the necessary parameters in the Auto Mapper window.
 * **Output File**This will be the transformed file and essentially what will be imported in to Sage.

[Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk)

 * **Fail File**This is the file that any failed Sales Orders will be imported in to, we will also write out the nature of the error in this file so you can pinpoint any wrongdoings.
 * **Input File**This will be the Output File from the previous task.
 * **Success File**This is the file that any successful Sales Orders will be imported in to.

## Archive - Phase 2

This part of the process will archive off any data used in the workflow for your reference when reviewing previous orders.

 * [Archive Workflow Data](archive-workflow-data) This will archive off all the data used in the workflow in to a folder specified at Task Settings level.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.