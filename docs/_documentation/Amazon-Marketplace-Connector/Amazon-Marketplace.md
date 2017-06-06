---
slug: amazon-marketplace
redirect_from: "/article/146-introduction-to-the-amazon-marketplace-connector"
title: Amazon Marketplace
---
The Amazon Marketplace connector in Zynk allows you to download your orders from Amazon Marketplace in an XML format, and then process them within Zynk into your Accounting, ERP, CRM or database. It also supports the upload any kind of Amazon compatible data feed (XML or CSV).

Each of the tasks require a connection to Amazon Marketplace, for more information on setting up and managing connections see [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace).

Zynk currently supports the UK, US, CA, DE, ES, FR and IT marketplaces.

## Tasks
* [Downloading Orders from Amazon Marketplace](downloading-orders-from-amazon-marketplace)
* [Uploading Feeds to Amazon Marketplace](uploading-feeds-to-amazon-marketplace)
* [Uploading Inventory Feeds to Amazon Marketplace](uploading-inventory-feeds-to-amazon-marketplace)
* [Uploading Price Feeds to Amazon Marketplace](uploading-price-feeds-to-amazon-marketplace)

Each task listed above requires you to select the countries you wish to download. Please note, the channel settings on your task must correspond to your connection details. For example, if you wish to download orders from Amazon Canada you will be required to enter a North America authorisation token and seller id.

## Managing Inventory

Before starting an integration with Amazon, it is important that you are able to match products between Amazon and the other systems that you are integrating with. You will need to ensure you are using the Merchant SKU / Seller SKU field within Amazon, and that the values entered into this field match the product codes in the systems you are going to integrate with. Note that once you have created an item on Amazon you cannot edit the SKU code as this is the unique identifier for the product, you will first have to remove the item and re-add with the correct SKU.

## Articles and Sample Files
The following articles are available on the links below:

* [Amazon to Sage Integration](458-amazon-to-sage-integration)
* [Amazon Marketplace - Submit Feeds](640-amazon-submit-feeds)
