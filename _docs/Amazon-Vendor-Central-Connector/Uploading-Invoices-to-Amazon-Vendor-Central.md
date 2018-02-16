---
slug: uploading-invoices-to-amazon-vendor-central
redirect_from: "/article/163-uploading-invoices-to-amazon-vendor-central"
title: Uploading Invoices to Amazon Vendor Central
---
This task will convert an input XML file containing invoices (INVOIC) to EDIFACT D96A format, and upload them to Amazon Vendor Central.

## Settings
### Connection
_Required_  
The Amazon Vendor Central Connection to use. See the [Connecting to Amazon Vendor Central](connecting-to-amazon-vendor-central) article if you require more information on how to create/manage connections.

### Test Mode
_Required_  
Set to true to save the generated EDI files to the workflow's data directory instead of uploading them to the SFTP. This can be useful for testing purposes, as it allows you to take a look at the converted EDI file.

### Fail File
_Required_  
The XML file to output any invoices which failed to upload to Amazon. The data is stored in the same format as the input file.

### Input File
_Required_  
The XML file containing the invoices to upload to Amazon. See below for an example.

### Success File
_Required_  
The XML file to output invoices which successfully to upload to Amazon. The data is stored in the same format as the input file. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below. Refer to the documentation provided by Amazon for an explanation of the segment and element tags. Note that in the XML, the segment tags are prefixed with `S_`, segment groups are prefixed with `G_`, composite element tags are prefixed with `C_` and value element tags are prefixed with `D_`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfInterchange>
	<INTERCHANGE xmlns="www.edifabric.com/edifact">
		<S_UNB>
			<C_S001>
				<D_0001_1>UNOA</D_0001_1>
				<D_0002_2>2</D_0002_2>
			</C_S001>
			<C_S002>
				<D_0004_1>0123456789012</D_0004_1>
				<D_0007_2>14</D_0007_2>
			</C_S002>
			<C_S003>
				<D_0010_1>5450534000000</D_0010_1>
				<D_0007_2>14</D_0007_2>
			</C_S003>
			<C_S004>
				<D_0017_1>150128</D_0017_1>
				<D_0019_2>1206</D_0019_2>
			</C_S004>
			<D_0020_5>IN150128120621</D_0020_5>
			<D_0032_10>EANCOM</D_0032_10>
		</S_UNB>
		<GROUPS>
			<GROUP>
				<MESSAGES>
					<MESSAGE>
						<Item>
							<M_INVOIC>
								<S_UNH>
									<D_0062_1>1</D_0062_1>
									<C_S009>
										<D_0065_1>INVOIC</D_0065_1>
										<D_0052_2>D</D_0052_2>
										<D_0054_3>96A</D_0054_3>
										<D_0051_4>UN</D_0051_4>
										<D_0057_5>EAN008</D_0057_5>
									</C_S009>
								</S_UNH>
								<S_BGM>
									<C_C002>
										<D_1001_1>380</D_1001_1>
									</C_C002>
									<D_1004_2>93774</D_1004_2>
									<D_1225_3>9</D_1225_3>
								</S_BGM>
								<S_DTM>
									<C_C507>
										<D_2005_1>137</D_2005_1>
										<D_2380_2>20150128</D_2380_2>
										<D_2379_3>102</D_2379_3>
									</C_C507>
								</S_DTM>
								<S_DTM>
									<C_C507>
										<D_2005_1>35</D_2005_1>
										<D_2380_2>20150129</D_2380_2>
										<D_2379_3>102</D_2379_3>
									</C_C507>
								</S_DTM>
								<G_NAD>
									<S_NAD>
										<D_3035_1>SU</D_3035_1>
										<C_C082>
											<D_3039_1>0123456789012</D_3039_1>
											<D_3055_3>9</D_3055_3>
										</C_C082>
										<C_C080>
											<D_3036_1>Zynk Software Ltd</D_3036_1>
										</C_C080>
										<C_C059>
											<D_3042_1>Nelson House</D_3042_1>
											<D_3042_2>Jesmond</D_3042_2>
										</C_C059>
										<D_3164_6>Newcastle Upon Type</D_3164_6>
										<D_3251_8>NE2 3AE</D_3251_8>
										<D_3207_9>GB</D_3207_9>
									</S_NAD>
									<G_RFF_2>
										<S_RFF_2>
											<C_C506_2>
												<D_1153_1>VA</D_1153_1>
												<D_1154_2>GB901045085</D_1154_2>
											</C_C506_2>
										</S_RFF_2>
									</G_RFF_2>
								</G_NAD>
								<G_NAD>
									<S_NAD>
										<D_3035_1>DP</D_3035_1>
										<C_C082>
											<D_3039_1>5450534000055</D_3039_1>
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
								<G_PAT>
									<S_PAT>
										<D_4279_1>1</D_4279_1>
										<C_C112>
											<D_2475_1>5</D_2475_1>
											<D_2009_2>7</D_2009_2>
											<D_2151_3>D</D_2151_3>
											<D_2152_4>60</D_2152_4>
										</C_C112>
									</S_PAT>
									<S_DTM_6>
										<C_C507_6>
											<D_2005_1>171</D_2005_1>
											<D_2380_2>20150128</D_2380_2>
											<D_2379_3>102</D_2379_3>
										</C_C507_6>
									</S_DTM_6>
									<S_PCD>
										<C_C501>
											<D_5245_1>7</D_5245_1>
											<D_5482_2>3</D_5482_2>
											<D_5249_3>13</D_5249_3>
										</C_C501>
									</S_PCD>
								</G_PAT>
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
									<S_IMD_2>
										<C_C273_2>
											<D_7008_4>Kids Cutlery Set</D_7008_4>
										</C_C273_2>
									</S_IMD_2>
									<S_QTY_2>
										<C_C186_2>
											<D_6063_1>47</D_6063_1>
											<D_6060_2>3</D_6060_2>
										</C_C186_2>
									</S_QTY_2>
									<G_MOA_2>
										<S_MOA_5>
											<C_C516_5>
												<D_5025_1>203</D_5025_1>
												<D_5004_2>21</D_5004_2>
												<D_6345_3>GBP</D_6345_3>
												<D_6343_4>4</D_6343_4>
											</C_C516_5>
										</S_MOA_5>
									</G_MOA_2>
									<G_PRI>
										<S_PRI>
											<C_C509>
												<D_5125_1>AAA</D_5125_1>
												<D_5118_2>7</D_5118_2>
												<D_5375_3>CT</D_5375_3>
												<D_5387_4>NTP</D_5387_4>
											</C_C509>
										</S_PRI>
									</G_PRI>
									<G_RFF_5>
										<S_RFF_7>
											<C_C506_7>
												<D_1153_1>ON</D_1153_1>
												<D_1154_2>T0000001</D_1154_2>
											</C_C506_7>
										</S_RFF_7>
									</G_RFF_5>
									<G_TAX_3>
										<S_TAX_3>
											<D_5283_1>7</D_5283_1>
											<C_C241_3>
												<D_5153_1>VAT</D_5153_1>
											</C_C241_3>
											<C_C243_3>
												<D_5278_4>20</D_5278_4>
											</C_C243_3>
										</S_TAX_3>
									</G_TAX_3>
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
									<S_IMD_2>
										<C_C273_2>
											<D_7008_4>Medium backpack in red</D_7008_4>
										</C_C273_2>
									</S_IMD_2>
									<S_QTY_2>
										<C_C186_2>
											<D_6063_1>47</D_6063_1>
											<D_6060_2>3</D_6060_2>
										</C_C186_2>
									</S_QTY_2>
									<G_MOA_2>
										<S_MOA_5>
											<C_C516_5>
												<D_5025_1>203</D_5025_1>
												<D_5004_2>30</D_5004_2>
												<D_6345_3>GBP</D_6345_3>
												<D_6343_4>4</D_6343_4>
											</C_C516_5>
										</S_MOA_5>
									</G_MOA_2>
									<G_PRI>
										<S_PRI>
											<C_C509>
												<D_5125_1>AAA</D_5125_1>
												<D_5118_2>10</D_5118_2>
												<D_5375_3>CT</D_5375_3>
												<D_5387_4>NTP</D_5387_4>
											</C_C509>
										</S_PRI>
									</G_PRI>
									<G_RFF_5>
										<S_RFF_7>
											<C_C506_7>
												<D_1153_1>ON</D_1153_1>
												<D_1154_2>T0000001</D_1154_2>
											</C_C506_7>
										</S_RFF_7>
									</G_RFF_5>
									<G_TAX_3>
										<S_TAX_3>
											<D_5283_1>7</D_5283_1>
											<C_C241_3>
												<D_5153_1>VAT</D_5153_1>
											</C_C241_3>
											<C_C243_3>
												<D_5278_4>20</D_5278_4>
											</C_C243_3>
										</S_TAX_3>
									</G_TAX_3>
								</G_LIN>
								<S_UNS>
									<D_0081_1>S</D_0081_1>
								</S_UNS>
								<S_CNT>
									<C_C270>
										<D_6069_1>2</D_6069_1>
										<D_6066_2>2</D_6066_2>
									</C_C270>
								</S_CNT>
								<G_MOA_4>
									<S_MOA_10>
										<C_C516_10>
											<D_5025_1>77</D_5025_1>
											<D_5004_2>61.2</D_5004_2>
											<D_6345_3>GBP</D_6345_3>
											<D_6343_4>4</D_6343_4>
										</C_C516_10>
									</S_MOA_10>
								</G_MOA_4>
								<G_TAX_5>
									<S_TAX_5>
										<D_5283_1>7</D_5283_1>
										<C_C241_5>
											<D_5153_1>VAT</D_5153_1>
										</C_C241_5>
										<C_C243_5>
											<D_5278_4>20</D_5278_4>
										</C_C243_5>
									</S_TAX_5>
									<S_MOA_11>
										<C_C516_11>
											<D_5025_1>124</D_5025_1>
											<D_5004_2>10.2</D_5004_2>
											<D_6345_3>GBP</D_6345_3>
											<D_6343_4>4</D_6343_4>
										</C_C516_11>
									</S_MOA_11>
									<S_MOA_11>
										<C_C516_11>
											<D_5025_1>125</D_5025_1>
											<D_5004_2>51</D_5004_2>
											<D_6345_3>GBP</D_6345_3>
											<D_6343_4>4</D_6343_4>
										</C_C516_11>
									</S_MOA_11>
								</G_TAX_5>
								<S_UNT>
									<D_0074_1>29</D_0074_1>
									<D_0062_2>1</D_0062_2>
								</S_UNT>
							</M_INVOIC>
						</Item>
					</MESSAGE>
				</MESSAGES>
			</GROUP>
		</GROUPS>
		<S_UNZ>
			<D_0036_1>0</D_0036_1>
			<D_0020_2>IN150128120621</D_0020_2>
		</S_UNZ>
	</INTERCHANGE>
</ArrayOfInterchange>
```