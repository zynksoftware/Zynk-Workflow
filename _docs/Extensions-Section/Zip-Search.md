---
slug: zip-search
redirect_from: "/article/758-zip-search"
title: Zip Search
---
![Zip Search Icon](/assets/images/search.ico)  
You can use the Zip Search program to find files that contain an Input or search term, like an order reference, or a customer account ID.

[![](http://zynk.com/images/v2/zip_search/zip_search.PNG)](http://zynk.com/images/v2/zip_search/zip_search.PNG)

Zip Search searches the contents of files in zip archives, like those created by the __Archive Workflow Data__ Task.

Zip Search was developed by Zynk, to quickly locate archived information, like

* _missing Sage 50 Sales Orders_ in fail files
* _downloaded XML data_ used by Zynk as an input

Zip Search can be installed via Zynk's [Extensions Manager](extensions)

## Settings
### Workflow / Custom Directory
_Required_  
Choose the Workflow directory containing your archives, from the dropdown list.
_Alternatively_ Select the 'Use manual directory' option to paste the folder path directory

### Input
_Required_  
Enter the Input you'd like to search for in your .zip files. 
Specify multiple values by comma separating. E.g, 'OK,YES,NO'.

### Recursive
_Required_
Enable to search in sub-folders.

### Use Date Filter
_Required_
Filter your results by date. If enabled, you also need to configure the following date-time settings:

* __From__ The date to filter _from_
* __To__ The end date to filter _to_.

### Exclude
_Optional_
Exclude values from results by selecting an operator (Equals, Contains, StartsWith and EndsWith) and entering a value to Exclude. Click __Add__ to add an Exclude filter.

## Examples
Below is an example of using the 'Workflow' option using Zip Search. After clicking 'Search' after specifying the workflow archives I'm targeting and the input I'm looking for, you'll see the results list box populate with all .zip files containing the input.

[![](http://zynk.com/images/v2/zip_search/zip_search_results.PNG)](http://zynk.com/images/v2/zip_search/zip_search_results.PNG)

Below is an example of using the 'Custom Directory' option.
[![](http://zynk.com/images/v2/zip_search/zip_search_manual_dir.PNG)](http://zynk.com/images/v2/zip_search/zip_search_manual_dir.PNG)
