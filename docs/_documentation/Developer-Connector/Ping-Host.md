---
slug: ping-host
redirect_from: "/article/202-ping-host"
title: Ping Host
---
This condition task will ping a URL, and run a series of sub-tasks depending on the result.

## Settings
### Equal To
_Required_  
Set to true to run the sub-tasks if the ping was successful, or set to false to run the sub-tasks if the ping failed.

### Host
_Required_  
The URL to ping.

### Timeout
_Required_  
The amount of time (in milliseconds) to wait for the host to respond.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Developer Connector](developer-connector) article.