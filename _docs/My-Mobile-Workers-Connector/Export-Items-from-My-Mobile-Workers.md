---
slug: export-items-from-my-mobile-workers
title: Export Items from My Mobile Workers
---
The My Mobile Workers platform will allow their users to create items that trades people will to use to create jobs. For example, if you were a plumber you would have various items for pipes, wrenches and other equipment used.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Get_All_Items).

This task will export all available items from My Mobile Workers in an XML format.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

## XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Items>
    <Item>
      <external_id />
      <name>MTCU-19 Soft-Close Toilet Seat White </name>
      <category>
        <name>Demo Repair Items</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes />
      <price>17.9</price>
      <product_code>PB123</product_code>
      <Response />
    </Item>
    <Item>
      <name>MK 1-Gang 2-Way 10AX Switch White</name>
      <category>
        <name>Demo Repair Items</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes />
      <price>1.33</price>
      <product_code>CN/44FF</product_code>
      <Response />
    </Item>
    <Item>
      <name>Manrose MF100 W 100mm Fan</name>
      <category>
        <name>Demo Repair Items</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes />
      <price>69.99</price>
      <product_code>CN/44FE</product_code>
      <Response />
    </Item>
    <Item>
      <external_id />
      <name>Labour</name>
      <category>
        <name>Demo Repair Items</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes />
      <price>50</price>
      <product_code>lab</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>TEST</external_id>
      <name>test aw</name>
      <category>
        <external_id>1</external_id>
        <name>Test</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>test aw</notes>
      <price>0.01</price>
      <product_code>TEST</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>0</external_id>
      <name>Test Product.</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Test Product.</notes>
      <product_code>AAAA01</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>175.99</external_id>
      <name>AB Built-In Cookers Single-Oven/300mm/White.</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>AB Built-In Cookers Single-Oven/300mm/White.</notes>
      <product_code>ABBUILTIN/15/0/2</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>20</external_id>
      <name>Whiteboard - Drywipe (900 x 1200)</name>
      <category>
        <external_id>6</external_id>
        <name>Presentation Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Whiteboard - Drywipe (900 x 1200)</notes>
      <product_code>BOARD001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>22</external_id>
      <name>Whiteboard - Drywipe (1000 x 1500)</name>
      <category>
        <external_id>6</external_id>
        <name>Presentation Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Whiteboard - Drywipe (1000 x 1500)</notes>
      <product_code>BOARD002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>7.99</external_id>
      <name>A4 Ledger Book - 5 Column</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>A4 Ledger Book - 5 Column</notes>
      <product_code>BOOKS001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.99</external_id>
      <name>A4 Carbon Copy Book - Triplicate</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>A4 Carbon Copy Book - Triplicate</notes>
      <product_code>BOOKS002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>4.5</external_id>
      <name>Shorthand Notebook - 80 Sheets</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Shorthand Notebook - 80 Sheets</notes>
      <product_code>BOOKS003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>0</external_id>
      <name>Child Product</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Child Product</notes>
      <product_code>C-AA03550-H</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>10</external_id>
      <name>Calculator - Desktop</name>
      <category>
        <external_id>7</external_id>
        <name>Business Machines</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Calculator - Desktop</notes>
      <product_code>CALC001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>6</external_id>
      <name>Calculator - Pocket</name>
      <category>
        <external_id>7</external_id>
        <name>Business Machines</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Calculator - Pocket</notes>
      <product_code>CALC002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>17</external_id>
      <name>Calculator - Desktop (Printing)</name>
      <category>
        <external_id>7</external_id>
        <name>Business Machines</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Calculator - Desktop (Printing)</notes>
      <product_code>CALC003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>6</external_id>
      <name>Calculator - Printing Rolls</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Calculator - Printing Rolls</notes>
      <product_code>CALC004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>15</external_id>
      <name>AT Mini Tower Case</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>AT Mini Tower Case</notes>
      <product_code>CAS001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>20</external_id>
      <name>ATX Mini Tower Case</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>ATX Mini Tower Case</notes>
      <product_code>CAS002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>30</external_id>
      <name>ATX Desktop Case</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>ATX Desktop Case</notes>
      <product_code>CAS003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2</external_id>
      <name>CCTEST</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>CCTEST</notes>
      <product_code>CCTEST</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>154</external_id>
      <name>CDR08432 Read/Write CD Drive</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>CDR08432 Read/Write CD Drive</notes>
      <product_code>CDR001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>190</external_id>
      <name>CDR10432 Read/Write CD Drive</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>CDR10432 Read/Write CD Drive</notes>
      <product_code>CDR002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>223</external_id>
      <name>CDR12432 Read/Write CD Drive</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>CDR12432 Read/Write CD Drive</notes>
      <product_code>CDR003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.5</external_id>
      <name>Correction Fluid - White</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Correction Fluid - White</notes>
      <product_code>COR001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3</external_id>
      <name>Diskettes - Formatted (1.44MB)</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Diskettes - Formatted (1.44MB)</notes>
      <product_code>DISK001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>8</external_id>
      <name>Disk - CDR (640MB)</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Disk - CDR (640MB)</notes>
      <product_code>DISK002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>8.99</external_id>
      <name>Envelope - White (110 x 220) Plain</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Envelope - White (110 x 220) Plain</notes>
      <product_code>ENV001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>9.5</external_id>
      <name>Envelope - White (110 x 220) Window</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Envelope - White (110 x 220) Window</notes>
      <product_code>ENV002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>7.5</external_id>
      <name>Envelope - Brown (110 x 220) Plain</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Envelope - Brown (110 x 220) Plain</notes>
      <product_code>ENV003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>8.5</external_id>
      <name>Envelope - Brown (110 x 220) Window</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Envelope - Brown (110 x 220) Window</notes>
      <product_code>ENV004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>180</external_id>
      <name>FX010 Plain Paper Fax..</name>
      <category>
        <external_id>9</external_id>
        <name>Telecomunications</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>FX010 Plain Paper Fax..</notes>
      <product_code>FAX001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>400</external_id>
      <name>FX020 Multifunctional Fax.</name>
      <category>
        <external_id>9</external_id>
        <name>Telecomunications</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>FX020 Multifunctional Fax.</notes>
      <product_code>FAX002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>460</external_id>
      <name>FX030 Multifunctional Fax.</name>
      <category>
        <external_id>9</external_id>
        <name>Telecomunications</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>FX030 Multifunctional Fax.</notes>
      <product_code>FAX003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>45</external_id>
      <name>Filing Cabinet - 3 Drawer</name>
      <category>
        <external_id>5</external_id>
        <name>Organising and Filing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Filing Cabinet - 3 Drawer</notes>
      <product_code>FIL001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>65</external_id>
      <name>Filing Cabinet - 5 Drawer</name>
      <category>
        <external_id>5</external_id>
        <name>Organising and Filing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Filing Cabinet - 5 Drawer</notes>
      <product_code>FIL002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>16</external_id>
      <name>Flip Chart - A1 Pad</name>
      <category>
        <external_id>6</external_id>
        <name>Presentation Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Flip Chart - A1 Pad</notes>
      <product_code>FLIP001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>16</external_id>
      <name>Flip Chart - A1 Pad (Recycled)</name>
      <category>
        <external_id>6</external_id>
        <name>Presentation Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Flip Chart - A1 Pad (Recycled)</notes>
      <product_code>FLIP002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>50</external_id>
      <name>10gb Hard Drive</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>10gb Hard Drive</notes>
      <product_code>HAR001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>75</external_id>
      <name>20gb Hard Drive</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>20gb Hard Drive</notes>
      <product_code>HAR002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>90</external_id>
      <name>30gb Hard Drive</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>30gb Hard Drive</notes>
      <product_code>HAR003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>50</external_id>
      <name>Installation</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Installation</notes>
      <product_code>INST001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>20</external_id>
      <name>Standard Keyboard</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Standard Keyboard</notes>
      <product_code>KEY001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>4.25</external_id>
      <name>A4 Labels (68x99) - Inkjet</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>A4 Labels (68x99) - Inkjet</notes>
      <product_code>LABELS001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>4.25</external_id>
      <name>A4 Labels (38x99) - Inkjet</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>A4 Labels (38x99) - Inkjet</notes>
      <product_code>LABELS002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>75</external_id>
      <name>Laminator - A4</name>
      <category>
        <external_id>7</external_id>
        <name>Business Machines</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Laminator - A4</notes>
      <product_code>LAM001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>12</external_id>
      <name>Laminator Pouches - A4</name>
      <category>
        <external_id>6</external_id>
        <name>Presentation Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Laminator Pouches - A4</notes>
      <product_code>LAM002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>15</external_id>
      <name>Mailing Bag - Bubble Lined</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Mailing Bag - Bubble Lined</notes>
      <product_code>MAIL001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>30</external_id>
      <name>DIMM 32mb 100Mhz</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>DIMM 32mb 100Mhz</notes>
      <product_code>MEM001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>58</external_id>
      <name>DIMM 64mb 100Mhz</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>DIMM 64mb 100Mhz</notes>
      <product_code>MEM002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>100</external_id>
      <name>DIMM 128mb 100Mhz</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>DIMM 128mb 100Mhz</notes>
      <product_code>MEM003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>30</external_id>
      <name>SIMM 16mb 100Mhz</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>SIMM 16mb 100Mhz</notes>
      <product_code>MEM004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>50</external_id>
      <name>SIMM 32mb 100Mhz</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>SIMM 32mb 100Mhz</notes>
      <product_code>MEM005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>80</external_id>
      <name>SIMM 64mb 100Mhz</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>SIMM 64mb 100Mhz</notes>
      <product_code>MEM006</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>50</external_id>
      <name>MTH1000 Motherboard</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>MTH1000 Motherboard</notes>
      <product_code>MOTH001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>60</external_id>
      <name>MTH2000 Motherboard</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>MTH2000 Motherboard</notes>
      <product_code>MOTH002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>70</external_id>
      <name>MTH3000 Motherboard</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>MTH3000 Motherboard</notes>
      <product_code>MOTH003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1.5</external_id>
      <name>Mouse Mat - (241 x 203) Red</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Mouse Mat - (241 x 203) Red</notes>
      <product_code>MOUSE001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1.5</external_id>
      <name>Mouse Mat - (241 x 203) Blue</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Mouse Mat - (241 x 203) Blue</notes>
      <product_code>MOUSE002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1.5</external_id>
      <name>Mouse Mat - (241 x 203) Black</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Mouse Mat - (241 x 203) Black</notes>
      <product_code>MOUSE003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>15</external_id>
      <name>Dual Wheel Mouse</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Dual Wheel Mouse</notes>
      <product_code>MOUSE004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>400</external_id>
      <name>Orange Amplifier</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Orange Amplifier</notes>
      <product_code>ORANGE</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.59</external_id>
      <name>Copy Paper - Economy Grade</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Copy Paper - Economy Grade</notes>
      <product_code>PAPER001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.89</external_id>
      <name>Copy Paper - Standard Grade</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Copy Paper - Standard Grade</notes>
      <product_code>PAPER002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3.4</external_id>
      <name>Copy Paper - Premium Grade</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Copy Paper - Premium Grade</notes>
      <product_code>PAPER003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>4.99</external_id>
      <name>Inkjet Paper - Premium Grade</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Inkjet Paper - Premium Grade</notes>
      <product_code>PAPER004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.45</external_id>
      <name>Lasercopy Paper - Standard Grade</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Lasercopy Paper - Standard Grade</notes>
      <product_code>PAPER005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3.8</external_id>
      <name>Coloured Paper - Pastel Blue</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Coloured Paper - Pastel Blue</notes>
      <product_code>PAPER006</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3.8</external_id>
      <name>Coloured Paper - Pastel Green</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Coloured Paper - Pastel Green</notes>
      <product_code>PAPER007</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>14.92</external_id>
      <name>pb123</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>pb123</notes>
      <product_code>PB123</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>550</external_id>
      <name>PC Combo Pack 1</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PC Combo Pack 1</notes>
      <product_code>PC001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>650</external_id>
      <name>PC Combo Pack 2</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PC Combo Pack 2</notes>
      <product_code>PC002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>750</external_id>
      <name>PC Combo Pack 3</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PC Combo Pack 3</notes>
      <product_code>PC003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>850</external_id>
      <name>PC Combo Pack 4</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PC Combo Pack 4</notes>
      <product_code>PC004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1200</external_id>
      <name>PC Combo Pack 5</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PC Combo Pack 5</notes>
      <product_code>PC005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1500</external_id>
      <name>PC Combo Pack 6</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PC Combo Pack 6</notes>
      <product_code>PC006</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2</external_id>
      <name>Ball Point Pen - Black</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Ball Point Pen - Black</notes>
      <product_code>PEN001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2</external_id>
      <name>Ball Point Pen - Blue</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Ball Point Pen - Blue</notes>
      <product_code>PEN002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2</external_id>
      <name>Ball Point Pen - Red</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Ball Point Pen - Red</notes>
      <product_code>PEN003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.5</external_id>
      <name>Pencil - HB</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Pencil - HB</notes>
      <product_code>PEN004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.5</external_id>
      <name>Pencil - H</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Pencil - H</notes>
      <product_code>PEN005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>4.8</external_id>
      <name>Pencil - Chinagraph Black</name>
      <category>
        <external_id>4</external_id>
        <name>Writing Equipment</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Pencil - Chinagraph Black</notes>
      <product_code>PEN006</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>80</external_id>
      <name>PCR600 Processor</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PCR600 Processor</notes>
      <product_code>PRC001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>130</external_id>
      <name>PCR650 Processor</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PCR650 Processor</notes>
      <product_code>PRC002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>200</external_id>
      <name>PCR700 Processor</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PCR700 Processor</notes>
      <product_code>PRC003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>300</external_id>
      <name>PCR800 Processor</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PCR800 Processor</notes>
      <product_code>PRC004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>400</external_id>
      <name>PCR900 Processor</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PCR900 Processor</notes>
      <product_code>PRC005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>240</external_id>
      <name>LP100 Laser Printer</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>LP100 Laser Printer</notes>
      <product_code>PRN001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1200</external_id>
      <name>LP200 Laser Printer</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>LP200 Laser Printer</notes>
      <product_code>PRN002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>70</external_id>
      <name>JP010 Jet Printer</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>JP010 Jet Printer</notes>
      <product_code>PRN003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>180</external_id>
      <name>JP020 Jet Printer</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>JP020 Jet Printer</notes>
      <product_code>PRN004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>190</external_id>
      <name>JP030 Jet Printer</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>JP030 Jet Printer</notes>
      <product_code>PRN005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>20.83</external_id>
      <name>PUSH Ultra Low Friction Fork Seal Kits PUSH 32mm</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>PUSH Ultra Low Friction Fork Seal Kits PUSH 32mm</notes>
      <product_code>PUPFS32</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>100</external_id>
      <name>Example Product w/ Qty Breaks</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Example Product w/ Qty Breaks</notes>
      <product_code>QTYBREAK</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3</external_id>
      <name>Remember-Me Sticky Notes</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Remember-Me Sticky Notes</notes>
      <product_code>REMEMBER01</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3.5</external_id>
      <name>Remember-Me Sticky Notes (Recycled)</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Remember-Me Sticky Notes (Recycled)</notes>
      <product_code>REMEMBER02</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>7.99</external_id>
      <name>Remember-Me Memo Pads</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Remember-Me Memo Pads</notes>
      <product_code>REMEMBER03</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>6</external_id>
      <name>Rubber Bands - Selection Pack (200)</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Rubber Bands - Selection Pack (200)</notes>
      <product_code>RUB001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>0</external_id>
      <name>Parent Product</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Parent Product</notes>
      <product_code>S-AA03550-G</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>3</external_id>
      <name>Scissors - Economy</name>
      <category>
        <external_id>2</external_id>
        <name>Office Supplies</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Scissors - Economy</notes>
      <product_code>SCI001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>86</external_id>
      <name>SCAN1000 Scanner</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>SCAN1000 Scanner</notes>
      <product_code>SCN001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>189</external_id>
      <name>SCAN2000 Scanner</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>SCAN2000 Scanner</notes>
      <product_code>SCN002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.5</external_id>
      <name>Adhesive Tape - Brown (48mm x 60m)</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Adhesive Tape - Brown (48mm x 60m)</notes>
      <product_code>TAPE001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>2.8</external_id>
      <name>Adhesive Tape - Brown (50mm x 66m)</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Adhesive Tape - Brown (50mm x 66m)</notes>
      <product_code>TAPE002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>0.65</external_id>
      <name>Adhesive Tape - Clear (19mm x 33m)</name>
      <category>
        <external_id>3</external_id>
        <name>Envelopes and Mailing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Adhesive Tape - Clear (19mm x 33m)</notes>
      <product_code>TAPE003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>12.5</external_id>
      <name>Heavy Duty Mount Kit 12.7mm M8 8x40</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Heavy Duty Mount Kit 12.7mm M8 8x40</notes>
      <product_code>TF840</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>16.67</external_id>
      <name>Custom Heavy Duty Mount Kit 12.7mm</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Custom Heavy Duty Mount Kit 12.7mm</notes>
      <product_code>TFCUSTOM</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>12.5</external_id>
      <name>Heavy Duty Mount Kit 12mm M6 6x45.6</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Heavy Duty Mount Kit 12mm M6 6x45.6</notes>
      <product_code>TM6456</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>10</external_id>
      <name>LP100 Laser Printer Toner</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>LP100 Laser Printer Toner</notes>
      <product_code>TR001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>6</external_id>
      <name>LP200 Laser Printer Toner</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>LP200 Laser Printer Toner</notes>
      <product_code>TR002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>18</external_id>
      <name>JP010 Jet Printer Cartridge</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>JP010 Jet Printer Cartridge</notes>
      <product_code>TR003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>15</external_id>
      <name>JP020 Jet Printer Cartridge</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>JP020 Jet Printer Cartridge</notes>
      <product_code>TR004</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>14</external_id>
      <name>JP030 Jet Printer Cartridge</name>
      <category>
        <external_id>8</external_id>
        <name>Computer Accessories</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>JP030 Jet Printer Cartridge</notes>
      <product_code>TR005</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>7</external_id>
      <name>Letter Trays - 3 pack (Black)</name>
      <category>
        <external_id>5</external_id>
        <name>Organising and Filing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Letter Trays - 3 pack (Black)</notes>
      <product_code>TRAY001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>7</external_id>
      <name>Letter Trays - 3 pack (Pink/Brown)</name>
      <category>
        <external_id>5</external_id>
        <name>Organising and Filing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Letter Trays - 3 pack (Pink/Brown)</notes>
      <product_code>TRAY002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>7</external_id>
      <name>Letter Trays - 3 pack (Grey)</name>
      <category>
        <external_id>5</external_id>
        <name>Organising and Filing</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>Letter Trays - 3 pack (Grey)</notes>
      <product_code>TRAY003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>34</external_id>
      <name>8mb PCI Video Card</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>8mb PCI Video Card</notes>
      <product_code>VID001</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>44</external_id>
      <name>16mb PCI Video Card</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>16mb PCI Video Card</notes>
      <product_code>VID002</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>55</external_id>
      <name>32mb PCI Video Card</name>
      <category>
        <external_id>10</external_id>
        <name>Computer Hardware</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>32mb PCI Video Card</notes>
      <product_code>VID003</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>1234</external_id>
      <name>1234</name>
      <category>
        <external_id>abc</external_id>
        <name>Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>1234</notes>
      <price>1</price>
      <product_code>1234</product_code>
      <Response />
    </Item>
    <Item>
      <external_id>WEST2</external_id>
      <name>255/55R18V Westlake</name>
      <category>
        <external_id>1</external_id>
        <name>Paper Products</name>
        <Response />
      </category>
      <category_id>
        <Response />
      </category_id>
      <notes>255/55R18V Westlake</notes>
      <price>58.11</price>
      <product_code>WEST2</product_code>
      <Response />
    </Item>
  </Items>
</MyMobileWorkersData>
```
