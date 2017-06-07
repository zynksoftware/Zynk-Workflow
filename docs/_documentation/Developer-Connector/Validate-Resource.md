---
slug: validate-resource
redirect_from: "/article/203-validate-resource"
title: Validate Resource
---
You can validate a URL with Zynk using the validate resource task. You can use any online validator, however our default is[http://validator.w3.org/check](http://validator.w3.org/check).

## Settings
### Output File
_Required_  
The HTML response from validation will be written to this file.

### URL
_Required_  
The URL you are validating, e.g http://validator.w3.org/

### Validation URL
_Required_  
The validation checker you are using, e.g http://validator.w3.org/check

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Developer Connector](developer-connector) article.

To validate[http://validator.w3.org/](http://validator.w3.org/), follow the steps below:

1. Set your URL to [http://validator.w3.org/](http://validator.w3.org/)
2. Set your Validation URL to [http://validator.w3.org/check](http://validator.w3.org/check)
3. Configure your output file, e.g response.html
4. Run workflow!