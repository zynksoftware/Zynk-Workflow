---
slug: sage-50-uk-stock-columns
title: Sage 50 UK STOCK Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| STOCK_CODE | VARCHAR | 30 | 30 | Stock code | BOARD001 |
| DESCRIPTION | VARCHAR | 60 | 60 | Description | Whiteboard - Drywipe (900 x 1200) |
| UNIT_OF_SALE | VARCHAR | 8 | 8 | Unit of sale | Each |
| NOMINAL_CODE | VARCHAR | 8 | 8 | Nominal code | 4000 |
| PURCHASE_REF | VARCHAR | 8 | 8 | Supplier's account reference | UNI001 |
| SUPPLIER_PART_NUMBER | VARCHAR | 16 | 16 | Supplier's part number | U143 |
| LOCATION | VARCHAR | 16 | 16 | Bin location | Warehouse |
| COMMODITY_CODE | VARCHAR | 30 | 30 | Commodity code |  |
| SALES_PRICE | DOUBLE | 8 | 15 | Sale price | 20 |
| WEB_DESCRIPTION | VARCHAR | 255 | 255 | Web Description | Whiteboard - Drywipe (900 x 1200) |
| WEB_DETAILS | VARCHAR | 1023 | 1023 | Web Details | Magnetic steel drywipe whiteboard.  Complete with marker tray.  Compatible with most rail systems  Dimensions: 900 x 1200 |
| WEB_CATEGORY_1 | VARCHAR | 60 | 60 | Web Category 1 | Office Equipment |
| WEB_CATEGORY_2 | VARCHAR | 60 | 60 | Web Category 2 | Presentation Supplies |
| WEB_CATEGORY_3 | VARCHAR | 60 | 60 | Web Category 3 | Whiteboards |
| WEB_IMAGE_FILE | VARCHAR | 60 | 60 | Web Image Filename | board001.jpg |
| WEB_PUBLISH | SMALLINT | 2 | 5 | Is published on the web | 1 |
| WEB_SPECIAL | SMALLINT | 2 | 5 | Is on special offer on the web | 0 |
| INTRASTAT_COMM_CODE | VARCHAR | 8 | 8 | Commodity Code (for Intrastat) |  |
| INTRASTAT_IMPORT_DUTY_CODE | VARCHAR | 2 | 2 | Import duty code (for Intrastat) |  |
| SUPP_UNIT_QTY | DOUBLE | 8 | 15 | Supplementary Unit Quantity | 0 |
| IGNORE_STK_LVL_FLAG | TINYINT | 1 | 3 | Ignore stock level flag | 0 |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department number | 1 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Sales |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) | T1 |
| ASSEMBLY_LEVEL | SMALLINT | 2 | 5 | Assembly level | 0 |
| LINK_LEVEL | SMALLINT | 2 | 5 | Link level | 0 |
| STOCK_CAT | SMALLINT | 2 | 5 | Stock category number | 6 |
| STOCK_CAT_NAME | VARCHAR | 30 | 30 | Stock category name | Presentation Supplies |
| STOCK_TAKE_DATE | DATE | 2 | 10 | Stock take date | 31/12/2006 00:00:00 |
| LAST_PURCHASE_PRICE | DOUBLE | 8 | 15 | Last purchase price | 15 |
| LAST_DISC_PURCHASE_PRICE | DOUBLE | 8 | 15 | Last discounted purchase price | 15 |
| AVERAGE_COST_PRICE | DOUBLE | 8 | 15 | Average cost price | 13.2 |
| QTY_IN_STOCK | DOUBLE | 8 | 15 | Quantity in stock | 5 |
| QTY_ON_ORDER | DOUBLE | 8 | 15 | Quantity on order | 0 |
| QTY_ALLOCATED | DOUBLE | 8 | 15 | Quantity allocated | 0 |
| QTY_LAST_ORDER | DOUBLE | 8 | 15 | Last order quantity | 8 |
| QTY_REORDER | DOUBLE | 8 | 15 | Reorder quantity | 2 |
| QTY_REORDER_LEVEL | DOUBLE | 8 | 15 | Reorder level | 1 |
| QTY_LAST_STOCK_TAKE | DOUBLE | 8 | 15 | Last stock take quantity | 2 |
| QTY_MAKEUP | DOUBLE | 8 | 15 | Makeup from quantity in stock (ignore quantity on order) | 0 |
| LAST_SALE_DATE | DATE | 2 | 10 | Last sale date | 01/04/2007 00:00:00 |
| LAST_PURCHASE_DATE | DATE | 2 | 10 | Last purchase date | 27/04/2007 00:00:00 |
| UNIT_WEIGHT | DOUBLE | 8 | 15 | Unit weight | 0 |
| HAS_NO_COMPONENT | SMALLINT | 2 | 5 | 1 if has no components, 0 if contains subcomponents | 1 |
| HAS_BOM | VARCHAR | 1 | 1 | Y if has components, blank if not |  |
| BARCODE | VARCHAR | 60 | 60 | Stock Barcode |  |
| COMPONENT_CODE_1 | VARCHAR | 30 | 30 | Component 1 stock code |  |
| COMPONENT_CODE_2 | VARCHAR | 30 | 30 | Component 2 stock code |  |
| COMPONENT_CODE_3 | VARCHAR | 30 | 30 | Component 3 stock code |  |
| COMPONENT_CODE_4 | VARCHAR | 30 | 30 | Component 4 stock code |  |
| COMPONENT_CODE_5 | VARCHAR | 30 | 30 | Component 5 stock code |  |
| COMPONENT_CODE_6 | VARCHAR | 30 | 30 | Component 6 stock code |  |
| COMPONENT_CODE_7 | VARCHAR | 30 | 30 | Component 7 stock code |  |
| COMPONENT_CODE_8 | VARCHAR | 30 | 30 | Component 8 stock code |  |
| COMPONENT_CODE_9 | VARCHAR | 30 | 30 | Component 9 stock code |  |
| COMPONENT_CODE_10 | VARCHAR | 30 | 30 | Component 10 stock code |  |
| COMPONENT_CODE_11 | VARCHAR | 30 | 30 | Component 11 stock code |  |
| COMPONENT_CODE_12 | VARCHAR | 30 | 30 | Component 12 stock code |  |
| COMPONENT_CODE_13 | VARCHAR | 30 | 30 | Component 13 stock code |  |
| COMPONENT_CODE_14 | VARCHAR | 30 | 30 | Component 14 stock code |  |
| COMPONENT_CODE_15 | VARCHAR | 30 | 30 | Component 15 stock code |  |
| COMPONENT_CODE_16 | VARCHAR | 30 | 30 | Component 16 stock code |  |
| COMPONENT_CODE_17 | VARCHAR | 30 | 30 | Component 17 stock code |  |
| COMPONENT_CODE_18 | VARCHAR | 30 | 30 | Component 18 stock code |  |
| COMPONENT_CODE_19 | VARCHAR | 30 | 30 | Component 19 stock code |  |
| COMPONENT_CODE_20 | VARCHAR | 30 | 30 | Component 20 stock code |  |
| COMPONENT_CODE_21 | VARCHAR | 30 | 30 | Component 21 stock code |  |
| COMPONENT_CODE_22 | VARCHAR | 30 | 30 | Component 22 stock code |  |
| COMPONENT_CODE_23 | VARCHAR | 30 | 30 | Component 23 stock code |  |
| COMPONENT_CODE_24 | VARCHAR | 30 | 30 | Component 24 stock code |  |
| COMPONENT_CODE_25 | VARCHAR | 30 | 30 | Component 25 stock code |  |
| COMPONENT_CODE_26 | VARCHAR | 30 | 30 | Component 26 stock code |  |
| COMPONENT_CODE_27 | VARCHAR | 30 | 30 | Component 27 stock code |  |
| COMPONENT_CODE_28 | VARCHAR | 30 | 30 | Component 28 stock code |  |
| COMPONENT_CODE_29 | VARCHAR | 30 | 30 | Component 29 stock code |  |
| COMPONENT_CODE_30 | VARCHAR | 30 | 30 | Component 30 stock code |  |
| COMPONENT_CODE_31 | VARCHAR | 30 | 30 | Component 31 stock code |  |
| COMPONENT_CODE_32 | VARCHAR | 30 | 30 | Component 32 stock code |  |
| COMPONENT_CODE_33 | VARCHAR | 30 | 30 | Component 33 stock code |  |
| COMPONENT_CODE_34 | VARCHAR | 30 | 30 | Component 34 stock code |  |
| COMPONENT_CODE_35 | VARCHAR | 30 | 30 | Component 35 stock code |  |
| COMPONENT_CODE_36 | VARCHAR | 30 | 30 | Component 36 stock code |  |
| COMPONENT_CODE_37 | VARCHAR | 30 | 30 | Component 37 stock code |  |
| COMPONENT_CODE_38 | VARCHAR | 30 | 30 | Component 38 stock code |  |
| COMPONENT_CODE_39 | VARCHAR | 30 | 30 | Component 39 stock code |  |
| COMPONENT_CODE_40 | VARCHAR | 30 | 30 | Component 40 stock code |  |
| COMPONENT_CODE_41 | VARCHAR | 30 | 30 | Component 41 stock code |  |
| COMPONENT_CODE_42 | VARCHAR | 30 | 30 | Component 42 stock code |  |
| COMPONENT_CODE_43 | VARCHAR | 30 | 30 | Component 43 stock code |  |
| COMPONENT_CODE_44 | VARCHAR | 30 | 30 | Component 44 stock code |  |
| COMPONENT_CODE_45 | VARCHAR | 30 | 30 | Component 45 stock code |  |
| COMPONENT_CODE_46 | VARCHAR | 30 | 30 | Component 46 stock code |  |
| COMPONENT_CODE_47 | VARCHAR | 30 | 30 | Component 47 stock code |  |
| COMPONENT_CODE_48 | VARCHAR | 30 | 30 | Component 48 stock code |  |
| COMPONENT_CODE_49 | VARCHAR | 30 | 30 | Component 49 stock code |  |
| COMPONENT_CODE_50 | VARCHAR | 30 | 30 | Component 50 stock code |  |
| COMPONENT_QTY_1 | DOUBLE | 8 | 15 | Component 1 quantity | 0 |
| COMPONENT_QTY_2 | DOUBLE | 8 | 15 | Component 2 quantity | 0 |
| COMPONENT_QTY_3 | DOUBLE | 8 | 15 | Component 3 quantity | 0 |
| COMPONENT_QTY_4 | DOUBLE | 8 | 15 | Component 4 quantity | 0 |
| COMPONENT_QTY_5 | DOUBLE | 8 | 15 | Component 5 quantity | 0 |
| COMPONENT_QTY_6 | DOUBLE | 8 | 15 | Component 6 quantity | 0 |
| COMPONENT_QTY_7 | DOUBLE | 8 | 15 | Component 7 quantity | 0 |
| COMPONENT_QTY_8 | DOUBLE | 8 | 15 | Component 8 quantity | 0 |
| COMPONENT_QTY_9 | DOUBLE | 8 | 15 | Component 9 quantity | 0 |
| COMPONENT_QTY_10 | DOUBLE | 8 | 15 | Component 10 quantity | 0 |
| COMPONENT_QTY_11 | DOUBLE | 8 | 15 | Component 11 quantity | 0 |
| COMPONENT_QTY_12 | DOUBLE | 8 | 15 | Component 12 quantity | 0 |
| COMPONENT_QTY_13 | DOUBLE | 8 | 15 | Component 13 quantity | 0 |
| COMPONENT_QTY_14 | DOUBLE | 8 | 15 | Component 14 quantity | 0 |
| COMPONENT_QTY_15 | DOUBLE | 8 | 15 | Component 15 quantity | 0 |
| COMPONENT_QTY_16 | DOUBLE | 8 | 15 | Component 16 quantity | 0 |
| COMPONENT_QTY_17 | DOUBLE | 8 | 15 | Component 17 quantity | 0 |
| COMPONENT_QTY_18 | DOUBLE | 8 | 15 | Component 18 quantity | 0 |
| COMPONENT_QTY_19 | DOUBLE | 8 | 15 | Component 19 quantity | 0 |
| COMPONENT_QTY_20 | DOUBLE | 8 | 15 | Component 20 quantity | 0 |
| COMPONENT_QTY_21 | DOUBLE | 8 | 15 | Component 21 quantity | 0 |
| COMPONENT_QTY_22 | DOUBLE | 8 | 15 | Component 22 quantity | 0 |
| COMPONENT_QTY_23 | DOUBLE | 8 | 15 | Component 23 quantity | 0 |
| COMPONENT_QTY_24 | DOUBLE | 8 | 15 | Component 24 quantity | 0 |
| COMPONENT_QTY_25 | DOUBLE | 8 | 15 | Component 25 quantity | 0 |
| COMPONENT_QTY_26 | DOUBLE | 8 | 15 | Component 26 quantity | 0 |
| COMPONENT_QTY_27 | DOUBLE | 8 | 15 | Component 27 quantity | 0 |
| COMPONENT_QTY_28 | DOUBLE | 8 | 15 | Component 28 quantity | 0 |
| COMPONENT_QTY_29 | DOUBLE | 8 | 15 | Component 29 quantity | 0 |
| COMPONENT_QTY_30 | DOUBLE | 8 | 15 | Component 30 quantity | 0 |
| COMPONENT_QTY_31 | DOUBLE | 8 | 15 | Component 31 quantity | 0 |
| COMPONENT_QTY_32 | DOUBLE | 8 | 15 | Component 32 quantity | 0 |
| COMPONENT_QTY_33 | DOUBLE | 8 | 15 | Component 33 quantity | 0 |
| COMPONENT_QTY_34 | DOUBLE | 8 | 15 | Component 34 quantity | 0 |
| COMPONENT_QTY_35 | DOUBLE | 8 | 15 | Component 35 quantity | 0 |
| COMPONENT_QTY_36 | DOUBLE | 8 | 15 | Component 36 quantity | 0 |
| COMPONENT_QTY_37 | DOUBLE | 8 | 15 | Component 37 quantity | 0 |
| COMPONENT_QTY_38 | DOUBLE | 8 | 15 | Component 38 quantity | 0 |
| COMPONENT_QTY_39 | DOUBLE | 8 | 15 | Component 39 quantity | 0 |
| COMPONENT_QTY_40 | DOUBLE | 8 | 15 | Component 40 quantity | 0 |
| COMPONENT_QTY_41 | DOUBLE | 8 | 15 | Component 41 quantity | 0 |
| COMPONENT_QTY_42 | DOUBLE | 8 | 15 | Component 42 quantity | 0 |
| COMPONENT_QTY_43 | DOUBLE | 8 | 15 | Component 43 quantity | 0 |
| COMPONENT_QTY_44 | DOUBLE | 8 | 15 | Component 44 quantity | 0 |
| COMPONENT_QTY_45 | DOUBLE | 8 | 15 | Component 45 quantity | 0 |
| COMPONENT_QTY_46 | DOUBLE | 8 | 15 | Component 46 quantity | 0 |
| COMPONENT_QTY_47 | DOUBLE | 8 | 15 | Component 47 quantity | 0 |
| COMPONENT_QTY_48 | DOUBLE | 8 | 15 | Component 48 quantity | 0 |
| COMPONENT_QTY_49 | DOUBLE | 8 | 15 | Component 49 quantity | 0 |
| COMPONENT_QTY_50 | DOUBLE | 8 | 15 | Component 50 quantity | 0 |
| QTY_SOLD_BF | DOUBLE | 8 | 15 | Brought forward quantity sold | 15 |
| QTY_SOLD_MTH1 | DOUBLE | 8 | 15 | Month 1 quantity sold | 0 |
| QTY_SOLD_MTH2 | DOUBLE | 8 | 15 | Month 2 quantity sold | 0 |
| QTY_SOLD_MTH3 | DOUBLE | 8 | 15 | Month 3 quantity sold | 0 |
| QTY_SOLD_MTH4 | DOUBLE | 8 | 15 | Month 4 quantity sold | 0 |
| QTY_SOLD_MTH5 | DOUBLE | 8 | 15 | Month 5 quantity sold | 0 |
| QTY_SOLD_MTH6 | DOUBLE | 8 | 15 | Month 6 quantity sold | 0 |
| QTY_SOLD_MTH7 | DOUBLE | 8 | 15 | Month 7 quantity sold | 0 |
| QTY_SOLD_MTH8 | DOUBLE | 8 | 15 | Month 8 quantity sold | 0 |
| QTY_SOLD_MTH9 | DOUBLE | 8 | 15 | Month 9 quantity sold | 0 |
| QTY_SOLD_MTH10 | DOUBLE | 8 | 15 | Month 10 quantity sold | 0 |
| QTY_SOLD_MTH11 | DOUBLE | 8 | 15 | Month 11 quantity sold | 0 |
| QTY_SOLD_MTH12 | DOUBLE | 8 | 15 | Month 12 quantity sold | 0 |
| QTY_SOLD_FUTURE | DOUBLE | 8 | 15 | Future quantity sold | 0 |
| SALES_BF | DOUBLE | 8 | 15 | Brought forward sales | 274.14 |
| SALES_MTH1 | DOUBLE | 8 | 15 | Month 1 sales | 0 |
| SALES_MTH2 | DOUBLE | 8 | 15 | Month 2 sales | 0 |
| SALES_MTH3 | DOUBLE | 8 | 15 | Month 3 sales | 0 |
| SALES_MTH4 | DOUBLE | 8 | 15 | Month 4 sales | 0 |
| SALES_MTH5 | DOUBLE | 8 | 15 | Month 5 sales | 0 |
| SALES_MTH6 | DOUBLE | 8 | 15 | Month 6 sales | 0 |
| SALES_MTH7 | DOUBLE | 8 | 15 | Month 7 sales | 0 |
| SALES_MTH8 | DOUBLE | 8 | 15 | Month 8 sales | 0 |
| SALES_MTH9 | DOUBLE | 8 | 15 | Month 9 sales | 0 |
| SALES_MTH10 | DOUBLE | 8 | 15 | Month 10 sales | 0 |
| SALES_MTH11 | DOUBLE | 8 | 15 | Month 11 sales | 0 |
| SALES_MTH12 | DOUBLE | 8 | 15 | Month 12 sales | 0 |
| SALES_FUTURE | DOUBLE | 8 | 15 | Future sales | 0 |
| COST_BF | DOUBLE | 8 | 15 | Brought forward costs | 221.4 |
| COST_MTH1 | DOUBLE | 8 | 15 | Month 1 costs | 0 |
| COST_MTH2 | DOUBLE | 8 | 15 | Month 2 costs | 0 |
| COST_MTH3 | DOUBLE | 8 | 15 | Month 3 costs | 0 |
| COST_MTH4 | DOUBLE | 8 | 15 | Month 4 costs | 0 |
| COST_MTH5 | DOUBLE | 8 | 15 | Month 5 costs | 0 |
| COST_MTH6 | DOUBLE | 8 | 15 | Month 6 costs | 0 |
| COST_MTH7 | DOUBLE | 8 | 15 | Month 7 costs | 0 |
| COST_MTH8 | DOUBLE | 8 | 15 | Month 8 costs | 0 |
| COST_MTH9 | DOUBLE | 8 | 15 | Month 9 costs | 0 |
| COST_MTH10 | DOUBLE | 8 | 15 | Month 10 costs | 0 |
| COST_MTH11 | DOUBLE | 8 | 15 | Month 11 costs | 0 |
| COST_MTH12 | DOUBLE | 8 | 15 | Month 12 costs | 0 |
| COST_FUTURE | DOUBLE | 8 | 15 | Future costs | 0 |
| THIS_RECORD | INTEGER | 4 | 10 | Record number | 1 |
| BUDGET_QTY_SOLD_BF | DOUBLE | 8 | 15 | Brought forward budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH1 | DOUBLE | 8 | 15 | Month 1 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH2 | DOUBLE | 8 | 15 | Month 2 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH3 | DOUBLE | 8 | 15 | Month 3 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH4 | DOUBLE | 8 | 15 | Month 4 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH5 | DOUBLE | 8 | 15 | Month 5 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH6 | DOUBLE | 8 | 15 | Month 6 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH7 | DOUBLE | 8 | 15 | Month 7 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH8 | DOUBLE | 8 | 15 | Month 8 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH9 | DOUBLE | 8 | 15 | Month 9 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH10 | DOUBLE | 8 | 15 | Month 10 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH11 | DOUBLE | 8 | 15 | Month 11 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_MTH12 | DOUBLE | 8 | 15 | Month 12 budget quantity sold | 0 |
| BUDGET_QTY_SOLD_FUTURE | DOUBLE | 8 | 15 | Future budget quantity sold | 0 |
| BUDGET_SALES_BF | DOUBLE | 8 | 15 | Brought forward budget sales | 0 |
| BUDGET_SALES_MTH1 | DOUBLE | 8 | 15 | Month 1 budget sales | 0 |
| BUDGET_SALES_MTH2 | DOUBLE | 8 | 15 | Month 2 budget sales | 0 |
| BUDGET_SALES_MTH3 | DOUBLE | 8 | 15 | Month 3 budget sales | 0 |
| BUDGET_SALES_MTH4 | DOUBLE | 8 | 15 | Month 4 budget sales | 0 |
| BUDGET_SALES_MTH5 | DOUBLE | 8 | 15 | Month 5 budget sales | 0 |
| BUDGET_SALES_MTH6 | DOUBLE | 8 | 15 | Month 6 budget sales | 0 |
| BUDGET_SALES_MTH7 | DOUBLE | 8 | 15 | Month 7 budget sales | 0 |
| BUDGET_SALES_MTH8 | DOUBLE | 8 | 15 | Month 8 budget sales | 0 |
| BUDGET_SALES_MTH9 | DOUBLE | 8 | 15 | Month 9 budget sales | 0 |
| BUDGET_SALES_MTH10 | DOUBLE | 8 | 15 | Month 10 budget sales | 0 |
| BUDGET_SALES_MTH11 | DOUBLE | 8 | 15 | Month 11 budget sales | 0 |
| BUDGET_SALES_MTH12 | DOUBLE | 8 | 15 | Month 12 budget sales | 0 |
| BUDGET_SALES_FUTURE | DOUBLE | 8 | 15 | Future budget sales | 0 |
| PRIOR_YR_QTY_SOLD_BF | DOUBLE | 8 | 15 | Prior year brought forward quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH1 | DOUBLE | 8 | 15 | Prior year month 1 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH2 | DOUBLE | 8 | 15 | Prior year month 2 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH3 | DOUBLE | 8 | 15 | Prior year month 3 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH4 | DOUBLE | 8 | 15 | Prior year month 4 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH5 | DOUBLE | 8 | 15 | Prior year month 5 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH6 | DOUBLE | 8 | 15 | Prior year month 6 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH7 | DOUBLE | 8 | 15 | Prior year month 7 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH8 | DOUBLE | 8 | 15 | Prior year month 8 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH9 | DOUBLE | 8 | 15 | Prior year month 9 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH10 | DOUBLE | 8 | 15 | Prior year month 10 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH11 | DOUBLE | 8 | 15 | Prior year month 11 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_MTH12 | DOUBLE | 8 | 15 | Prior year month 12 quantity sold | 0 |
| PRIOR_YR_QTY_SOLD_FUTURE | DOUBLE | 8 | 15 | Prior year future quantity sold | 0 |
| PRIOR_YR_SALES_BF | DOUBLE | 8 | 15 | Prior year brought forward sales | 0 |
| PRIOR_YR_SALES_MTH1 | DOUBLE | 8 | 15 | Prior year month 1 sales | 0 |
| PRIOR_YR_SALES_MTH2 | DOUBLE | 8 | 15 | Prior year month 2 sales | 0 |
| PRIOR_YR_SALES_MTH3 | DOUBLE | 8 | 15 | Prior year month 3 sales | 0 |
| PRIOR_YR_SALES_MTH4 | DOUBLE | 8 | 15 | Prior year month 4 sales | 0 |
| PRIOR_YR_SALES_MTH5 | DOUBLE | 8 | 15 | Prior year month 5 sales | 0 |
| PRIOR_YR_SALES_MTH6 | DOUBLE | 8 | 15 | Prior year month 6 sales | 0 |
| PRIOR_YR_SALES_MTH7 | DOUBLE | 8 | 15 | Prior year month 7 sales | 0 |
| PRIOR_YR_SALES_MTH8 | DOUBLE | 8 | 15 | Prior year month 8 sales | 0 |
| PRIOR_YR_SALES_MTH9 | DOUBLE | 8 | 15 | Prior year month 9 sales | 0 |
| PRIOR_YR_SALES_MTH10 | DOUBLE | 8 | 15 | Prior year month 10 sales | 0 |
| PRIOR_YR_SALES_MTH11 | DOUBLE | 8 | 15 | Prior year month 11 sales | 0 |
| PRIOR_YR_SALES_MTH12 | DOUBLE | 8 | 15 | Prior year month 12 sales | 0 |
| PRIOR_YR_SALES_FUTURE | DOUBLE | 8 | 15 | Prior year future sales | 0 |
| PRIOR_YR_COST_BF | DOUBLE | 8 | 15 | Prior year brought forward costs | 0 |
| PRIOR_YR_COST_MTH1 | DOUBLE | 8 | 15 | Prior year month 1 costs | 0 |
| PRIOR_YR_COST_MTH2 | DOUBLE | 8 | 15 | Prior year month 2 costs | 0 |
| PRIOR_YR_COST_MTH3 | DOUBLE | 8 | 15 | Prior year month 3 costs | 0 |
| PRIOR_YR_COST_MTH4 | DOUBLE | 8 | 15 | Prior year month 4 costs | 0 |
| PRIOR_YR_COST_MTH5 | DOUBLE | 8 | 15 | Prior year month 5 costs | 0 |
| PRIOR_YR_COST_MTH6 | DOUBLE | 8 | 15 | Prior year month 6 costs | 0 |
| PRIOR_YR_COST_MTH7 | DOUBLE | 8 | 15 | Prior year month 7 costs | 0 |
| PRIOR_YR_COST_MTH8 | DOUBLE | 8 | 15 | Prior year month 8 costs | 0 |
| PRIOR_YR_COST_MTH9 | DOUBLE | 8 | 15 | Prior year month 9 costs | 0 |
| PRIOR_YR_COST_MTH10 | DOUBLE | 8 | 15 | Prior year month 10 costs | 0 |
| PRIOR_YR_COST_MTH11 | DOUBLE | 8 | 15 | Prior year month 11 costs | 0 |
| PRIOR_YR_COST_MTH12 | DOUBLE | 8 | 15 | Prior year month 12 costs | 0 |
| PRIOR_YR_COST_FUTURE | DOUBLE | 8 | 15 | Prior year future costs | 0 |
| DISC_A_LEVEL_1_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 1, Quantity | 0 |
| DISC_A_LEVEL_2_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 2, Quantity | 0 |
| DISC_A_LEVEL_3_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 3, Quantity | 0 |
| DISC_A_LEVEL_4_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 4, Quantity | 0 |
| DISC_A_LEVEL_5_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 5, Quantity | 0 |
| DISC_A_LEVEL_6_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 6, Quantity | 0 |
| DISC_A_LEVEL_7_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 7, Quantity | 0 |
| DISC_A_LEVEL_8_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 8, Quantity | 0 |
| DISC_A_LEVEL_9_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 9, Quantity | 0 |
| DISC_A_LEVEL_10_QTY | DOUBLE | 8 | 15 | Discount Table A, Break Level 10, Quantity | 0 |
| DISC_A_LEVEL_1_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 1, Rate | 0 |
| DISC_A_LEVEL_2_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 2, Rate | 0 |
| DISC_A_LEVEL_3_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 3, Rate | 0 |
| DISC_A_LEVEL_4_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 4, Rate | 0 |
| DISC_A_LEVEL_5_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 5, Rate | 0 |
| DISC_A_LEVEL_6_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 6, Rate | 0 |
| DISC_A_LEVEL_7_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 7, Rate | 0 |
| DISC_A_LEVEL_8_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 8, Rate | 0 |
| DISC_A_LEVEL_9_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 9, Rate | 0 |
| DISC_A_LEVEL_10_RATE | DOUBLE | 8 | 15 | Discount Table A, Break Level 10, Rate | 0 |
| DISC_B_LEVEL_1_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 1, Quantity | 0 |
| DISC_B_LEVEL_2_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 2, Quantity | 0 |
| DISC_B_LEVEL_3_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 3, Quantity | 0 |
| DISC_B_LEVEL_4_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 4, Quantity | 0 |
| DISC_B_LEVEL_5_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 5, Quantity | 0 |
| DISC_B_LEVEL_6_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 6, Quantity | 0 |
| DISC_B_LEVEL_7_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 7, Quantity | 0 |
| DISC_B_LEVEL_8_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 8, Quantity | 0 |
| DISC_B_LEVEL_9_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 9, Quantity | 0 |
| DISC_B_LEVEL_10_QTY | DOUBLE | 8 | 15 | Discount Table B, Break Level 10, Quantity | 0 |
| DISC_B_LEVEL_1_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 1, Rate | 0 |
| DISC_B_LEVEL_2_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 2, Rate | 0 |
| DISC_B_LEVEL_3_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 3, Rate | 0 |
| DISC_B_LEVEL_4_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 4, Rate | 0 |
| DISC_B_LEVEL_5_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 5, Rate | 0 |
| DISC_B_LEVEL_6_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 6, Rate | 0 |
| DISC_B_LEVEL_7_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 7, Rate | 0 |
| DISC_B_LEVEL_8_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 8, Rate | 0 |
| DISC_B_LEVEL_9_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 9, Rate | 0 |
| DISC_B_LEVEL_10_RATE | DOUBLE | 8 | 15 | Discount Table B, Break Level 10, Rate | 0 |
| DISC_C_LEVEL_1_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 1, Quantity | 0 |
| DISC_C_LEVEL_2_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 2, Quantity | 0 |
| DISC_C_LEVEL_3_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 3, Quantity | 0 |
| DISC_C_LEVEL_4_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 4, Quantity | 0 |
| DISC_C_LEVEL_5_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 5, Quantity | 0 |
| DISC_C_LEVEL_6_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 6, Quantity | 0 |
| DISC_C_LEVEL_7_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 7, Quantity | 0 |
| DISC_C_LEVEL_8_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 8, Quantity | 0 |
| DISC_C_LEVEL_9_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 9, Quantity | 0 |
| DISC_C_LEVEL_10_QTY | DOUBLE | 8 | 15 | Discount Table C, Break Level 10, Quantity | 0 |
| DISC_C_LEVEL_1_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 1, Rate | 0 |
| DISC_C_LEVEL_2_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 2, Rate | 0 |
| DISC_C_LEVEL_3_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 3, Rate | 0 |
| DISC_C_LEVEL_4_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 4, Rate | 0 |
| DISC_C_LEVEL_5_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 5, Rate | 0 |
| DISC_C_LEVEL_6_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 6, Rate | 0 |
| DISC_C_LEVEL_7_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 7, Rate | 0 |
| DISC_C_LEVEL_8_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 8, Rate | 0 |
| DISC_C_LEVEL_9_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 9, Rate | 0 |
| DISC_C_LEVEL_10_RATE | DOUBLE | 8 | 15 | Discount Table C, Break Level 10, Rate | 0 |
| DISC_D_LEVEL_1_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 1, Quantity | 0 |
| DISC_D_LEVEL_2_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 2, Quantity | 0 |
| DISC_D_LEVEL_3_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 3, Quantity | 0 |
| DISC_D_LEVEL_4_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 4, Quantity | 0 |
| DISC_D_LEVEL_5_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 5, Quantity | 0 |
| DISC_D_LEVEL_6_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 6, Quantity | 0 |
| DISC_D_LEVEL_7_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 7, Quantity | 0 |
| DISC_D_LEVEL_8_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 8, Quantity | 0 |
| DISC_D_LEVEL_9_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 9, Quantity | 0 |
| DISC_D_LEVEL_10_QTY | DOUBLE | 8 | 15 | Discount Table D, Break Level 10, Quantity | 0 |
| DISC_D_LEVEL_1_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 1, Rate | 0 |
| DISC_D_LEVEL_2_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 2, Rate | 0 |
| DISC_D_LEVEL_3_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 3, Rate | 0 |
| DISC_D_LEVEL_4_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 4, Rate | 0 |
| DISC_D_LEVEL_5_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 5, Rate | 0 |
| DISC_D_LEVEL_6_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 6, Rate | 0 |
| DISC_D_LEVEL_7_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 7, Rate | 0 |
| DISC_D_LEVEL_8_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 8, Rate | 0 |
| DISC_D_LEVEL_9_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 9, Rate | 0 |
| DISC_D_LEVEL_10_RATE | DOUBLE | 8 | 15 | Discount Table D, Break Level 10, Rate | 0 |
| DISC_E_LEVEL_1_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 1, Quantity | 0 |
| DISC_E_LEVEL_2_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 2, Quantity | 0 |
| DISC_E_LEVEL_3_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 3, Quantity | 0 |
| DISC_E_LEVEL_4_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 4, Quantity | 0 |
| DISC_E_LEVEL_5_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 5, Quantity | 0 |
| DISC_E_LEVEL_6_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 6, Quantity | 0 |
| DISC_E_LEVEL_7_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 7, Quantity | 0 |
| DISC_E_LEVEL_8_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 8, Quantity | 0 |
| DISC_E_LEVEL_9_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 9, Quantity | 0 |
| DISC_E_LEVEL_10_QTY | DOUBLE | 8 | 15 | Discount Table E, Break Level 10, Quantity | 0 |
| DISC_E_LEVEL_1_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 1, Rate | 0 |
| DISC_E_LEVEL_2_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 2, Rate | 0 |
| DISC_E_LEVEL_3_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 3, Rate | 0 |
| DISC_E_LEVEL_4_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 4, Rate | 0 |
| DISC_E_LEVEL_5_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 5, Rate | 0 |
| DISC_E_LEVEL_6_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 6, Rate | 0 |
| DISC_E_LEVEL_7_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 7, Rate | 0 |
| DISC_E_LEVEL_8_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 8, Rate | 0 |
| DISC_E_LEVEL_9_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 9, Rate | 0 |
| DISC_E_LEVEL_10_RATE | DOUBLE | 8 | 15 | Discount Table E, Break Level 10, Rate | 0 |
| PURCHASE_NOMINAL_CODE | VARCHAR | 8 | 8 | Purchase nominal code | 5000 |
| INACTIVE_FLAG | TINYINT | 1 | 3 | Inactive Flag - Yes/No | 0 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:49 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
