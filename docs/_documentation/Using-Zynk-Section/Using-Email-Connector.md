---
slug: using-email-connector
redirect_from: "/article/633-using-email-connector"
title: Using Email Connector
---
 This tutorial gives an example of how the Email Connector can be used to send automated emails using Zynk. We will demonstratea workflow which sends an order confirmation email to customers who have placed         

You can download a copy of the workflow from our             [GitHub site](https://github.com/zynksoftware/samples/tree/master/Workflow%20Samples).

The workflow consists of the following tasks. Note that we don't provide details for all of the task settings here, only            the relevant ones. Please see the individual task pages for full details of all the settings.

## [Import Sales Orders into Sage](importing-sales-orders-into-sage-50-uk)
This is the task that creates the sales orders in Sage. Note that we don't go into any detail about where the orders have            come from as this is not relevant to the tutorial. In practice it doesn't matter what the source of the orders            is, as they will always need to be stored in the standard Zynk XML format in order to be able to import them            into Sage. We are only interested in the success file from this task, as this will contain the email addresses            of the customers whose orders have been successfully imported into Sage.

### Success File
This is where successfully imported sales orders will be saved to.
`sales_orders_success.xml`

## [XML Repeater](xml-repeater)
This task will be used to loop through each of the orders that were imported into Sage. The sub-tasks of the XML Repeater    will be ran once for each order that was imported into Sage.    

### Input File
This is the success file from the previous task.
`sales_orders_success.xml`

### XPath Query
This is the XPath Query to get the collection of SalesOrder nodes from the input file.
`Company/SalesOrders/SalesOrder`

## [If Email Exists](if-email-exists)
This task will check whether an email address is valid. We will use this to ensure we don't try to send emails if no email        address was provided, or it was typed in incorrectly by the customer.

### Email Address To Validate
This will read the email address from the current sales order being processed by the XML Repeater. The 'Use Razor Engine' option must be enabled for this to work.
`@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Email").InnerText`

## [Send Email](send-email)
This task will send an email to the customer. As this is a sub-task of the If Email Exists task, it will only run if the        email validation was passed. Note that you will need to enter your own SMTP details to use to send the emails.

### Body
This is the content of the email. Note how we set the customer's name based on the sales order, just like how we get the email address. The 'Use Razor Engine' option must be enabled for this to work.
See workflow

### From
This is the 'From' address on the email.
accounts@zynk.com

### Subject
This is the email's subject. In this example we are just using a static piece of text, but you could take info from the sales order and use it here, such as the order number, just like we've done with the 'To' address below.
Order Confirmation

### To
This is the 'To' address on the emails. We take this from the sales order dynamically. The 'Use Razor Engine' option must be enabled for this to work.
`@Context.Object.SelectSingleNode("CustomerInvoiceAddress/Email").InnerText`