---
slug: moving-workflows-between-computers
redirect_from: "/article/67-moving-workflows-between-computers"
title: Moving Workflows Between Computers
---
Zynk provides functions to import and export workflows and their data using a single workflow package file, which can easily be moved from one PC and another. For example, you may need to move a workflow when deploying an integration to a live environment.

The following data is included in a workflow package:
 * The workflow (.wkf) file,
 * All data contained in the workflow's working directory (and sub directories),
 * Any connections used by the tasks in the workflow,
 * Any XSL transform files used by Auto Mapper tasks in the workflow.

It does not include the following:

 * Any data files used by the workflow which aren't stored in the working directory,
 * The logs for the workflow as seen in the History tab,
 * Any truth table data as seen on the Data tab.

## Exporting A Workflow
To export a workflow, first find the workflow you want to export in the Workflows tab in Zynk. Right click on the workflow and click 'Export'. You will see a screen like the one shown below:

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b098189033603f7da36ff4/file-B0Fd0divYB.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b098189033603f7da36ff4/file-B0Fd0divYB.png)

1. Enter file to save the workflow package to, or use the Browse button to select this.
2. Click the Ok button to start the export.
3. Once the export is complete, a confirmation message will be displayed.

## Importing A Workflow
To import a workflow, first find the folder you want to add the workflow in the Workflows tab in Zynk. Right click on the folder and click 'Import'. You will see a screen like the one shown below:

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b098209033603f7da36ff5/file-9DoVk5Iciv.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b098209033603f7da36ff5/file-9DoVk5Iciv.png)

1. Enter the workflow package file, or use the Browse button to select it.
2. Click the Ok button to start the import. Please note that if a connection contained in the workflow package file already exists, it will be overwritten automatically without warning.
3. Once the import is complete, a confirmation message will be displayed.