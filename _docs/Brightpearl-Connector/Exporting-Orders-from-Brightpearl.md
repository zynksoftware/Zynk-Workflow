---
slug: exporting-orders-from-brightpearl
redirect_from: "/article/175-downloading-orders-from-brightpearl"
title: Exporting Orders from Brightpearl
---


This task will download orders from Brightpearl in XML format.


## Settings

### Connection 
_Required_

### Order Status ID
_Optional_

### Order Type ID
_Optional_

### Output File 
_Required_
The file to save the downloaded orders to.

### Brightpearl Settings
See [Common Brightpearl Settings](common-brightpearl-settings)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples

Sample output file:


```xml
    <?xml version="1.0"?>
    <ArrayOfOrder>
      <Order>
        <externalId>5230</externalId>
        <createdOn>2016-11-30T10:00:43Z</createdOn>
        <updatedOn xsi:nil="true" />
        <id>25</id>
        <parentOrderId>0</parentOrderId>
        <orderTypeCode>SO</orderTypeCode>
        <reference>upload4321</reference>
        <acknowledged>0</acknowledged>
        <orderStatus>
          <orderStatusId>3</orderStatusId>
          <name>New phone order</name>
        </orderStatus>
        <orderPaymentStatus>UNPAID</orderPaymentStatus>
        <stockStatusCode>SON</stockStatusCode>
        <allocationStatusCode>ANA</allocationStatusCode>
        <shippingStatusCode>SNS</shippingStatusCode>
        <placedOn>2016-11-18T14:00:00Z</placedOn>
        <createdById>4</createdById>
        <priceList>
          <id>1</id>
          <name>
            <languageCode>en</languageCode>
            <text>Cost</text>
            <format>PLAINTEXT</format>
          </name>
          <code>COST</code>
          <currencyCode>GBP</currencyCode>
          <currencySymbol>£</currencySymbol>
          <currencyId>1</currencyId>
          <priceListTypeCode>BUY</priceListTypeCode>
          <gross>false</gross>
        </priceList>
        <priceModeCode>EXC</priceModeCode>
        <delivery>
          <deliveryDate>2016-11-25T23:00:00Z</deliveryDate>
          <shippingMethod>
            <id>6</id>
            <name>DHL</name>
            <code>DHL</code>
            <breaks>10,100,250,1000,100000</breaks>
            <methodType>1</methodType>
            <additionalInformationRequired>false</additionalInformationRequired>
          </shippingMethod>
        </delivery>
        <invoices>
          <invoice>
            <dueDate>2016-12-30T00:00:00Z</dueDate>
            <invoiceReference />
            <taxDate>2016-11-18T00:00:00Z</taxDate>
          </invoice>
        </invoices>
        <currency>
          <accountingCurrencyCode>GBP</accountingCurrencyCode>
          <orderCurrencyCode>GBP</orderCurrencyCode>
          <exchangeRate>1</exchangeRate>
        </currency>
        <totalValue>
          <net>410</net>
          <taxAmount>82</taxAmount>
          <baseNet>410</baseNet>
          <baseTaxAmount>82</baseTaxAmount>
        </totalValue>
        <assignment>
          <current>
            <staffOwnerContactId>0</staffOwnerContactId>
            <departmentId xsi:nil="true" />
            <leadSourceId>0</leadSourceId>
            <channelId>0</channelId>
            <projectId>0</projectId>
          </current>
        </assignment>
        <parties>
          <customer>
            <contact>
              <createdOn>2010-08-17T13:57:14+01:00</createdOn>
              <updatedOn>2016-11-24T10:11:22Z</updatedOn>
              <contactId>200</contactId>
              <isPrimaryContact>true</isPrimaryContact>
              <salutation>Mr.</salutation>
              <firstName>Demo</firstName>
              <lastName>Customer</lastName>
              <postalAddresses>
                <defaultAddress>
                  <addressId>107</addressId>
                  <countryId xsi:nil="true" />
                </defaultAddress>
                <billingAddress>
                  <addressId>107</addressId>
                  <countryId xsi:nil="true" />
                </billingAddress>
                <deliveryAddress>
                  <addressId>107</addressId>
                  <countryId xsi:nil="true" />
                </deliveryAddress>
              </postalAddresses>
              <communication>
                <emails>
                  <PRI>
                    <email>demo@test.com</email>
                  </PRI>
                </emails>
                <telephones>
                  <PRI>01245 845632</PRI>
                </telephones>
                <messagingVoips />
                <websites />
              </communication>
              <contactStatus>
                <current>
                  <contactStatusId>0</contactStatusId>
                </current>
              </contactStatus>
              <relationshipToAccount>
                <isSupplier>false</isSupplier>
                <isStaff>false</isStaff>
              </relationshipToAccount>
              <marketingDetails>
                <isReceiveEmailNewsletterStaff xsi:nil="true" />
              </marketingDetails>
              <financialDetails>
                <priceList>
                  <id>1</id>
                  <currencyId xsi:nil="true" />
                  <gross xsi:nil="true" />
                </priceList>
                <nominalCode>0</nominalCode>
                <creditLimit>1000</creditLimit>
                <creditTermDays>30</creditTermDays>
                <currency>
                  <id>1</id>
                  <isDefault xsi:nil="true" />
                </currency>
                <discountPercentage>0</discountPercentage>
              </financialDetails>
              <assignment>
                <current>
                  <staffOwnerContactId xsi:nil="true" />
                  <departmentId xsi:nil="true" />
                  <leadSourceId xsi:nil="true" />
                  <channelId xsi:nil="true" />
                  <projectId xsi:nil="true" />
                </current>
              </assignment>
              <organisation>
                <organisationId xsi:nil="true" />
                <name>Customer Company Ltd.</name>
              </organisation>
              <createdByid>2</createdByid>
              <contactTags>1</contactTags>
            </contact>
            <addressFullName>Demo Customer</addressFullName>
            <companyName>Customer Company Ltd.</companyName>
            <addressLine1>34 Lime St</addressLine1>
            <addressLine2>Barton</addressLine2>
            <addressLine3>Sheffield</addressLine3>
            <addressLine4>South Yorkshire</addressLine4>
            <postalCode>S1 4RT</postalCode>
            <country>United Kingdom</country>
            <countryIsoCode>GB</countryIsoCode>
            <telephone>01245 845632</telephone>
            <mobileTelephone />
            <email>demo@test.com</email>
          </customer>
          <delivery>
            <addressFullName>Demo Customer</addressFullName>
            <companyName>Customer Company Ltd.</companyName>
            <addressLine1>34 Lime St</addressLine1>
            <addressLine2>Barton</addressLine2>
            <addressLine3>Sheffield</addressLine3>
            <addressLine4>South Yorkshire</addressLine4>
            <postalCode>S1 4RT</postalCode>
            <country>United Kingdom</country>
            <countryIsoCode>GB</countryIsoCode>
            <telephone>01245 845632</telephone>
            <mobileTelephone />
            <email>demo@test.com</email>
          </delivery>
          <billing>
            <contact>
              <createdOn xsi:nil="true" />
              <updatedOn xsi:nil="true" />
              <contactId>200</contactId>
              <isPrimaryContact xsi:nil="true" />
              <createdByid xsi:nil="true" />
            </contact>
            <addressFullName>Demo Customer</addressFullName>
            <companyName>Customer Company Ltd.</companyName>
            <addressLine1>34 Lime St</addressLine1>
            <addressLine2>Barton</addressLine2>
            <addressLine3>Sheffield</addressLine3>
            <addressLine4>South Yorkshire</addressLine4>
            <postalCode>S1 4RT</postalCode>
            <country>United Kingdom</country>
            <countryIsoCode>GB</countryIsoCode>
            <telephone>01245 845632</telephone>
            <mobileTelephone />
            <email />
          </billing>
        </parties>
        <orderRows>
          <item>
            <key>43</key>
            <value>
              <externalId>4877</externalId>
              <createdOn xsi:nil="true" />
              <updatedOn xsi:nil="true" />
              <orderRowSequence>10</orderRowSequence>
              <product>
                <createdOn xsi:nil="true" />
                <updatedOn>2016-11-17T10:36:49Z</updatedOn>
                <id>1002</id>
                <brand>
                  <id>74</id>
                </brand>
                <productType>
                  <id>1</id>
                </productType>
                <seasons />
                <productGroupId>0</productGroupId>
                <nominalCodeStock>1001</nominalCodeStock>
                <identity>
                  <sku>LT1</sku>
                  <barcode />
                </identity>
                <stock>
                  <stockTracked>false</stockTracked>
                  <weight>
                    <magnitude>0</magnitude>
                  </weight>
                </stock>
                <financialDetails>
                  <taxable>false</taxable>
                  <taxCode>
                    <id>7</id>
                    <code>T20</code>
                    <rate xsi:nil="true" />
                  </taxCode>
                </financialDetails>
                <salesChannels>
                  <salesChannel>
                    <id xsi:nil="true" />
                    <salesChannelName>Brightpearl</salesChannelName>
                    <productName>Labour time</productName>
                    <productCondition>new</productCondition>
                    <categories>
                      <Category>
                        <categoryCode>295</categoryCode>
                      </Category>
                    </categories>
                    <description>
                      <languageCode>en</languageCode>
                      <text />
                      <format>HTML_FRAGMENT</format>
                    </description>
                    <shortDescription>
                      <languageCode>en</languageCode>
                      <text />
                      <format>HTML_FRAGMENT</format>
                    </shortDescription>
                    <availableToSellOnChannel xsi:nil="true" />
                    <sellwhenNoStock xsi:nil="true" />
                  </salesChannel>
                </salesChannels>
                <composition>
                  <bundle>false</bundle>
                </composition>
                <warehouses>
                  <item>
                    <key>2</key>
                    <value>
                      <defaultLocationId>0</defaultLocationId>
                      <reorderLevel>1</reorderLevel>
                      <reorderQuantity>1</reorderQuantity>
                    </value>
                  </item>
                </warehouses>
              </product>
              <productName>Labour time</productName>
              <quantity>
                <magnitude>1</magnitude>
              </quantity>
              <itemCost>
                <currencyCode>GBP</currencyCode>
                <value>0</value>
              </itemCost>
              <rowValue>
                <taxRate>20</taxRate>
                <taxCode>T20</taxCode>
                <rowNet>
                  <currencyCode>GBP</currencyCode>
                  <value>200</value>
                </rowNet>
                <rowTax>
                  <currencyCode>GBP</currencyCode>
                  <value>40</value>
                </rowTax>
              </rowValue>
              <nominalCode>4000</nominalCode>
              <composition>
                <bundleParent>false</bundleParent>
                <bundleChild>false</bundleChild>
                <parentOrderRowId>0</parentOrderRowId>
              </composition>
            </value>
          </item>
          <item>
            <key>44</key>
            <value>
              <externalId>6004</externalId>
              <createdOn xsi:nil="true" />
              <updatedOn xsi:nil="true" />
              <orderRowSequence>20</orderRowSequence>
              <product>
                <createdOn>2007-05-29T11:42:08+01:00</createdOn>
                <updatedOn>2007-09-08T15:42:45+01:00</updatedOn>
                <id>1000</id>
                <brand>
                  <id>74</id>
                </brand>
                <productType>
                  <id>1</id>
                </productType>
                <seasons />
                <productGroupId>0</productGroupId>
                <nominalCodeStock>1001</nominalCodeStock>
                <identity>
                  <sku />
                  <barcode />
                </identity>
                <stock>
                  <stockTracked>false</stockTracked>
                  <weight>
                    <magnitude>100</magnitude>
                  </weight>
                </stock>
                <financialDetails>
                  <taxable>false</taxable>
                  <taxCode>
                    <id>7</id>
                    <code>T20</code>
                    <rate xsi:nil="true" />
                  </taxCode>
                </financialDetails>
                <salesChannels>
                  <salesChannel>
                    <id xsi:nil="true" />
                    <salesChannelName>Brightpearl</salesChannelName>
                    <productName>Misc item without VAT</productName>
                    <productCondition>new</productCondition>
                    <categories>
                      <Category>
                        <categoryCode>276</categoryCode>
                      </Category>
                    </categories>
                    <description>
                      <languageCode>en</languageCode>
                      <text>Product description in here</text>
                      <format>HTML_FRAGMENT</format>
                    </description>
                    <shortDescription>
                      <languageCode>en</languageCode>
                      <text />
                      <format>HTML_FRAGMENT</format>
                    </shortDescription>
                    <availableToSellOnChannel xsi:nil="true" />
                    <sellwhenNoStock xsi:nil="true" />
                  </salesChannel>
                </salesChannels>
                <composition>
                  <bundle>false</bundle>
                </composition>
                <warehouses>
                  <item>
                    <key>2</key>
                    <value>
                      <defaultLocationId>0</defaultLocationId>
                      <reorderLevel>1</reorderLevel>
                      <reorderQuantity>1</reorderQuantity>
                    </value>
                  </item>
                </warehouses>
              </product>
              <productName>Free text item</productName>
              <quantity>
                <magnitude>1</magnitude>
              </quantity>
              <itemCost>
                <currencyCode>GBP</currencyCode>
                <value>0</value>
              </itemCost>
              <rowValue>
                <taxRate>20</taxRate>
                <taxCode>T20</taxCode>
                <rowNet>
                  <currencyCode>GBP</currencyCode>
                  <value>10</value>
                </rowNet>
                <rowTax>
                  <currencyCode>GBP</currencyCode>
                  <value>2</value>
                </rowTax>
              </rowValue>
              <nominalCode>4000</nominalCode>
              <composition>
                <bundleParent>false</bundleParent>
                <bundleChild>false</bundleChild>
                <parentOrderRowId>0</parentOrderRowId>
              </composition>
            </value>
          </item>
        </orderRows>
        <warehouse>
          <id>2</id>
          <name>Main warehouse</name>
          <address>
            <addressId>110</addressId>
            <countryId>222</countryId>
          </address>
        </warehouse>
        <customFields>
          <customField>
            <op xsi:nil="true" />
            <path>/PCF_YESNO</path>
            <value type="System.Boolean, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
              <boolean>true</boolean>
            </value>
          </customField>
          <customField>
            <op xsi:nil="true" />
            <path>/PCF_DATE</path>
            <value type="System.DateTime, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
              <dateTime>2016-11-17T00:00:00Z</dateTime>
            </value>
          </customField>
        </customFields>
      </Order>
    </ArrayOfOrder>

```