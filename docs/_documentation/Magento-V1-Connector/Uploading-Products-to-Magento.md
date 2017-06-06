---
slug: uploading-products-to-magento
redirect_from: "/article/270-uploading-products-to-magento"
title: Uploading Products to Magento
---
 This task uploads product data to Magento, creating products which don't exist and updating those that already exist. The product inventory information is also updated on Magento if provided in the product data.

The input file should be in Magento XML format. If a product with matching sku is found in Magento, the existing product will be updated in Magento, otherwise a new product will be created.

## Settings
### Connection
_Required_  
The Magento connection to use. See the [Connecting to Magento](connecting-to-magento) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
An absolute or relative file path on the local computer or network to save Product records that fail to upload to Magento.  

See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works. 

Defaulted to `magento_upload_products_fail.xml` in the current working directory.

### Input File
_Required_  
The absolute or relative file path to the XML file containing the Magento Products to import.  
This can also be inline XML, e.g. by generating the data using a razor script or by providing a URI to a script generating the data and specifying 'Read contents of file'.  

See the  Zynk Objects article if you require more information on how the Zynk Object file value works.

Defaulted to Output from the previous task 

### Success File
_Required_  
An absolute or relative file path on the local computer or network to save Product records that are successfully uploaded to Magento.  

See the  Zynk Objects article if you require more information on how the Zynk Object file value works.

Defaulted to `magento_upload_products_success.xml` in the current working directory. 

### Prevent Reprocessing
_Required_  
Set to true if you would only like to upload each Product to Magento the first time it is processed by Zynk.

This setting relies on the `<external_id>` element being provided in the Product XML data.

Defaulted to False.

### Upload Categories - Case Sensitive Category
_Required_  
Set to true if you would like to perform a case sensitive match when uploading Categories.

__Upload Categories - Enabled__ must be set to true for the Upload Categories functionality to be enabled.

Defaulted to False.

### Upload Categories - Category Field Name
_Required_  
The Name of the Field(s) in the Product data that contain the Category structures to upload.

__Upload Categories - Enabled__ must be set to true for the Upload Categories functionality to be enabled.

Defaulted to `category_structure`.    

```xml
<Fields> <br> <Field Name="category_structure" Value="Category Name" /><br> </Fields>
```

### Upload Categories - Category Field Separator
_Required_  
The separator character used between Categories to infer the Category nesting.

__Upload Categories - Enabled__ must be set to true for the Upload Categories functionality to be enabled. 

Defaulted to `;`.

```xml
<Fields><br> <Field Name="category_structure" Value="Category Top Level;Category Sub Level" /><br></Fields>
```

### Upload Categories - Create Categories - Enabled
_Required_  
Set to true if you would like to automatically create Categories on Magento that are provided in the Product data but do not exist yet on Magento.

__Upload Categories - Enabled__ must be set to true for the Upload Categories functionality to be enabled.

Defaulted to False.

### Upload Categories - Create Categories - New Category Available Sort By Value
_Required_  
The `<available_sort_by>` value to use for automatically created Categories.

__Upload Categories - Enabled__ and __Upload Categories - Create Categories - Enabled__ must be set to true for the Create Categories functionality to be enabled.

Defaulted to position, name, sku, price.

### Upload Categories - Create Categories - New Category Default Sort By Value
_Required_  
The `<default_sort_by>` value to use for automatically created Categories. 

__Upload Categories - Enabled__ and __Upload Categories - Create Categories - Enabled__ must be set to true for the Create Categories functionality to be enabled.

Defaulted to price.

### Upload Categories - Create Categories - Include In Menu Value
_Required_  
The `<include_in_menu>` value to use for automatically created Categories. 

__Upload Categories - Enabled__ and __Upload Categories - Create Categories - Enabled__ must be set to true for the Create Categories functionality to be enabled.

Defaulted to True.

### Upload Categories - Create Categories - Is Active Value
_Required_  
The `<is_active>` value to use for automatically created Categories. 

__Upload Categories - Enabled__ and __Upload Categories - Create Categories - Enabled__ must be set to true for the Create Categories functionality to be enabled.

Defaulted to True.

### Upload Categories - Enabled
_Required_  
Set to true if you would like to lookup Categories on Magento based on Field(s) that are provided in the Product data. 

Defaulted to True.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0"?>
<ArrayOfProduct>
  <Product>
    <type>simple</type>
    <status>1</status>
    <options_container>container2</options_container>
    <category_ids />
    <description>test</description>
    <visibility>4</visibility>
    <short_description>test</short_description>
    <required_options>0</required_options>
    <websites>
      <string>1</string>
    </websites>
    <tax_class_id>2</tax_class_id>
    <type_id>simple</type_id>
    <set>4</set>
    <categories />
    <sku>PROD001</sku>
    <name>test</name>
    <weight>2.0000</weight>
    <price>10.0000</price>
    <group_price />
  </Product>
</ArrayOfProduct>
```