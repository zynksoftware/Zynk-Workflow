---
slug: using-sage-50-custom-exports
redirect_from: "/article/634-using-sage-50-custom-exports"
title: Using Sage 50 Custom Exports
---
This article will outline some basic functions of the Sage 50 Export Query task. In this process, I'll go through the process of using the helper settings and also the custom query setting. For this example, I'm going to export printed sales orders from Sage 50.

Firstly, you'll need to select an Export Query task from the Sage 50 UK folder in the task library. Once you have done so, you will see the following settings appear on the right hand side of the user interface.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56a24755c69791436156195b/file-SdTAFMEeab.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56a24755c69791436156195b/file-SdTAFMEeab.png)

I am selecting the ORDER_NUMBER and PRINTED columns from the Sage 50 database, which are located on the SALES_ORDER table. My export will only contain records with a printed flag of 'Y' as this means they have been printed. The following will be in your resulting export file:

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row ORDER_NUMBER="1014" PRINTED="Y" />
  <Row ORDER_NUMBER="1016" PRINTED="Y" />
  <Row ORDER_NUMBER="1018" PRINTED="Y" />
  <Row ORDER_NUMBER="1076" PRINTED="Y" />
  <Row ORDER_NUMBER="1077" PRINTED="Y" />
  <Row ORDER_NUMBER="1078" PRINTED="Y" />
</Rows>
```

For the custom query example, I am going to export inactive products from the Sage 50 database. Firstly, I am going to drop another Export Query task into my workflow and edit the Custom Query setting shown above.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56a24decc697914361561998/file-wro8mycGUF.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56a24decc697914361561998/file-wro8mycGUF.png)

Once my query has ran, the following will be output:

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row STOCK_CODE="CALC001" INACTIVE_FLAG="1" />
  <Row STOCK_CODE="CALC002" INACTIVE_FLAG="1" />
  <Row STOCK_CODE="CALC003" INACTIVE_FLAG="1" />
</Rows>
```