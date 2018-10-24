---
slug: export-categories-from-my-mobile-workers
title: Export Categories from My Mobile Workers
---
The My Mobile Workers platform will allow their users to categories items based on their type. For example, a pipe would be placed in a 'Drainage' category or guttering would be placed in a 'Rainwater' category.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Get_Categories).

This task will export all available categories from My Mobile Workers in an XML format.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Categories>
    <Category>
      <name>Demo Repair Items</name>
      <Response />
    </Category>
    <Category>
      <external_id>1</external_id>
      <name>Test</name>
      <Response />
    </Category>
    <Category>
      <external_id>2</external_id>
      <name>Test 2</name>
      <Response />
    </Category>
    <Category>
      <external_id>1</external_id>
      <name>Paper Products</name>
      <Response />
    </Category>
    <Category>
      <external_id>2</external_id>
      <name>Office Supplies</name>
      <Response />
    </Category>
    <Category>
      <external_id>3</external_id>
      <name>Envelopes and Mailing</name>
      <Response />
    </Category>
    <Category>
      <external_id>4</external_id>
      <name>Writing Equipment</name>
      <Response />
    </Category>
    <Category>
      <external_id>5</external_id>
      <name>Organising and Filing</name>
      <Response />
    </Category>
    <Category>
      <external_id>6</external_id>
      <name>Presentation Supplies</name>
      <Response />
    </Category>
    <Category>
      <external_id>7</external_id>
      <name>Business Machines</name>
      <Response />
    </Category>
    <Category>
      <external_id>8</external_id>
      <name>Computer Accessories</name>
      <Response />
    </Category>
    <Category>
      <external_id>9</external_id>
      <name>Telecomunications</name>
      <Response />
    </Category>
    <Category>
      <external_id>10</external_id>
      <name>Computer Hardware</name>
      <Response />
    </Category>
    <Category>
      <external_id>abc</external_id>
      <name>Products</name>
      <Response />
    </Category>
  </Categories>
</MyMobileWorkersData>
```
