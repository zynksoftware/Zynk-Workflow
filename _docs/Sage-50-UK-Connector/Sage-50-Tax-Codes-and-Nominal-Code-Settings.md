---
slug: sage-50-tax-codes-and-nominal-code-settings
title: Sage 50 Tax code and Nominal Code Import Settings
---

Zynk supports reading the default Tax Codes and Nominal Codes from Sage 50, so these fields are not required within the Connect XML schema when importing Invoices, Sales Orders or Purchase Orders.

## Sales

### Item Tax Codes

Zynk will calculate the tax code for items in the following order:

  * ***If using Custom VAT Settings:***
  
    * If the Delivery Address is the same as the Company Address we use the UK Sales Tax Code
    * If the Delivery Address is in EU (as setup in Sage -> Settings -> Countries) we use the EU Sales Tax Code
    * Otherwise we use the RoW Sales Tax Code
    
 * ***By Default:***
             
    * Use Tax Code field from the XML source (if supplied)
    * Use Tax Code specified on the Sales Ledger Account - if option is checked to Override Tax Code in Invoicing)
    * Use Tax Code from the Stock Record
    * Use Tax Code from Settings -> Product Defaults
      
### Item Nominal Codes

Zynk will calculate the Nominal Code for items in the following order:

   * Use the NominalCode field as specified in the XML source if supplied
   * Use the Default Nominal Code from the Sales Ledger account (if the option is checked on the account to override Nominal Code in Invoicing)
   * Use the Sales Nominal Code from the Stock Record
   * Use the Sales Nominal Code from Settings -> Product Defaults
   
 ### Carriage Tax Codes
 
 Zynk will calculate the Tax Code for carriage in the follow order:
 
  * ***If using Custom VAT Settings:***
  
    * If the Delivery Address is the same as the Company Address we use the UK Carriage Code
    * If the Delivery Address is in EU (as setup in Sage -> Settings -> Countries) we use the EU Carriage Code
    * Otherwise we use the RoW Carriage Code
    
  * ***By default is not supplied in the XML:***
    
    * We will use the T1 code
    
### Carriage Nominal Codes

Zynk will calculate the Nominal Code for items in the following order:

  * Use the Nominal Code field as specified in the XML source (if supplied)
  * Use the Footer Sales Nominal Code from Settings -> Invoice and Order Defaults
  
## Purchase

### Item Tax Codes

Zynk will calculate the Tax Code for items in the following order:

* ***If using Custom VAT Settings:***
  
    * If the Delivery Address is the same as the Company Address we use the UK Purchase Tax Code
    * If the Delivery Address is in EU (as setup in Sage -> Settings -> Countries) we use the EU Purchase Tax Code
    * Otherwise we use the RoW Purchase Tax Code
          
 * ***By Default:***
             
    * Use Tax Code field from the XML source (if supplied)
    * Use Tax Code specified on the Purchase Ledger Account - if option is checked to Override Tax Code in Invoicing)
    * Use Tax Code from the Stock Record
    * Use Tax Code from Settings -> Product Defaults
      
### Item Nominal Codes

Zynk will calculate the Nominal Code for items in the following order:

   * Use the NominalCode field as specified in the XML source if supplied
   * Use the Default Nominal Code from the Purchase Ledger account (if the option is checked on the account to override Nominal Code in Invoicing)
   * Use the Sales Nominal Code from the Stock Record
   * Use the Sales Nominal Code from Settings -> Product Defaults
   
 ### Carriage Tax Codes
 
 Zynk will calculate the Tax Code for carriage in the follow order:
 
  * ***If using Custom VAT Settings:***
  
    * If the Delivery Address is the same as the Company Address we use the UK Carriage Code
    * If the Delivery Address is in EU (as setup in Sage -> Settings -> Countries) we use the EU Carriage Code
    * Otherwise we use the RoW Carriage Code
    
  * ***By default is not supplied in the XML:***
    
    * We will use the T1 code
    
### Carriage Nominal Codes

Zynk will calculate the Nominal Code for items in the following order:

  * Use the Nominal Code field as specified in the XML source (if supplied)
  * Use the Footer Purchase Nominal Code from Settings -> Invoice and Order Defaults
