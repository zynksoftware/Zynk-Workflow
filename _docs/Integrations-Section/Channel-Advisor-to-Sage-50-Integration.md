---
slug: channel-advisor-to-sage-50-integration
redirect_from: "/article/469-channel-advisor-to-sage-50-integration"
title: Channel Advisor to Sage 50 Integration
---
 This tutorial details the basic principles when dealing with an integration between **Channel Advisor** and **Sage 50**.This workflow will perform one basic task, which is the download of orders from Channel Advisor in to Sage 50 (as sales orders).

You can download a copy of the workflow and files from our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Channel%20Advisor%20to%20Sage%2050%20Integration).

## Assumptions
We make the following assumptions about how the integration should work:

 * All orders will be downloaded to a single 'websales' account in Sage.
 * The product codes in the two systems match.
 * The default tax code and nominal code will be used on the order item lines.

## Download Channel Advisor Orders to Sage - Phase 1
This part of the process will download any new orders from Channel Advisor which have been shipped, and import them in to    Sage. The process consists of the following tasks:

1. [Downloading Orders from Channel Advisor](downloading-orders-from-channel-advisor) - This task will download        orders with shipping status 'Shipped' from Channel Advisor in XML format.
2. [XSLT Transform](xslt-transform) - This task will transform the Channel Advisor order        XML from the previous task into the Zynk XML format, ready to be imported into Sage. The task uses the 'Channel Advisor Orders to Zynk Sales Orders.xslt' XSLT file to perform the transformation. A copy is included with the workflow provided        above.
3. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk) - This task will import the orders contained        in the output file from the previous task in to Sage 50. It will write out any failed or successful orders to separate        output files.

## Archive - Phase 2
This is the final task in the process, and will archive off all data that was used by the workflow process. This allows for    traceability and will assist when debugging the workflow.

1. [Archive Workflow Data](archive-workflow-data) - This task will archive off all data that was used by        the workflow process.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone    on 0191 303 7279. Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.