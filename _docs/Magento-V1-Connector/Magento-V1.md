---
slug: magento-v1
redirect_from: "/article/257-introduction-to-the-magento-connector"
title: Magento V1
---
The Magento connector implements an interface to Magento and provides tasks to import and export data from Magento. All data is transferred using an XML format, please refer to the individual task pages for examples of the format for each task.

Each of the tasks require a connection to Magento, for more information on setting up and managing connections see the page [Connecting to Magento](connecting-to-magento).

Zynk requires an API user account to be able to connect to Magento. You can create one from your Magento admin by going to System -> Web Services -> SOAP/XML-RPC Users. Make sure you assign the user a role which grants it access to the areas of Magento you want to integrate with. Roles can be configured from System -> Web Services -> SOAP/XML-RPC Roles.

## Tasks
* [Exporting Attribute Options from Magento](downloading-attribute-options-from-magento)
* [Exporting Credit Memos from Magento](downloading-credit-memos-from-magento)
* [Exporting Customer Groups from Magento](downloading-customer-groups-from-magento)
* [Exporting Customers from Magento](downloading-customers-from-magento)
* [Exporting Invoices from Magento](downloading-invoices-from-magento)
* [Exporting Orders from Magento](downloading-orders-from-magento)
* [Exporting Products from Magento](downloading-products-from-magento)
* [Exporting Product Attributes from Magento](downloading-product-attributes-from-magento)
* [Exporting Product Categories from Magento](downloading-product-categories-from-magento)
* [Exporting Stores from Magento](downloading-stores-from-magento)
* [Updating Inventory in Magento](uploading-inventory-to-magento)
* [Updating Orders in Magento](updating-orders-in-magento)
* [Importing Credit Memos to Magento](uploading-credit-memos-to-magento)
* [Importing Customers to Magento](uploading-customers-to-magento)
* [Importing Group Prices to Magento](uploading-group-prices-to-magento)
* [Importing Invoices to Magento](uploading-invoices-to-magento)
* [Importing Products to Magento](uploading-products-to-magento)
* [Importing Product Attributes to Magento](uploading-product-attributes-to-magento)
* [Importing Product Categories to Magento](uploading-product-categories-to-magento)
* [Importing Shipments to Magento](uploading-shipments-to-magento)
* [Importing Tier Prices to Magento](uploading-tier-prices-to-magento)

## Supported Versions
This connector only supports version 1 of Magento. Please see [Magento V2](magento-v2) for information relating to Magento V2.

## Performance Issue
It is normal for each individual record to take about half a second to export from the Magento API servers. Therefore, it may take quite some time to export a large amount of data. Where appropriate, filters can be used to select only certain records for export, which can reduce the amount of time taken.

## Articles and Sample Files
There is a Workflow Template, Articles and Sample Files on the links below:

* [Workflow Template](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples)
* [Article](magento-to-sage-integration)

## Troubleshooting
* [Troubleshooting the Magento v1 Connector](troubleshooting-the-magento-v1-connector)

