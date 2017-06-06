---
slug: magento-to-sage-integration
redirect_from: "/article/456-magento-to-sage-integration"
title: Magento to Sage Integration
---
This is a tutorial detailing the basic principles when dealing with an integration between **Magento** and **Sage**. This workflow will perform the standard tasks when considering this type of integration, which is the downloading orders in to Sage and then passing inventory levels back up to Magento.

There is a Workflow Template for both Sage 50 and Sage 200 integrations available [here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Magento%20to%20Sage%20Integration).

## Download Sales Orders - Phase 1
This part of the process will download any new orders from Magento and then be taken through the standard process of importing them in to Sage and updating the order on the back end of the Magento site.

[Downloading Orders from Magento](downloading-orders-from-magento)

This task will download orders created/updated since the last time the task was run, from Magento in XML format. The results can be filtered if required. See attachments for sample file.

 * **Output File** - The name of the file to export the orders to.
 * **Filter Property Optional.** - The property the filter is to be based upon.
 * **Filter Type** - Set to eq to return records where the property matches the specified value, gt will return records where the property is greater than the specified value, lt will return records where the property is less than the specified value, and like will return records where the property contains the specified value.
 * **Filter Value Optional.** - The value the filter is to be based upon.
 * **Download Stage Optional.** - Set the status of the orders to be downloaded (e.g. pending, processing, complete).

[Auto Mapper](auto-mapper) - Magento Orders to Zynk Sales Orders

This task will transform the Magento orders in to the standard Zynk format so we can import it in to Sage.

 * **Input File** - This will be the Output File from the previous task. This is the Magento order format we receive when we download an order from Magento.
 * **Mapping** - This is the setting to determine which mapping you are looking for, make sure you specify any parameters that appear once you specify your mapping.
 * **Output File** - This will be the name of the transformed file and will be the file that you import in to Sage.

[Importing Sales Orders into Sage 50 UK](importing-sales-orders-into-sage-50-uk)

This task will Import your Sales Orders in to Sage and write out any failed or successful orders in to separate files.

 * **Fail File** - This is the file that any failed Sales Orders will be imported in to, we will also write out the nature of the error in this file so you can pinpoint any wrongdoings.
 * **Input File** - This will be the Output File from the previous task.
 * **Success File** - This is the file that any successful Sales Orders will be imported in to.

[Auto Mapper](auto-mapper) - Zynk Sales Orders to Update Magento Orders

This task will transform the Success File from the previous task in to the format we need to update the order in Magento.

 * **Input File** - This will be the Success File from the previous task.
 * **Mapping** - This is the setting to determine which mapping you are looking for, make sure you specify any parameters that appear once you specify your mapping.
 * **Output File** - This will be the name of the transformed file and will be the file that you upload to Magento.

[Updating Orders in Magento](updating-orders-in-magento)

This task will assign any successfully imported orders in Magento to the status specified on the task settings.

 * **Input File** - The XML file containing the orders to be updated in Magento.
 * **Notify Customer** - Set to true to notify the customer of the update by email, set to false to not notify the customer.
 * **Notify Stage** - Sets the status the order should be changed to, and be shown in the notification (e.g. pending, processed, complete).

## **Upload Inventory Levels - Phase 2**

[Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk)

This task will export Product information from Sage Sales ledger in Zynk XML format.

 * **Export All** - Set this to False to export records modified since the last export, if set to True it will export all records every time it runs
 * **Export Published** - Set this value to True if you want to only export products marked as Publish if set to False it will ignore the published flag and export all records
 * **Export Attachments** - Set to True if you want the attachments exported from Customers note: this will result in very large XML output files.
 * **Attachment Search Pattern** - File search pattern for attachment export e.g. \*.PDF
 * **Output File** - The name of the file to export to. Data is exported in Connect XML format.

[Auto Mapper](auto-mapper) - Zynk Stock Records to Magento Inventory

This task will transform our Zynk Stock Records format in to the standard Magento Inventory format to update the levels on the Magento site.

 * **Input File** - This will be Output File from the previous task.
 * **Mapping** - This is the setting to determine which mapping you are looking for, make sure you specify any parameters that appear once you specify your mapping.
 * **Output File** - This will be the name of the transformed file and will be the file that you upload to Magento.

[Uploading Inventory to Magento](uploading-inventory-to-magento)

This task will update stock data for the products in Magento.

 * **Input File** - The XML file containing the products to update stock levels for.

## Archive - Phase 3
This is the final task in the process, this will archive off any data in to a folder specified at the Task Settings level.

[Archive Workflow Data](archive-workflow-data)

 * **Archive Folder** - This is the folder where files will be archived to, you can use this as a point of reference to check previous success files etc.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com or via telephone on 0191 303 7279.  Please note, as stated on the Auto Mapper task we do not support any changes to XSLT.