---
slug: how-to-calculate-vat-from-a-gross-price
redirect_from: "/article/620-how-to-calculate-vat-from-a-gross-price"
title: How to calculate VAT from a gross price
---
Calculation of VAT can cause a number of strange rounding issues and this example below shows the correct and incorrect methods of calculating VAT from a gross price.

Figures are shown at 15% VAT for the purpose of this example, you should use the correct VAT rate which at this time is 20%

## Incorrect calcuation method

 * Total Gross Price = 14.99
 * Take off VAT = 13.0347
 * Round to 2dp = 13.03
 * Add back VAT = 14.9845
 * Round to 2dp = 14.98

## Correct calcuation method

 * Total Gross Price = 14.99
 * Take off VAT = 13.0347
 * Do not round the value = 13.0347
 * Add back VAT = 14.989905
 * Round to 2dp = 14.99

## Values to pass to Zynk XML

 * Net = 13.03 (14.99 / 1.15)
 * Vat = 1.96 (14.99 - 13.03)

