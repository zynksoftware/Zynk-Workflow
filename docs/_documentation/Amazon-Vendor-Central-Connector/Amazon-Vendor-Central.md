---
slug: amazon-vendor-central
redirect_from: "/article/159-introduction-to-the-amazon-vendor-central-connector"
title: Amazon Vendor Central
---
The Amazon Vendor Central connector provides functions to import and export EDI files from Amazon Vendor Central. As with most of the tasks in Zynk, the data is provided in XML format. The tasks automatically convert this to/from the EDIFACT D96A format used by Amazon.

Each of the tasks require a connection to Amazon Vendor Central, for more information on setting up and managing connections see the page [Connecting to Amazon Vendor Central](connecting-to-amazon-vendor-central).

All data is exchanged via an SFTP connection, Zynk does not support AS2 connections to Amazon. The SFTP connection can be configured in Vendor Central under EDI Self Service Setup > Basic Setup. Refer to the documentation provided by Amazon for instructions on how do this. Please note that Zynk does not currently support performing the connection tests required by Amazon during the setup process. You can perform these manually using an application which supports SFTP, such as Filezilla.

## Tasks

* [Downloading Purchases from Amazon Vendor Central](downloading-purchases-from-amazon-vendor-central)
* [Notify Purchase Orders to Amazon Vendor Central](notify-purchase-orders-to-amazon-vendor-central)
* [Uploading Despatch Advice to Amazon Vendor Central](uploading-despatch-advice-to-amazon-vendor-central)
* [Uploading Invoices to Amazon Vendor Central](uploading-invoices-to-amazon-vendor-central)
* [Uploading Purchase Order Responses to Amazon Vendor Central](uploading-purchase-order-responses-to-amazon-vendor-central)

## Installing the Amazon Vendor Central Connector

The Amazon Vendor Central connector isn't included in the standard Zynk installation. You need to install it separately by following the instructions below:

1. Run Zynk as an Administrator (right-click and Run As Administrator)
2. Choose Extensions -> Extensions Manger from the main toolbar.
3. In the Additions tab, select Amazon Vendor Central and click Install.

![Zynk Extensions](http://d33v4339jhl8k0.cloudfront.net/docs/assets/565effd4c697915b26a5c620/images/5873910490336009736c4146/file-YxHmwztu1C.png)

4. Refresh the Task Library (Choose Tools -> Refresh Task Library from the main toolbar)