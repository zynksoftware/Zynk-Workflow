---
slug: despatching-sales-orders-in-sage-50-uk
redirect_from: "/article/391-despatching-sales-orders-in-sage-50-uk"
title: Despatching Sales Orders in Sage 50 UK
---
This task will despatch allocated sales orders in Sage based on the selected options. It will export a list of goods despatched notes in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Allow Partial Despatch
_Required_  
If set to True, the task will despatch both part allocated and fully allocated sales orders. If set to False, the task will only despatch fully allocated sales order.

### Despatch Orders Taken By
_Optional_  
Specify a username to only despatch orders that were taken by this user.

### Payment Type
_Required_  
Specify the type of payment to use on the invoice.

### Output File
_Required_  
The name of the file to export the generated goods despatched notes to.

### Zynk Settings
See [Common Task Settings](common-task-settings)