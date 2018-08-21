---
slug: exporting-reports-from-amazon-marketplace
title: Exporting Reports from Amazon Marketplace
---
This task allows you to run reports from your Amazon MWS account. Some reports will return XML data, while others will return tab delimited data.

## Settings
### API Call Delay
_Required_  
Specify the delay in milliseconds to use between calls to Amazon. Amazon throttle requests to their services, so if sending a large data set you may need to increase this limit.

### Connection
_Required_  
The Amazon Marketplace Connection to use. See the [Connecting to Amazon Marketplace](connecting-to-amazon-marketplace) article if you require more information on how to create/manage connections.

### End Date
_Optional_  
Specify an end date to filter the data returned by the report.

### Output File
_Required_  
The name of the file to export the data returned by the report to.

### Report Options
_Optional_  
Some reports allow additional options to be specified, which can be found in Amazon's [documentation](http://docs.developer.amazonservices.com/en_UK/reports/Reports_ReportType.html). Enter the name and desired value of the option into this list.  

### Report Type
_Required_  
Select the type of report to run. Full details of each report type can be found in Amazon's [documentation](http://docs.developer.amazonservices.com/en_UK/reports/Reports_ReportType.html).

### Start Date
_Optional_  
Specify an start date to filter the data returned by the report.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file for the '_GET_MERCHANT_LISTINGS_ALL_DATA_' report:
```
item-name	item-description	listing-id	seller-sku	price	quantity	open-date	image-url	item-is-marketplace	product-id-type	zshop-shipping-fee	item-note	item-condition	zshop-category1	zshop-browse-path	zshop-storefront-feature	asin1	asin2	asin3	will-ship-internationally	expedited-shipping	zshop-boldface	product-id	bid-for-featured-placement	add-delete	pending-quantity	fulfillment-channel	merchant-shipping-group	status
Vest		0708QHIDPCS	1234567	20	1	08/07/2016 10:12:40 BST		y	3			11				B01I53BE4O						680242554716			0	DEFAULT	Migrated Template	Active
Survive The Vibe [Audio CD]		0330INLVNF4	35-GFRR-W3VC	0.02	1	30/03/2011 16:23:57 BST		y	4		NOT A REAL ITEM	4				B004ADOCTI						3800065711135			0	DEFAULT	Migrated Template	Active
Apple TV 2, MC572FD_A		0324IL4Y6TS	ATV2	10	1	24/03/2011 09:29:39 GMT		y	1			1				B0041IZHVO						B0041IZHVO			0	DEFAULT	Migrated Template	Inactive
```