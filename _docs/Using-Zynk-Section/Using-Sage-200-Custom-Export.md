---
slug: using-sage-200-custom-export
redirect_from: "/article/648-using-sage-200-custom-export"
title: Using Sage 200 Custom Export
---
This article will show you how to configure your own custom export from Sage 200. In this example, we demonstrate the process of filtering the results of an export and exporting additional fields which are not included in the standard export. We will use the Export Sales Orders task as an example in this tutorial, but the same principles apply across all the Sage 200 export tasks.

## Filtering the Export
As an example, we will filter the results of the Export Sales Orders task to only include orders where the total amount is greater than £100. Firstly, we need to check the field name in the Sage database. You can do this using SQL Server Management Studio.


1. Navigate to your Sage 200 database in the Object Explorer, and expand the 'Tables' folder.
2. Select the table where the data is stored, in the case of sales orders it is 'SOPOrderReturn', and expand the 'Columns' folder.
3. A list of the field names will be displayed. We can see that the total is stored in the 'TotalGrossValue' column.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb61029033607d708f33e5/file-hJbrX2sWLb.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb61029033607d708f33e5/file-hJbrX2sWLb.png)

4. In the Export Sales Orders task settings in Zynk, expand the 'Query Settings', and click the 'Where Clauses' setting.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb61819033607d708f33eb/file-JgJONlpkkx.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb61819033607d708f33eb/file-JgJONlpkkx.png)

5. Set the Comparison to 'GreaterThan', the Field Name to 'SOPOrderReturn.TotalGrossValue' and the Value to '100'.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb621d9033607d708f33f1/file-tVGtwI99I9.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb621d9033607d708f33f1/file-tVGtwI99I9.png)

6. Now when you run the workflow, the task will only export sales orders where the total amount is greater than 100.

## Including Additional Fields in the Export
As an example, we will include the Total Net, Total Tax and Total Gross fields in the orders returned by the Export Sales Orders task. Firstly, we need to check the field names in the Sage database. You can do this using SQL Server Management Studio.

1. Navigate to your Sage 200 database in the Object Explorer, and expand the 'Tables' folder.
2. Select the table where the data is stored, in the case of sales orders it is 'SOPOrderReturn', and expand the 'Columns' folder.
3. A list of the field names will be displayed. We can see that the data is stored in the 'TotalNetValue', 'TotalTaxValue', and 'TotalGrossValue' column.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb61029033607d708f33e5/file-hJbrX2sWLb.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb61029033607d708f33e5/file-hJbrX2sWLb.png)

4. In the Export Sales Orders task settings in Zynk, expand the 'Query Settings', and click the 'Columns' setting.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb638dc697917fdc55dbad/file-kCXTkyp72C.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb638dc697917fdc55dbad/file-kCXTkyp72C.png)

5. Enter the column names into the list.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09e869033603f7da3701b/file-FbYshVUdde.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09e869033603f7da3701b/file-FbYshVUdde.png)

6. Now when you run the workflow, the task will include these additional fields in the CustomFields collection in the output file.

![https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb6423c697917fdc55dbb6/file-kHboIbxrV5.png](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56bb6423c697917fdc55dbb6/file-kHboIbxrV5.png)