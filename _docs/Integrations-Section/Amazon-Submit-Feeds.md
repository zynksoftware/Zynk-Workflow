---
slug: amazon-submit-feeds
redirect_from: "/article/640-amazon-submit-feeds"
title: Amazon Submit Feeds
---
 This tutorial does not cover publishing product data to Amazon, only updating stock levels and prices - it is assumed that the products already exist in your Amazon inventory and the Amazon Merchant SKU matches the Sage Product Code. You will also need your Merchant ID which you should have received after associating your Amazon Seller Central account with our Developer Account,  see [Obtaining a Merchant ID from Amazon](obtaining-a-merchant-id-from-amazon).

## Zynk Connectors  
 For this tutorial you will need access to the following connectors in Zynk:
 * [Sage 50 UK](sage-50-uk)
 * [Amazon Marketplace](amazon-marketplace)
 * [XML and XSLT](xml-and-xslt)

## Required Files
 * Connect Products to Amazon Inventory.XSLT
 * Connect Products to Amazon Prices.XSLT
 * Connect 50 to Amazon Sample.WKF (optional)

## Creating the Workflow

1. From the task library add the "Connect for Sage 50 - Export Stock Records" task        
    * Set the Output File to products.xml
    * Optionally set the Export All flag to True to always update all product information
2. Next, select the XML Library and the XSLT Transform task and drag that into your workflow        
    * Set the Task Name to Inventory Transform
    * Set the Input File to products.xml
    * Set the Output File to inventory.xml
    * Set the XSLT File to Connect Products to Amazon Inventory.XSLT (or the path where you downloaded the                file to)
    * Set the following Parameters: MerchantID = Your Amazon Merchant ID
3. Next, add a second XML Library XSLT Transform task to the workflow        
    * Set the Task Name to Price Transform
    * Set the Input File to products.xml
    * Set the Output File to price.xml
    * Set the XSLT File to Connect Products to Amazon Prices.XSLT (or the path where you downloaded the file                to)
    * Set the following Parameters: MerchantID = Your Amazon Merchant ID, Currency = GBP (or your base selling                currency)
4. Next, add the Upload Inventory Feed task from the Amazon MWS library        
    * Set Merchant ID to your Amazon Merchant ID
    * Set Market Place ID to your Amazon Market Place ID
    * Set Country to the correct country for your Amazon store
    * Set Input File to inventory.xml
5. Finally add the Upload Price Feed task from the Amazon MWS library        
    * Set Merchant ID to your Amazon Merchant ID
    * Set Market Place ID to your Amazon Market Place ID
    * Set Country to the correct country for your Amazon store
    * Set Input File to price.xml

## Testing the Workflow
1. Save the workflow as 'Sage 50 to Amazon'.
2. Run the workflow.
3. Check the output files have been created successfully in the workflow's working directory (this folder can be accessed        from the 'Data' tab by clicking the 'Working Directory' button):        
    * products.xml
    * inventory.xml
    * price.xml
4. Check the stock levels and prices have been updated within Amazon Seller Central.
