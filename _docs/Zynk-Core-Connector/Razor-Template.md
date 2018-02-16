---
slug: razor-template
redirect_from: "/article/375-razor-template"
title: Razor Template
---
The Razor template uses the Microsoft Razor engine to render any text based output. You specify the Template File which is a Razor template containing text and variables, and an Output File which is the file you want to produce. You can also specify Template Variables which can be used within your template in the format of `@Context.Template["VariableName"]` which will then be converted when the task is run.

Please refer to Create a Razor Template in the Tutorials section.

## Settings
### Output File
_Required_  
The name of the file to be output after being processed through the Razor template engine.

### Prepend Timestamp
_Required_  
Set to true to add a timestamp to start of file name. Defaults to False. This setting is useful when using this task within a repeater task, as it will ensure the same file is not overwritten each time the task is ran.

### Referenced Assemblies
_Optional_  
The list of additional .NET assemblies to reference.

### Template File
_Required_  
The name of the file containing the Razor template to be used for processing.

### Template Variables
_Optional_  
The collection of user defined variables to be used in the template. They can be accessed in the template file using the 	`@Context.Template` variable collection. For example, you would access a variable called 'Forename' using `@Context.Template["Forename"]`.

### Timestamp Format
_Optional_  
The format for the timestamp. Only required if the 'Prepend Timestamp' setting is set to True. Defaults to `yyyyMMddHHmmssffff`.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample razor template file, which inserts values from the template variables collection into the body of an HTML email message:

```html
<html>
  <head>
    <Style>
      * { font-family:verdana; }
      body { font-size: 75%; }
      h1 { font-size: 175%; font-weight:normal; font-family: Trebuchet MS}
    </Style>
  </head>

  <body>
    <p>Hi @(Context.Template["Forename"]),</p>

    <p>We've created an account for you on our website, please log in using the username below and set your password.</p>

    <p>Username: @(Context.Template["Email_Address"])</p>

    <p>Regards,<br/>The Zynk Team</p>
  </body>
</html>
```
