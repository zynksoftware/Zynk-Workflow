---
slug: downloading-products-from-corecommerce
redirect_from: "/article/189-downloading-products-from-corecommerce"
title: Downloading Products from CoreCommerce
---
This task will import download products from CoreCommerce in the CoreCommerce XML format.

## Settings
### Connection
_Required_  
The CoreCommerce connection to use. See the [Connecting to CoreCommerce](connecting-to-corecommerce) article if you require more information on how to create/manage connections.

### IDs
_Optional_  
Enter a list of specific product IDs to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form.

### SKUs
_Optional_  
Enter a list of specific product SKU codes to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form.

### UPCs
_Optional_  
Enter a list of specific product UPC codes to download. The list can be entered as either a comma separated list, or using the 'Use a list' option on the  Zynk Object form.

### Output File
_Required_  
The file to save the downloaded products to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0"?>
<Response xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
	<Action>ACTION_TYPE_PRODUCT_LIST</Action>
	<Status>SUCCESS_CODE</Status>
	<Code />
	<List length="1" possibleLength="1">
		<Product id="8">
			<Languages length="1">
				<LanguageData charset="UTF-8" name="English" id="1">
					<Name>Test Product</Name>
					<Description>
						<p>     Test Product</p>
					</Description>
					<CallEmailForPricingDisplay />
					<MetaDescription />
					<MetaKeywords />
					<MetaTitle />
					<MobileTeaser>
						<p>     Test Product</p>
					</MobileTeaser>
					<MobileDescription>
						<p>     Test Product</p>
					</MobileDescription>
					<CustomTab1Name />
					<CustomTab1HTML />
					<CustomTab2Name />
					<CustomTab2HTML />
					<Slug>Test-Product</Slug>
				</LanguageData>
			</Languages>
			<Sku>PROD001</Sku>
			<Upc />
			<Msrp>
				<Amount>0.00</Amount>
			</Msrp>
			<Price>
				<Amount>10.00</Amount>
			</Price>
			<SalesPrice>
				<Amount>0.00</Amount>
			</SalesPrice>
			<SaleStart>
				<UnixTimeStamp />
				<Day>31</Day>
				<Month>12</Month>
				<Year>1969</Year>
				<Hour>18</Hour>
				<Minute>00</Minute>
				<Second>00</Second>
			</SaleStart>
			<SaleEnd>
				<UnixTimeStamp />
				<Day>31</Day>
				<Month>12</Month>
				<Year>1969</Year>
				<Hour>18</Hour>
				<Minute>00</Minute>
				<Second>00</Second>
			</SaleEnd>
			<UseSalesPrice>FALSE_VALUE</UseSalesPrice>
			<CustomerMustAddToCartToSeeSalesPrice>FALSE_VALUE</CustomerMustAddToCartToSeeSalesPrice>
			<DisplayMSRPAndSavingsFormat>FALSE_VALUE</DisplayMSRPAndSavingsFormat>
			<Categories length="1">
				<Category id="1">
					<Languages length="1">
						<LanguageData charset="UTF-8" name="English" id="1">
							<Name>Men's Fashion</Name>
						</LanguageData>
					</Languages>
				</Category>
			</Categories>
			<Vendors length="1">
				<Vendor id="0">
					<Name />
				</Vendor>
			</Vendors>
			<DisplayFacebookLink>TRUE_VALUE</DisplayFacebookLink>
			<DisplayFacebookLike>TRUE_VALUE</DisplayFacebookLike>
			<DisplayTwitterLink>TRUE_VALUE</DisplayTwitterLink>
			<TwoCheckoutId />
			<Available>TRUE_VALUE</Available>
			<Discontinued>FALSE_VALUE</Discontinued>
			<TrackInventory>TRACK_PRODUCT_BY_PRODUCT</TrackInventory>
			<InventoryLevel>24</InventoryLevel>
			<LowInventoryNotifyLevel>5</LowInventoryNotifyLevel>
			<InventoryNotified>INVENTORY_NOTIFICATION_NO</InventoryNotified>
			<Cost>
				<Amount>0.00</Amount>
			</Cost>
			<BundledProducts length="0" />
			<BundleDiscount>0</BundleDiscount>
			<Weight>
				<Amount>1.0000</Amount>
				<Units>KGS</Units>
			</Weight>
			<BoxWidth>0.00</BoxWidth>
			<BoxHeight>0.00</BoxHeight>
			<BoxLength>0.00</BoxLength>
			<BoxGirth>0.00</BoxGirth>
			<FirstClassMailType>USPS_FIRST_CLASS_MAIL_TYPE_PARCEL</FirstClassMailType>
			<ContainerType>USPS_CONTAINER_TYPE_RECTANGULAR</ContainerType>
			<FreightClass />
			<SouthEasternFreightClass />
			<ABFFreightClass />
			<UPSFreightClass />
			<UPSFreightNumberOfPieces>0</UPSFreightNumberOfPieces>
			<UPSFreightNumberOfHandlingUnits>0.00</UPSFreightNumberOfHandlingUnits>
			<UPSFreightPackaging />
			<MultiShipBox />
			<Weight2>
				<Amount>0.0000</Amount>
				<Units>KGS</Units>
			</Weight2>
			<Width2>0.00</Width2>
			<Height2>0.00</Height2>
			<Length2>0.00</Length2>
			<Girth2>0.00</Girth2>
			<FirstClassMailType2 />
			<ContainerType2 />
			<Weight3>
				<Amount>0.0000</Amount>
				<Units>KGS</Units>
			</Weight3>
			<Width3>0.00</Width3>
			<Height3>0.00</Height3>
			<Length3>0.00</Length3>
			<Girth3>0.00</Girth3>
			<FirstClassMailType3 />
			<ContainerType3 />
			<Weight4>
				<Amount>0.0000</Amount>
				<Units>KGS</Units>
			</Weight4>
			<Width4>0.00</Width4>
			<Height4>0.00</Height4>
			<Length4>0.00</Length4>
			<Girth4>0.00</Girth4>
			<FirstClassMailType4 />
			<ContainerType4 />
			<Weight5>
				<Amount>0.0000</Amount>
				<Units>KGS</Units>
			</Weight5>
			<Width5>0.00</Width5>
			<Height5>0.00</Height5>
			<Length5>0.00</Length5>
			<Girth5>0.00</Girth5>
			<FirstClassMailType5 />
			<ContainerType5 />
			<ShippingSurcharge>
				<Amount>0.50</Amount>
			</ShippingSurcharge>
			<FreightItem>
				<Amount>0.00</Amount>
			</FreightItem>
			<RelatedProducts length="0" />
			<NumberOfRelatedProductsToDisplay>0</NumberOfRelatedProductsToDisplay>
			<Size />
			<CallEmailForPricing>FALSE_VALUE</CallEmailForPricing>
			<CallEmailForPricingDisplayPrice>FALSE_VALUE</CallEmailForPricingDisplayPrice>
			<UserDefinedFields length="10">
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
				<UserDefinedField>
					<Label />
					<Value />
				</UserDefinedField>
			</UserDefinedFields>
			<PhotoGroups length="0" />
			<Taxable>TRUE_VALUE</Taxable>
			<Featured>FALSE_VALUE</Featured>
			<ShippingExempt>FALSE_VALUE</ShippingExempt>
			<EligibleForFreeShipping>FALSE_VALUE</EligibleForFreeShipping>
			<GiftWrappingAvailable>FALSE_VALUE</GiftWrappingAvailable>
			<EligibleForRewardPoints>TRUE_VALUE</EligibleForRewardPoints>
			<AllowFileUploads>FALSE_VALUE</AllowFileUploads>
			<EligibleForSubscriptionBilling>TRUE_VALUE</EligibleForSubscriptionBilling>
			<SubscriptionPrice>
				<Amount>0.00</Amount>
			</SubscriptionPrice>
			<UseEmailReminder>FALSE_VALUE</UseEmailReminder>
			<MinimumOrderQuantity>0</MinimumOrderQuantity>
			<MaximumOrderQuantity>0</MaximumOrderQuantity>
			<SubscriptionShippingFee>
				<Amount>0.00</Amount>
			</SubscriptionShippingFee>
			<AllowSubscriptionLimit>FALSE_VALUE</AllowSubscriptionLimit>
			<SubscriptionLimit>0</SubscriptionLimit>
			<Expiration>
				<UnixTimeStamp>-62169962400</UnixTimeStamp>
				<Day>30</Day>
				<Month>11</Month>
				<Year>-0001</Year>
				<Hour>00</Hour>
				<Minute>00</Minute>
				<Second>00</Second>
			</Expiration>
			<ProductType />
			<Isbn />
			<Shopzilla>
				<CategoryIdentification />
				<Condition>SHOPZILLA_CONDITION_TYPE_NEW</Condition>
			</Shopzilla>
			<ProductReviews />
			<UseRegularTeaserAndDescriptionForMobile>FALSE_VALUE</UseRegularTeaserAndDescriptionForMobile>
			<AllowLowerPriceRequest>FALSE_VALUE</AllowLowerPriceRequest>
			<CanonicalUrl>http://zynktest.corecommerce.com/Test-Product.html</CanonicalUrl>
			<SearchPriority />
			<ShowMsrpAndHideRetailPrice>FALSE_VALUE</ShowMsrpAndHideRetailPrice>
			<RequiresCustomOrderCompletePage>FALSE_VALUE</RequiresCustomOrderCompletePage>
			<DisplayAddThisButton>TRUE_VALUE</DisplayAddThisButton>
			<InternationalMailType />
			<InternationalMailType2 />
			<InternationalMailType3 />
			<InternationalMailType4 />
			<InternationalMailType5 />
			<NumberOfItemsPerBox>0</NumberOfItemsPerBox>
			<GoogleProductsDescription />
			<PasswordProtected>FALSE_VALUE</PasswordProtected>
			<SearchTerms />
			<MPN />
			<Brand />
			<GoogleProductsCategory>0</GoogleProductsCategory>
			<GoogleAvailability />
			<GoogleGender />
			<GoogleAgeGroup />
			<IncludeInBingProductFeed>TRUE_VALUE</IncludeInBingProductFeed>
			<IncludeInGoogleProductFeed>TRUE_VALUE</IncludeInGoogleProductFeed>
			<SlugStyle>auto</SlugStyle>
			<UsePinterest>FALSE_VALUE</UsePinterest>
			<EchoFreightClass />
			<EchoFreightPalletQuantity>0</EchoFreightPalletQuantity>
			<SoldInMultiplesOf>0</SoldInMultiplesOf>
			<treatVariantsAsMainLevelInvItemsInQb>N</treatVariantsAsMainLevelInvItemsInQb>
			<includeProductInAdditionToVariantsInQbOrderXml>Y</includeProductInAdditionToVariantsInQbOrderXml>
			<ThisProductHasAUniqueIdentifier>TRUE_VALUE</ThisProductHasAUniqueIdentifier>
		</Product>
	</List>
</Response>
```