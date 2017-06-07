---
slug: salesforce-to-sage-50-integration
redirect_from: "/article/467-salesforce-to-sage-50-integration"
title: Salesforce to Sage 50 Integration
---
This tutorial details the basic principles when dealing with an integration between **Salesforce** and **Sage 50**. This workflow will perform three basic tasks, which is the downloading opportunities from Salesforce to Sage, upload customers from Sage to Salesforce and upload products from Sage to Salesforce. We make the assumption that the product codes of the products match in both systems. The integration is not designed to handle products with options. We also assume that a custom external ID field named `SageAccountReference__c` is available on the accounts in Salesforce, and will be used by the integration to store the Sage A/C reference that corresponds with each account in Salesforce.

You can download a copy of the workflow from [here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Salesforce%20to%20Sage%2050). Please bear in mind when using this workflow that Salesforce is a highly customisable system, and the workflow will almost certainly need to be adapted to your needs.

## Download Opportunities - Phase 1
This part of the process will download new 'Closed Won' opportunities from Salesforce and import them in to Sage. If the import was successful, the status in Salesforce will be updated to 'Order Confirmed' to prevent the opportunities from downloading again. It will automatically create customer accounts in Sage if they do not already exist. The process consists of the following tasks:

1. [Querying Records in Salesforce](querying-records-in-salesforce) - This task will query Salesforce for all opportunities where the 'StageName' field is set to 'Closed Won'. The results will be saved to the 'salesforce\_opportunities.xml' file.
2. [XSLT Transform](xslt-transform) - This task will transform the output file from the previous task to customers and orders in the Zynk XML format, ready to be imported into Sage. Refer to our [API Documentation](zynk-xml-overview) for detailed XML schema information.
3. [Container Task](container-task) - This container task wraps up the tasks related to automatically creating customer accounts into Sage. It is used for organisational purposes only, it doesn't perform any functions of the integration.
    1. [Importing Customers into Sage 50 UK](importing-customers-into-sage-50-uk) - This task takes the output file from the 'Transform to Zynk Customer + Sales Order XML' task and imports the customers contained within the file into Sage. The 'Auto Generate References' setting on this task controls how new A/C references are generated. The task will write out any failed or successful customer imports to separate success and fail files.
    2. [XML Repeater](xml-repeater) - This XML Repeater task will loop through each customer in the success file from the previous task, and run the following sub-tasks for each one. This process will upload the generated Sage A/C reference of each customer to Salesforce.	
        1. [Razor Template](razor-template) - This Razor template task writes out the Sage A/C reference of the customer in the Salesforce XML format, ready to upload to the corresponding account in Salesforce. The Sage A/C reference of the customer is accessed using the context variables from the XML Repeater task.
        2. [Updating Records in Salesforce](updating-records-in-salesforce) - This task will upload the output file from the previous task to Salesforce. This will update the Sage A/C reference stored on the account in Salesforce. The ID of the Salesforce account to update is accessed using the context variables from the XML Repeater task.
4. [Container Task](container-task) - This container task wraps up the tasks related to importing orders into Sage. It is used for organisational purposes only, it doesn't perform any functions of the integration.  
    1. [Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk) - This task takes the output file from the 'Transform to Zynk Customer + Sales Order XML' task and imports the orders contained within the file into Sage. The task will write out any failed or successful order imports to separate success and fail files.
    2. [XML Repeater](xml-repeater) - This XML Repeater task will loop through each order in the success file from the previous task, and run the following sub-tasks for each one. This process will update the status of the corresponding opportunities in Salesforce.	
        1. [Razor Template](razor-template) - This Razor template task writes out the new status of the order in the Salesforce XML format, ready to upload to the corresponding account in Salesforce.
        2. [Updating Records in Salesforce](updating-records-in-salesforce) - This task will upload the output file from the previous task to Salesforce. This will update the status of the opportunity in Salesforce. The ID of the Salesforce opportunity to update is accessed using the context variables from the XML Repeater task.

## Upload Customers to Salesforce - Phase 2
This part of the process will export any modified customers from Sage 50, and update the corresponding account in Salesforce.  The process consists of the following tasks:

1. [Exporting Customers from Sage 50 UK](exporting-customers-from-sage-50-uk) - This task will export modified customer information from Sage 50 in Zynk XML format.
2. [Importing Records to Salesforce (Bulk)](importing-records-to-salesforce-bulk) - This task will upload the customers information contained in the output file from the previous task to the accounts module in Salesforce. The accounts are matched based on the A/C field in Sage (i.e. the AccountReference in the XML file) and the SageAccountReference__c field in Salesforce.

## Upload Products to Salesforce - Phase 3
This part of the process will export any modified products from Sage 50, and update the corresponding product in Salesforce. The process consists of the following tasks:

1. [Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk) - This task will export modified product information from Sage 50 in Zynk XML format.
2. [Importing Records to Salesforce (Bulk)](importing-records-to-salesforce-bulk) - This task will upload the product information contained in the output file from the previous task to the Product2 module in Salesforce. The products are matched based on the product code field in Sage (i.e. the Sku in the XML file) and the ProductCode field in Salesforce.

## Archive - Phase 4
This is the final task in the process, and will archive off all data that was used by the workflow process. This allows for traceability and will assist when debugging the workflow.

1. [Archive Workflow Data](archive-workflow-data) - This task will archive off all data that was used by the workflow process.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.