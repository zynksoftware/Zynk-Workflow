---
slug: sage-50-stock-records-to-magento-products
redirect_from: "/article/624-sage-50-stock-records-to-magento-products"
title: Sage 50 Stock Records to Magento Products
---
 This tutorial will run through what is required to upload products from Zynk XML format (export from Sage 50 demo company)to Magento simple products.  Note you will need to have access to a Magento installation with API credentials to upload productdata.  To begin you will need to find the attribute set id to use when creating new products, you can find this from yourMagento admin.        

The Workflow, XSLT and sample XML files can be found            [here](https://github.com/zynksoftware/samples/tree/master/Integration%20Samples/Zynk%20Products%20to%20Magento%20Products), and the XSLT can be found in the Auto Mapper task within Zynk.  If            you do not have a copy of Zynk you can register for a trial [here](http://zynk.com/download-trial/).             The following libraries and tasks will be used in this tutorial:

 * [Exporting Stock Records from Sage 50 UK](exporting-stock-records-from-sage-50-uk)
 * [Auto Mapper](auto-mapper)
 * [Uploading Products to Magento](uploading-products-to-magento)

## Building the Workflow

1. Open Zynk and click on the New Workflow button or choose File > New from the main menu
2. You should now see the Task Library pane displayed.
3. Navigate down to the Connect for Sage 50 library and then Double-click (or Drag and drop) the Export Stock Records                task to copy that task into the Tasks List
4. Select the Export Stock Records task in the Task List and set the Output File to sage_products.xml
5. Locate the Auto Mapper task from the Zynk library and add that task into the Tasks List, setting the following                
 1. Set Input File to sage_products.xml
 2. Set Output File to magento_products.xml
 3. Edit Mapping (use the button on the right hand side of the setting)                        
  1. Choose Input File Format Zynk XML
  2. Choose Input File Data Type Products
  3. Choose Output File Format Magento
  4. Choose Output File Date Type Products
  5. If required change the values of the parameters
6. Locate the Upload Products task in the Magento library and add to the workflow, setting the following                
 1. Set Input File to magento_products.xml
 2. Set Success File to magento_success.xml
 3. Set Fail File to magento_fail.xml
7. Click on the Save button and enter the name Sage to Magento for the name of the Workflow and click Save

## Running the Workflow

To run the workflow click the Run Workflow button, or hit F5.  The workflow should prompt for your connection details            to Sage 50, the sample data is from the Sage 50 Demo Company, but you can choose any company you have setup.             Once the workflow has exported and converted the data it will then prompt for the Magento connection details,            enter your URL, Username and Password to continue.  Depending on the amount of products you have it can            take a while for the information to be uploaded, but you should start to see products appearing in the Magento            product list.

## Modifying the Mapping

The mapping provided in the Auto Mapper is a basic example of creating Magento products.  You will more than likely            need to modify the mapping to set the fields you require in your integration.  As part of the Auto Mapper            you can set the attribute set id for the products you are uploading (edit the mapping and set the parameter value).

If you require any custom fields you can add these to the Fields collection in the XSLT.  The name of the field can            be found from your Magento installation.  Note by default you can only set text field values, not select            options.

If you have any queries on any of the above, feel free to contact our support team via email at support@zynk.com                or via telephone on 0191 303 7279. Please note, as stated on the Auto Mapper task we do not support any changes                to XSLT.