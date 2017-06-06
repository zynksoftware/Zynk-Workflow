---
slug: exporting-a-file-list-on-amazon-s3
redirect_from: "/article/155-listing-files-on-amazon-s3"
title: Exporting a File List on Amazon S3
---


This task will provide a list of files in XML format from a specified bucket.


## Settings

### Bucket 
_Required_
The name of the storage bucket to list files from.

### Connection
_Required_
The Amazon S3 Connection to use.

### Folder 
_Optional_
The folder to list files in. Leave blank to list all files in the selected bucket.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


Sample output file showing the file 'customers.xml':

```xml
<?xml version="1.0" encoding="utf-8"?>
    <ArrayOfListEntry>
    <ListEntry>
    	<Name>customers.xml</Name>
    	<ETag>"91216dfc27fd460e8ac86ac4f27ed029"</ETag>
    	<LastModified>2015-05-21T09:02:07</LastModified>
    	<Owner>
    		<Id>2ec66d54fb6dcf0819b44f515e43a0604b55872a11b399648f36aba0d98bb5e0</Id>
    		<DisplayName>zynksoftware</DisplayName>
    	</Owner>
    	<Size>835</Size>
    	<StorageClass>
    		<Value>STANDARD</Value>
    	</StorageClass>
    </ListEntry>
    </ArrayOfListEntry>
```