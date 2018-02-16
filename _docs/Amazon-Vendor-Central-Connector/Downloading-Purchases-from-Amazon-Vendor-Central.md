---
slug: downloading-purchases-from-amazon-vendor-central
redirect_from: "/article/160-downloading-purchases-from-amazon-vendor-central"
title: Downloading Purchases from Amazon Vendor Central
---
This task will download purchase orders (ORDERS) files from Amazon Vendor Central, and convert them to XML format.

## Settings
### Connection
_Required_  
The Amazon Vendor Central Connection to use. See the [Connecting to Amazon Vendor Central](connecting-to-amazon-vendor-central) article if you require more information on how to create/manage connections.

### Output Directory
_Required_  
The folder to save the downloaded purchase order files to.

### Use XML Mapping
_Required_  
Set to true to use the built in mapping to convert the purchase order files to the Zynk XML format, or false to output the raw XML data.

### XML Mapping
_Optional_  
Settings for customising the built in mapping. See the  Auto Mapper article for more information.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file when the Use XML Mapping setting is set to false is shown below. Refer to the documentation provided by Amazon for an explanation of the segment and element tags. Note that in the XML, the segment tags are prefixed with `S_`, segment groups are prefixed with `G_`, composite element tags are prefixed with `C_` and value element tags are prefixed with `D_`.

