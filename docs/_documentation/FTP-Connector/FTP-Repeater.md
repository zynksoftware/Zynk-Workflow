---
slug: ftp-repeater
redirect_from: "/article/251-ftp-repeater"
title: FTP Repeater
---
The FTP Repeater task will allow you to run a series of sub-tasks against all the files in the directory on the remote server.

## Settings
### FTP Connection
_Required_  
The FTP Connection to delete from. See the [Connecting to an FTP Server](connecting-to-an-ftp-server) article here if you require more information on how to create/manage connections.  

### Directory
_Required_  
Initial Directory to move to on FTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### List Recursively
_Required_  
Set to true to list files in sub-directories of the directory specified.

### Search Pattern
_Optional_  
The search pattern to use to filter the results returned. Supports both the `*` and `?` wildcards. For example, `*.xml` will only list files with the .xml extension.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The following variables are available to this task. To use these variables, reference them in templates as `@Context.Current["Name"]`, or within other task settings using the Razor option.

 * Name
 * Extension
 * NameWithoutExtension
 * Directory
 * Server

## Examples
You can find an example of how to use this task in the [FTP to Sage 50 Integration](ftp-to-sage-50-integration) article.