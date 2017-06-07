---
slug: sftp-repeater
redirect_from: "/article/305-sftp-repeater"
title: SFTP Repeater
---
The SFTP Repeater task will allow you to run a series of sub-tasks against files in a directory on the remote server.

## Settings
### Connection
_Required_  
The SFTP Connection to delete from.  See the [Connecting to an SFTP Server](connecting-to-an-sftp-server) if you require more information on how to create/manage connections.

### List Recursively
_Required_  
Set to true to list files in sub-directories of the directory specified.

### Search Pattern
_Optional_  
Specify a search pattern to filter the files listed e.g. `*.xml` would list all files with the xml extension

### Directory
_Required_  
The directory to move to on SFTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
The following variables are available to sub-tasks of this task. To use these variables, reference them in templates as `@Context.Current["Name"]` or within the task settings using the Razor option.

 * Name
 * Extension
 * NameWithoutExtension
 * FullName
 * Directory
 * Server

## Examples
You can find an example of how to use this task in the [SFTP to Sage 50 Integration](sftp-to-sage-50-integration) article.