``` xml
<?xml version="1.0" encoding="utf-8"?>
<INTERCHANGE xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="www.edifabric.com/edifact">
	<S_UNB>
		<C_S001>
			<D_0001_1>UNOA</D_0001_1>
			<D_0002_2>2</D_0002_2>
		</C_S001>
		<C_S002>
			<D_0004_1>5450534000000</D_0004_1>
			<D_0007_2>14</D_0007_2>
		</C_S002>
		<C_S003>
			<D_0010_1>0123456789012</D_0010_1>
			<D_0007_2>14</D_0007_2>
		</C_S003>
		<C_S004>
			<D_0017_1>150127</D_0017_1>
			<D_0019_2>0622</D_0019_2>
		</C_S004>
		<D_0020_5>3</D_0020_5>
		<C_S005>
			<D_0022_1 />
			<D_0025_2 />
		</C_S005>
		<D_0026_7 />
		<D_0029_8 />
		<D_0031_9>1</D_0031_9>
		<D_0032_10>EANCOM</D_0032_10>
	</S_UNB>
	<GROUPS>
		<GROUP>
			<MESSAGES>
				<MESSAGE>
					<Item>
						<M_ORDERS>
							<S_UNH>
								<D_0062_1>1</D_0062_1>
								<C_S009>
									<D_0065_1>ORDERS</D_0065_1>
									<D_0052_2>D</D_0052_2>
									<D_0054_3>96A</D_0054_3>
									<D_0051_4>UN</D_0051_4>
									<D_0057_5>EAN008</D_0057_5>
								</C_S009>
							</S_UNH>
							<S_BGM>
								<C_C002>
									<D_1001_1>220</D_1001_1>
								</C_C002>
								<D_1004_2>T0000001</D_1004_2>
								<D_1225_3>9</D_1225_3>
							</S_BGM>
							<S_DTM>
								<C_C507>
									<D_2005_1>137</D_2005_1>
									<D_2380_2>20150127</D_2380_2>
									<D_2379_3>102</D_2379_3>
								</C_C507>
							</S_DTM>
							<S_DTM>
								<C_C507>
									<D_2005_1>63</D_2005_1>
									<D_2380_2>20150203</D_2380_2>
									<D_2379_3>102</D_2379_3>
								</C_C507>
							</S_DTM>
							<S_DTM>
								<C_C507>
									<D_2005_1>64</D_2005_1>
									<D_2380_2>20150127</D_2380_2>
									<D_2379_3>102</D_2379_3>
								</C_C507>
							</S_DTM>
							<G_NAD>
								<S_NAD>
									<D_3035_1>BY</D_3035_1>
									<C_C082>
										<D_3039_1>5450534000024</D_3039_1>
										<D_3055_3>9</D_3055_3>
									</C_C082>
								</S_NAD>
							</G_NAD>
							<G_NAD>
								<S_NAD>
									<D_3035_1>SU</D_3035_1>
									<C_C082>
										<D_3039_1>0123456789012</D_3039_1>
										<D_3055_3>9</D_3055_3>
									</C_C082>
								</S_NAD>
							</G_NAD>
							<G_NAD>
								<S_NAD>
									<D_3035_1>DP</D_3035_1>
									<C_C082>
										<D_3039_1>5450534000116</D_3039_1>
										<D_3055_3>9</D_3055_3>
									</C_C082>
									<D_3207_9>GB</D_3207_9>
								</S_NAD>
							</G_NAD>
							<G_NAD>
								<S_NAD>
									<D_3035_1>IV</D_3035_1>
									<C_C082>
										<D_3039_1>5450534000055</D_3039_1>
										<D_3055_3>9</D_3055_3>
									</C_C082>
									<C_C080>
										<D_3036_1>AMAZON EU SARL</D_3036_1>
										<D_3036_2>5 RUE PLAETIS LUXEMBOURG</D_3036_2>
									</C_C080>
									<C_C059>
										<D_3042_1>CO PO BOX 4558</D_3042_1>
									</C_C059>
									<D_3164_6>SLOUGH</D_3164_6>
									<D_3251_8>SL1 0TX</D_3251_8>
									<D_3207_9>GB</D_3207_9>
								</S_NAD>
								<G_RFF_2>
									<S_RFF_2>
										<C_C506_2>
											<D_1153_1>VA</D_1153_1>
											<D_1154_2>GB727255821</D_1154_2>
										</C_C506_2>
									</S_RFF_2>
								</G_RFF_2>
							</G_NAD>
							<G_CUX>
								<S_CUX>
									<C_C504>
										<D_6347_1>2</D_6347_1>
										<D_6345_2>GBP</D_6345_2>
										<D_6343_3>9</D_6343_3>
									</C_C504>
								</S_CUX>
							</G_CUX>
							<G_LIN>
								<S_LIN>
									<D_1082_1>1</D_1082_1>
								</S_LIN>
								<S_PIA>
									<D_4347_1>5</D_4347_1>
									<C_C212_2>
										<D_7140_1>101-021</D_7140_1>
										<D_7143_2>SA</D_7143_2>
									</C_C212_2>
								</S_PIA>
								<S_QTY_3>
									<C_C186_3>
										<D_6063_1>21</D_6063_1>
										<D_6060_2>3</D_6060_2>
									</C_C186_3>
								</S_QTY_3>
								<G_PRI>
									<S_PRI>
										<C_C509>
											<D_5125_1>AAA</D_5125_1>
											<D_5118_2>7</D_5118_2>
										</C_C509>
									</S_PRI>
								</G_PRI>
							</G_LIN>
							<G_LIN>
								<S_LIN>
									<D_1082_1>2</D_1082_1>
								</S_LIN>
								<S_PIA>
									<D_4347_1>5</D_4347_1>
									<C_C212_2>
										<D_7140_1>030-5442R</D_7140_1>
										<D_7143_2>SA</D_7143_2>
									</C_C212_2>
								</S_PIA>
								<S_QTY_3>
									<C_C186_3>
										<D_6063_1>21</D_6063_1>
										<D_6060_2>3</D_6060_2>
									</C_C186_3>
								</S_QTY_3>
								<G_PRI>
									<S_PRI>
										<C_C509>
											<D_5125_1>AAA</D_5125_1>
											<D_5118_2>10</D_5118_2>
										</C_C509>
									</S_PRI>
								</G_PRI>
							</G_LIN>
							<G_LIN>
								<S_LIN>
									<D_1082_1>3</D_1082_1>
								</S_LIN>
								<S_PIA>
									<D_4347_1>5</D_4347_1>
									<C_C212_2>
										<D_7140_1>INVALID-SKU</D_7140_1>
										<D_7143_2>SA</D_7143_2>
									</C_C212_2>
								</S_PIA>
								<S_QTY_3>
									<C_C186_3>
										<D_6063_1>21</D_6063_1>
										<D_6060_2>3</D_6060_2>
									</C_C186_3>
								</S_QTY_3>
								<G_PRI>
									<S_PRI>
										<C_C509>
											<D_5125_1>AAA</D_5125_1>
											<D_5118_2>10</D_5118_2>
										</C_C509>
									</S_PRI>
								</G_PRI>
							</G_LIN>
							<G_LIN>
								<S_LIN>
									<D_1082_1>4</D_1082_1>
								</S_LIN>
								<S_PIA>
									<D_4347_1>5</D_4347_1>
									<C_C212_2>
										<D_7140_1>INVALID-SKU-2</D_7140_1>
										<D_7143_2>SA</D_7143_2>
									</C_C212_2>
								</S_PIA>
								<S_QTY_3>
									<C_C186_3>
										<D_6063_1>21</D_6063_1>
										<D_6060_2>3</D_6060_2>
									</C_C186_3>
								</S_QTY_3>
								<G_PRI>
									<S_PRI>
										<C_C509>
											<D_5125_1>AAA</D_5125_1>
											<D_5118_2>20</D_5118_2>
										</C_C509>
									</S_PRI>
								</G_PRI>
							</G_LIN>
							<G_LIN>
								<S_LIN>
									<D_1082_1>5</D_1082_1>
								</S_LIN>
								<S_PIA>
									<D_4347_1>5</D_4347_1>
									<C_C212_2>
										<D_7140_1>12006</D_7140_1>
										<D_7143_2>SA</D_7143_2>
									</C_C212_2>
								</S_PIA>
								<S_QTY_3>
									<C_C186_3>
										<D_6063_1>21</D_6063_1>
										<D_6060_2>3</D_6060_2>
									</C_C186_3>
								</S_QTY_3>
								<G_PRI>
									<S_PRI>
										<C_C509>
											<D_5125_1>AAA</D_5125_1>
											<D_5118_2>50</D_5118_2>
										</C_C509>
									</S_PRI>
								</G_PRI>
							</G_LIN>
							<S_UNS>
								<D_0081_1>S</D_0081_1>
							</S_UNS>
							<S_CNT>
								<C_C270>
									<D_6069_1>2</D_6069_1>
									<D_6066_2>5</D_6066_2>
								</C_C270>
							</S_CNT>
							<S_UNT>
								<D_0074_1>34</D_0074_1>
								<D_0062_2>1</D_0062_2>
							</S_UNT>
						</M_ORDERS>
					</Item>
					<Context>
						<Tag>ORDERS</Tag>
						<Version>D96A</Version>
						<Format>Edifact</Format>
					</Context>
				</MESSAGE>
			</MESSAGES>
		</GROUP>
	</GROUPS>
	<S_UNZ>
		<D_0036_1>1</D_0036_1>
		<D_0020_2>3</D_0020_2>
	</S_UNZ>
</INTERCHANGE>
```