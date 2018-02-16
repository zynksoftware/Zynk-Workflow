---
slug: auto-generate-references
redirect_from: "/article/60-auto-generate-references"
title: Auto Generate References
---
The following settings are used to control how new account references are generated for customers or suppliers imported into Sage. Whenever an account reference is generated, it will be stored in the truth table along with the Id (if provided in the input file) of the customer or supplier. If the same customer or supplier is imported in future, Zynk will look up the previously generated account reference in the truth table based on the Id, and use that instead of generating another.

## Settings
### Account Reference Convention
_Required_  
Select a method for generating the alphabetic part of the account reference. The following options are available:	
 * **CompanyOtherwiseFullName** - The company name will be used if provided, otherwise the customers full name.
 * **CompanyOtherwiseForenameSurname** - The company name will be used if provided, otherwise the customers forename followed by surname.
 * **CompanyOtherwiseSurnameForename** - The company name will be used if provided, otherwise the customers surname followed by forename.
 * **ForenameSurname** - The customers forename followed by surname.
 * **SurnameForename** - The customers surname followed by forename.

### Alphabetic Length
_Required_  
Used with auto-generated Account Ref - specified the number of alphabetic characters to use e.g. 3 = `ABC`

### Numeric Length
_Required_  
Used with auto-generated Account Ref - specified the number of numeric characters to use e.g. 3 = `001`

### Auto generate Account References
_Required_  
Set this to True to have the task auto generate account references where an account reference is not provided in the input file. Set to False if an account reference generation is not required.

### Mask
_Optional_  
A mask to apply to the auto generated account references. This can be used to add prefixes or suffixes to the account references. Question marks are replaced by auto generated characters, as determined by the Alphabetic Length and Numeric Length settings, any other characters will be included in the generated account reference. For example, the mask `A??????` would ensure that the account references always start with the letter A

### Regular Expression
_Optional_  
The regular expression to use for stripping out undesired characters from the generated account reference. Any character which matches the regular expression will be removed. For example, `\s*` would be used to strip out all spaces.