---
slug: mappings
redirect_from: "/article/775-mappings"
title: Mappings
---
Mappings provide a simple way to handle cases where a field in the two systems you are integrating have values which don't match exactly. A mapping consists of pairs of corresponding values from two different systems. For example, this could be the names of shipping methods on an e-commerce website, with their corresponding SKU code in your accounts system.

You can access mappings by clicking the 'Mappings' button on the main toolbar. See below for details on how to create and manage mappings in Zynk.

Once a mapping has been created, it can be accessed within [XSLT Transform](xslt-transform) and [Auto Mapper](auto-mapper) using the `MapTo` and `MapFrom` functions. Please see the 'Extensions' section on [XSLT Transform](xslt-transform) for details of how to use the two functions.

[![](http://www.zynk.com/images/v2/mappings_manager.png)](http://www.zynk.com/images/v2/mappings_manager.png)

## Creating A New Mapping
To create a new connection, click the 'New' button on the toolbar. You will then see a window like the one below:

[![](http://www.zynk.com/images/v2/new_mapping.png)](http://www.zynk.com/images/v2/new_mapping.png)

1. Enter a name for the mapping. Note that each mapping must have a unique name.
2. Enter the pairs of corresponding values into the From and To columns. For example, if you were creating a mapping of shipping methods to SKU codes, you would enter the shipping method names into the 'From' column, and the corresponding SKUs into the To column.
3. Click the 'Ok' button to save the new mapping.

## Editing An Existing Mapping
To edit an existing mapping, select a mapping from the list, and click the 'Edit' button. The process for editing a mapping is the same as when creating a new mapping, so just follow the instructions above.

## Deleting A Mapping
To delete an existing mapping, select one or more mappings from the list, and click the 'Delete' button. You will see a message like the one below asking you to confirm the delete operation.

[![](http://www.zynk.com/images/v2/delete_mapping.png)](http://www.zynk.com/images/v2/delete_mapping.png)

Click 'Yes' to delete the mapping.

## Importing/Exporting Mappings
You can import and export mappings to and from files, this allows you to copy mappings from one PC to another. Please note that when importing mappings, it will overwrite any mappings which already exist.

**Export Connections**
1. Select one or more mappings from the list of mappings.
2. Click the 'Export' button.
3. Choose a file to export the mappings to, and click the 'Ok' button.

**Import Connections**
1. Click the 'Import' button.
2. Select the file containing the mappings to import.
3. Click the 'Ok' button.