---
slug: downloading-tax-rates-from-sage-one
redirect_from: "/article/886-download-tax-rates"
title: Downloading Tax Rates from Sage One
---
This task will download Tax Rates from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set to true to export all records from Sage One, or false to only export those updated since the date specified in the 'Export From' setting.

### Export From
_Required_  
The date to export new/modified records from. This setting only takes effect when 'Export All' is set to false. The date will update automatically each time the task runs.

### Output File
_Required_  
The file to save the downloaded records to.

### Items Per Page
_Required_  
The number records to fetch per request to Sage One. Increasing this value will reduce the number of requests needed to export the records, which may reduce the time taken.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <tax_rates>
    <tax_rate>
      <legacy_id>1</legacy_id>
      <id>GB_STANDARD</id>
      <displayed_as>Standard 20.00%</displayed_as>
      <path>/tax_rates/GB_STANDARD</path>
      <created_at>2013-07-03T10:38:09Z</created_at>
      <updated_at>2013-07-03T10:38:09Z</updated_at>
      <name>STANDARD</name>
      <percentage>20</percentage>
      <percentages>
        <percentage>
          <percentage>20</percentage>
          <from_date>1900-01-01T00:00:00</from_date>
          <to_date xsi:nil="true" />
        </percentage>
      </percentages>
      <is_visible>true</is_visible>
      <is_combined_rate>false</is_combined_rate>
      <editable>false</editable>
      <deletable>false</deletable>
    </tax_rate>
    <tax_rate>
      <legacy_id>2</legacy_id>
      <id>GB_LOWER</id>
      <displayed_as>Lower Rate 5.00%</displayed_as>
      <path>/tax_rates/GB_LOWER</path>
      <created_at>2013-07-03T10:38:09Z</created_at>
      <updated_at>2013-07-03T10:38:09Z</updated_at>
      <name>LOWER</name>
      <percentage>5</percentage>
      <percentages>
        <percentage>
          <percentage>5</percentage>
          <from_date>1900-01-01T00:00:00</from_date>
          <to_date xsi:nil="true" />
        </percentage>
      </percentages>
      <is_visible>true</is_visible>
      <is_combined_rate>false</is_combined_rate>
      <editable>false</editable>
      <deletable>false</deletable>
    </tax_rate>
    <tax_rate>
      <legacy_id>3</legacy_id>
      <id>GB_ZERO</id>
      <displayed_as>Zero Rated 0.00%</displayed_as>
      <path>/tax_rates/GB_ZERO</path>
      <created_at>2013-07-03T10:38:09Z</created_at>
      <updated_at>2013-07-03T10:38:09Z</updated_at>
      <name>ZERO</name>
      <percentage>0</percentage>
      <percentages>
        <percentage>
          <percentage>0</percentage>
          <from_date>1900-01-01T00:00:00</from_date>
          <to_date xsi:nil="true" />
        </percentage>
      </percentages>
      <is_visible>true</is_visible>
      <is_combined_rate>false</is_combined_rate>
      <editable>false</editable>
      <deletable>false</deletable>
    </tax_rate>
    <tax_rate>
      <legacy_id>4</legacy_id>
      <id>GB_EXEMPT</id>
      <displayed_as>Exempt 0.00%</displayed_as>
      <path>/tax_rates/GB_EXEMPT</path>
      <created_at>2013-07-03T10:38:10Z</created_at>
      <updated_at>2013-07-03T10:38:10Z</updated_at>
      <name>EXEMPT</name>
      <percentage>0</percentage>
      <percentages>
        <percentage>
          <percentage>0</percentage>
          <from_date>1900-01-01T00:00:00</from_date>
          <to_date xsi:nil="true" />
        </percentage>
      </percentages>
      <is_visible>true</is_visible>
      <is_combined_rate>false</is_combined_rate>
      <editable>false</editable>
      <deletable>false</deletable>
    </tax_rate>
    <tax_rate>
      <legacy_id>5</legacy_id>
      <id>GB_NO_TAX</id>
      <displayed_as>No VAT</displayed_as>
      <path>/tax_rates/GB_NO_TAX</path>
      <created_at>2013-07-03T10:38:10Z</created_at>
      <updated_at>2013-07-03T10:38:10Z</updated_at>
      <name>NO_TAX</name>
      <percentage>0</percentage>
      <percentages>
        <percentage>
          <percentage>0</percentage>
          <from_date>1900-01-01T00:00:00</from_date>
          <to_date xsi:nil="true" />
        </percentage>
      </percentages>
      <is_visible>true</is_visible>
      <is_combined_rate>false</is_combined_rate>
      <editable>false</editable>
      <deletable>false</deletable>
    </tax_rate>
  </tax_rates>
</sage_one_company>
```