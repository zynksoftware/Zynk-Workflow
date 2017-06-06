---
slug: connectwise-product-invoice-integration-field-mapping
redirect_from: "/article/185-connectwise-field-mapping"
title: ConnectWise Product Invoice Integration Field Mapping
---


**ConnectWise Customer to Sage 50 Customer Mapping**



The following fields are mapped by default in the ConnectWise to Sage 50 mapping file which is located in ConnectWise Invoice to Sage Product Invoice.XSLT which is stored in the XSLT folder.



| ConnectWise Field | Sage Field |
| -- | -- |
| Account Number | Id |
| Company Name | CompanyName |
| Account Number | Account Ref |
| Contact Name | Forename |
| Address Line 1 | Invoice Address 1 |
| Address Line 2 | Invoice Address 2 |
| City | Invoice Town |
| Postal Code | Invoice Postcode |
| State | Invoice County |
| Phone Number | Telephone |
| Contact name | Delivery Forename |
| Company Name | Delivery Company Name |
| Address Line 1 | Delivery Address 1 |
| Address Line 2 | Delivery Address 2 |
| City | Delivery Town |
| State | Delivery County |
| Postal Code | 	 Delivery Postcode |
| Phone Number | 	 Delivery Telephone  |



Additional Notes for Customer Mapping


- You must set up an Account Number on the finance screen of each ConnectWise customer account in order to import them as customers in Sage 50 - if they do not have an Account number you will not be able to close the invoice in ConnectWise.
- Country will always default to UK as the country is not passed down in the ConnectWise XML

**ConnectWise Invoice to Sage 50 Invoice Mapping**  
The following fields are mapped by default in the ConnectWise to Sage 50 mapping file which is located in ConnectWise Invoice to Sage Product Invoice.XSLT which is stored in the XSLT folder

| 	 **ConnectWise Field** | **Sage Field** |
| -- | -- |
| 	 GLEntryRecID | 	 Id |
| 	 Company Account Number | 	 Customer ID |
| 	 Document Number | 	 Invoice Number (Unless AutoNumbering) |
| 	 Document Number | 	 Customer Order Number |
| 	 Currency ID     | 	 Currency  |
| 	 Company Account Number | 	 Account Ref  |
| 	 Document Number | 	 Order Number  |
| 	 Document Date | 	 Invoice Date  |
| 	 Sales Rep Name | 	 Taken By |
| 	 Company Name | 	 Company  |
| 	 Address Line 1 | 	 Invoice Address 1  |
| 	 Address Line 2 | 	 Invoice Address 2 |
| 	 Address Line 3 | 	 Invoice Address 3 |
| 	 City | 	 Invoice Town |
| 	 Postal Code | 	 Invoice Postcode |
| 	 State | 	 Invoice County |
| 	 Company Name  | 	 Delivery Address Company |
| 	 Address Line 1 | 	 Delivery Address 1 |
| 	 Address Line 2 | 	 Delivery Address 2 |
| 	 Address Line 3 | 	 Delivery Address 3 |
| 	 City | 	 Delivery Address Town |
| 	 Postal Code | 	 Delivery Address Postcode |
| 	 State | 	 Delivery Address County  |
| 	 **Invoice Items** |
| 	 GLEntry Rec ID | 	 Id |
| 	 Item ID | 	 SKU |
| 	 Item Description | 	 Name |
| 	 Sales Description | 	 Description |
| 	 Quantity | 	 Quantity Ordered  |
| 	 Item Price | 	 Unit Price |



Additional Notes for Invoice Mappings


- Tax Code and Tax Rate is taken from the Sage Product Tax Code field and calculated using the Sage 50 calculation rules.
- Nominal Code is taken from the Sage Product Record Nominal Code
- Department is taken from the Sage Product Record Department
- Invoice Type defaults to Product Invoice - Credit Notes are not supported

