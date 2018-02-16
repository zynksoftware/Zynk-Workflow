---
slug: core-commerce-to-sage-50-integration
redirect_from: "/article/470-core-commerce-to-sage-50-integration"
title: Core Commerce to Sage 50 Integration
---
This tutorial details the basic principles when dealing with an integration between **Core Commerce** and **Sage 50**. This workflow will perform two basic tasks, which is the download of orders from Core Commerce in to Sage 50 (as sales orders), and the upload of product prices and stock levels from Sage to Core Commerce.

You can download a copy of the workflow and files from our [GitHub site](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Core%20Commerce%20to%20Sage%2050%20Integration).

## Assumptions
We make the following assumptions about how the integration should work:

 * Orders will be downloaded to individual customer accounts in Sage. If an account does not already exist, it will be created automatically. The InternalNumber field in CoreCommerce will be used to store the Sage account references.
 * The product codes in the two systems match.
 * The tax code on each item line will be determined by the delivery address. T1 will be used for UK orders, T4 for EU and T0 for the rest of the world.
 * The default nominal code will be used on the order item lines
 * Only the standard prices from Sage will be uploaded to Core Commerce.

## Download Core Commerce Orders to Sage - Phase 1
This part of the process will download any new orders from Core Commerce with the status 'Pending', and import them in to Sage. If a customer account does not exist in Sage, it will be created automatically. The status of the orders that were imported into Sage successfully will be updated to 'Processed', to prevent the same orders downloading again. The process consists of the following tasks:

1. [Exporting Country Codes From Sage 50 UK](exporting-country-codes-from-sage-50-uk) - This task will export a list of country codes from Sage to an XML file. The results will be used when determining the tax code based on the delivery country, to check whether the country is part of the EU or not.
2. [Downloading Orders from CoreCommerce](downloading-orders-from-corecommerce) - This task will download orders with status 'Pending' from Core Commerce and output the results to an XML file.
3. [Downloading Customers from CoreCommerce](downloading-customers-from-corecommerce) - This task is used to download the customers who placed the orders downloaded by the previous task. This is achieved using razor to read the customer strings from the output file of the previous task. The results are saved to an XML file, which will be used to check whether the customer already exists in Sage.
4. [XSLT Transform](xslt-transform) - This task will transform the Core Commerce order XML into the Zynk XML sales order format, ready to be imported into Sage. The task uses the 'CoreCommerce Orders to Zynk Customers and Sales Orders.xslt' XSLT file to perform the transformation. A copy is included with the workflow provided above. The country codes and customers from tasks 1 and 2 are passed to the XSLT using variables. The country codes are used to determine the tax codes. If a customer does not have an account reference in Core Commerce, the XSLT will convert the customers to the Zynk XML customers format, ready for import into Sage.
5. [Container Task](container-task) - This container task wraps up the tasks related to automatically creating customer accounts into Sage. It is used for organisational purposes only, it doesn't perform any functions of the integration
    1. [Importing Customers into Sage 50 UK](importing-customers-into-sage-50-uk) - This task will import the customers contained in the output file from task 4 into Sage. It will write out any failed or successful imports to separate output files.
    2. [XSLT Transform](xslt-transform) - This task takes the success file from the previous task and transforms it to the Core Commerce customer XML format. It maps the the automatically generated Sage account references of the customers to the InternalNumber field in Core Commerce.
    3. [Uploading Customers to CoreCommerce](uploading-customers-to-corecommerce) - This task takes the output file from the previous task and uploads it to Core Commerce. This will set the account references in Core Commerce, so that any future orders by these customers are downloaded to there existing account in Sage, rather than creating another new account.
6. [Container Task](container-task) - This container task wraps up the tasks related to importing the orders into Sage. It is used for organisational purposes only, it doesn't perform any functions of the integration.   
    1. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk) - This task will import the orders contained in the output file from task 4 into Sage. It will write out any failed or successful orders to separate output files.
    2. [XSLT Transform](xslt-transform) - This task takes the success file from the previous task and transforms it to the Core Commerce order status update XML format.
    3. [Updating Orders in CoreCommerce](updating-orders-in-corecommerce) - This task takes the output file from the previous task and uploads it to Core Commerce. This will change the order status to 'Processed', so that the successfully imported orders won't be downloaded again the next time the workflow runs.

## Upload Prices and Stock Levels to Core Commerce - Phase 2
This part of the process will upload product prices and stock levels from Sage 50 to Core Commerce. The process consists of the following tasks:

1. [Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk) - This task will export modified product information from Sage, and save the result to an XML file, in the Zynk XML products format.
2. [XSLT Transform](xslt-transform) - This task will transform the output file form the previous task to the Core Commerce product XML format, ready for upload to Core Commerce.
3. [Updating Products in CoreCommerce](updating-products-in-corecommerce) - This task will upload the output file from the previous task to Core Commerce.

## Archive - Phase 3
This is the final task in the process, and will archive off all data that was used by the workflow process. This allows for traceability and will assist when debugging the workflow.

1. [Archive Workflow Data](archive-workflow-data) - This task will archive off all data that was used by the workflow process.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.