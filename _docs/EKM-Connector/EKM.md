---
slug: ekm
title: EKM
---
The EKM connector for Zynk allows you to download your orders, customers and stock levels from your EKM site in XML format and then process them with Zynk. It also allows you to update the status of orders and product stock levels.

Each of the tasks require a connection to EKM, for more information on setting up and managing connections see the page [Connecting to EKM](connecting-to-ekm).

We recommend that only one connection is created in Zynk per EKM store. This is to avoid 'invalid grant' errors due to the existing refresh token being invalidated when a new refresh token is generated.

## Tasks

 * [Exporting Customers from EKM](exporting-customers-from-ekm)
 * [Exporting Orders from EKM](exporting-orders-from-ekm)
 * [Exporting Products from EKM](exporting-products-from-ekm)
 * [Importing Customers into EKM](importing-customers-into-ekm)
 * [Importing Stock Levels into EKM](importing-stock-levels-into-ekm)
 * [Updating Order Statuses in EKM](updating-order-statuses-in-ekm)