---
slug: zip-search
redirect_from: "/article/758-zip-search"
title: Zip Search
---
![Zip Search Icon](/assets/images/search.ico)  
You can use the Zip Search extension to loop through a series of zip files to find a certain match.

Typically, a Zynk workflow will finish with an Archive Workflow Data task. This task is built to clean up all the files used in the integration run and move them into a zip folder in your directory of choice.

If you enter a workflow directory, an input and complete the other optional settings you can click search to loop through the archived zip files to look for your input. For example, if I was trying to find the archive for an order with the number #1000001 in my 'Main Workflow', I would select my Main Workflow from the Directory drop down and enter the order number into the input.

We created this tool so that when a customer enquires about a record or another issue, we can easily search through the archived files to see what happened.

Zip Search can be installed via Zynk's [Extensions Manager](extensions)

## Settings
### Workflow / Custom Directory
_Required_  
You are required to configure this setting to either a workflow you're investigating or a custom directory containing your archives. Please note, if you are using a custom data directory in Zynk you will need to use the 'Custom Directory' option.

### Input
_Required_  
The text you would like to search for in your .zip files. You can optionally specify multiple values by comma separating. E.g, 'OK,YES,NO'.

### Recursive
_Required_
This setting indicates whether the search should be carried in sub folders, or just the folder you have selected.

### Use Date Filter
_Required_
This setting indicates whether you'd like to filter your results by date. If you enable this setting, you wil also need to configure the two following date time settings:

* __From__ The date you would like your filter to start.
* __To__ The date you would like your filter to end.

### Exclude
_Optional_
You can optionally add values to exclude from your results, just select an operator (Equals, Contains, StartsWith and EndsWith) and enter your value after clicking the 'Add' button.

## Examples
Below is an example of using the 'Workflow' option using Zip Search. After clicking 'Search' after specifying the workflow archives I'm targeting and the input I'm looking for, you'll see the results list box populate with all .zip files containing the input.

[![](http://zynk.com/images/v2/zip_search/zip_search.PNG)](http://zynk.com/images/v2/zip_search/zip_search.PNG)

[![](http://zynk.com/images/v2/zip_search/zip_search_results.PNG)](http://zynk.com/images/v2/zip_search/zip_search_results.PNG)

Below is an example of using the 'Custom Directory' option.
[![](http://zynk.com/images/v2/zip_search/zip_search_manual_dir.PNG)](http://zynk.com/images/v2/zip_search/zip_search_manual_dir.PNG)
