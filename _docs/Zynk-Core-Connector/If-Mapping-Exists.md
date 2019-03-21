---
slug: if-mapping-exists
title: If Mapping Exists
---
This task will check whether a mapping entry exists in Zynk's mappings file, and run a series of sub-tasks depending on the result.

Fore more detailed information on mappings please visit the [Mappings](mappings) page.

## Settings
### Mapping Name
_Required_  
The name of the mapping entry you are checking.

### Mapping Direction
_Required_
The value in the mapping entry you want to check, either From or To.

### Exact Match
_Required_
Set to true you want to match your input exactly to the value in the mapping entry. Set to false and the task will check if the mapping entry value contains your input value.

### Contains Match Direction
_Required_
Choose MappingContainsValue to find the first match where the mapping contains the value, and ValueContainsMapping to find the first match where the mapping is found in the value.

### Match Value
_Required_
Your input value that will be checked in the mapping entry you have chosen.