---
slug: using-dashboards
redirect_from: "/article/649-using-dashboards"
title: Using Dashboards
---
There are several Dashboard connectors available in Zynk, which can be used to create a dashboard displaying key information from another system. For example, you could create a dashboard showing the total sales and invoices this month in Sage.

The dashboard is generated as a HTML file, which can be viewed via a web browser. An example is shown below.

![http://www.zynk.com/images/v2/dashboards/sage_50_dashboard.png](http://www.zynk.com/images/v2/dashboards/sage_50_dashboard.png)

## Supported Systems

We have dashboard connectors available for the following systems:
 * **Sage 50** - Includes a range of pre-defined values, and supports custom SQL queries.
 * **Sage 200** - Includes a range of pre-defined values, and supports custom SQL queries.
 * **Salesforce** - Includes a range of pre-defined values, and supports custom SOQL queries.
 * **SQL Databases** - Can connect to any SQL Server, ODBC or OLEDB database. All data must be export by custom SQL queries.
 * **XML** - Reads values from XML files, using custom XPath queries.

## Using the Generate Dashboard task 
To generate a dashboard, you need to use the 'Generate Dashboard' task from the appropriate connector (based on the system you are working with). The task has the following settings.

 * **Dashboard** - This is where you configure the values to display on the dashboard. See below for more details.
 * **Output File** - The HTML file the dashboard should be saved to.
 * **Connection** - In most cases, there is a Connection setting, which is where you specify the connection details for the system you are getting the values from. Choose an existing connection from the list, or create a new one if required.

## Configuring the Dashboard 
To configure the dashboard, click on the ellipsis (...) button on the 'Dashboard' setting. You will then see a window like the one below.

![http://www.zynk.com/images/v2/dashboards/dashboard_designer_2.png](http://www.zynk.com/images/v2/dashboards/dashboard_designer_2.png)

1. Enter a title for the dashboard. This will be displayed at the top of the dashboard.
2. Select either the light or dark style. This determines the background colour of the dashboard.
3. Click the add button to add a new element to the dashboard. They can be re-arranged if required by clicking and dragging.
4. Select a value to display on the dashboard from the drop down box. If you can't see the value you need, it is possible to use the 'Custom Query' option to write your own query which will return the required data. Please note this option may not be available for some systems.
5. Enter a title for the value. This will be set the to the value selected in 4. by default, but can be customised if required. 
6. Any additional settings will be displayed here. In most cases, you can enter a target value, which will cause a percentage above/below to be displayed next to the value on the dashboard. Repeat steps 3 - 6 to add more values to the dashboard. You can add up to a maximum of 16 values per dashboard.
7. Any unwanted values can be removed by clicking the cross.
8. Once you have finished configuring the dashboard, click the OK button.

## Creating a Dashboard with Multiple Pages

If you can't fit all the information you require into a single dashboard, or simply want to split the values into separate groups, you can create separate dashboards and use the Dashboard Loop task to automatically link them together.This will cause the separate dashboards to automatically cycle through when viewed.

The task doesn't have any settings which need to be configured. Just drag and drop the individual Generate Dashboard tasks into the Dashboard Loop task, as shown below.

![http://help.zynk.com/sc_assets/11749/dashboard_loop.png](http://help.zynk.com/sc_assets/11749/dashboard_loop.png)