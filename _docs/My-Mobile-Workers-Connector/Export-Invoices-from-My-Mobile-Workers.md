---
slug: export-invoices-from-my-mobile-workers
title: Export Invoices from My Mobile Workers
---
The My Mobile Workers platform will allow their users to create an invoice for a job that has been completed and requires payment. For example, if a trades person finishes fitting a floor on site they will notify the company via the mobile app and they can raise an invoice.

The API documentation provided by My Mobile Workers is available [here](https://docs.mymobileworkers.com/index.php?title=Get_Invoices_Updated_Since).

This task will export invoices from My Mobile Workers in an XML format based on the settings you configure.

## Settings
### Connection
_Required_
The My Mobile Workers connection to use. See the [Connecting to My Mobile Workers](connecting-to-my-mobile-workers) article for more information.

### Date Modified
_Required_
Used when exporting modified records. The records modified on or after this date will be exported.

### DownloadAll
_Required_
Set to true to export all records and ignore the _Date Modified_ setting.

### Get Detailed Job Information Associated with Invoice
_Required_
Set to true to download detailed job information with each invoice. By default the My Mobile Workers invoice only contains the related job's number and external id.

### Job Status
_Optional_
Invoices with Jobs with this status will be exported. List of Job Statuses is available from the [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses)

## XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Invoices>
    <Invoice>
      <address>
        <line>63 random lane</line>
        <line>WA10 5ZD			</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2016/7/15/3510525/invoices/invoice_RBY59L_2016-07-15_16-29-00.pdf</file>
      <total>1.62</total>
      <notes />
      <job>
        <external_id>123456789</external_id>
        <type>Field Service</type>
        <date>2016-07-15</date>
        <time>16:25:00</time>
        <status>SAGE_UPDATE</status>
        <task />
        <duration>0</duration>
        <product />
        <created_at>2016-07-15T16:16:40+01:00</created_at>
        <job_number>RBY59L</job_number>
        <customer>
          <name>Joe Bloggs ABC</name>
          <created_at>2016-07-15T14:17:35+01:00</created_at>
          <contact_name>Joe Bloggs</contact_name>
          <address_1>63 random lane</address_1>
          <postcode>WA10 5ZD</postcode>
          <contact_number>01512143102</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>ChrisBaker1</username>
          <email>chris.baker@zynk.com</email>
          <color>7D8E60</color>
        </mobile_user>
        <contact_name>Joe Bloggs</contact_name>
        <address_1>63 random lane</address_1>
        <address_2 />
        <address_3 />
        <address_4 />
        <postcode>WA10 5ZD</postcode>
        <updated_at>2016-07-15T16:29:06+00:00</updated_at>
        <contact_number_1>01512143102</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2016-07-15T16:25:00+01:00</timeslot>
        <special_instructions />
        <notes />
        <fault />
        <repair_code>JC</repair_code>
        <repair_description>Job completed at premises</repair_description>
        <signee>John</signee>
        <satisfaction>3</satisfaction>
        <activities>
          <activity>
            <type>JOB_ARRIVED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:24:39+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Fault Details</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:25:06+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>PART_ADDED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:07+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Notes</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:13+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>JOB_FINISHED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:15+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>SIGNATURE_ADDED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:28+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>JOB_SIGNATURE_MISSING (customer - John)</type>
            <created_at>2016-07-15T15:27:30+01:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_COMPLETED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:28+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
        </activities>
        <parts>
          <part>
            <name>pb123</name>
            <description />
            <code>pb123</code>
            <created_at>2016-07-15T15:27:31+01:00</created_at>
            <quantity>1</quantity>
            <uuid>41bafe40-7607-417c-894d-1e490afe1b76</uuid>
          </part>
          <part>
            <name>Manrose MF100 W 100mm Fan</name>
            <description />
            <code>CN/44FE</code>
            <created_at>2016-07-15T17:14:46+01:00</created_at>
            <quantity>6</quantity>
          </part>
          <part>
            <name>Labour</name>
            <description />
            <code>lab</code>
            <created_at>2016-07-15T17:15:53+01:00</created_at>
            <quantity>1</quantity>
          </part>
        </parts>
        <checklists>
          <checklist>
            <created_at>2016-07-15T15:25:02+01:00</created_at>
            <name>Test Screen1</name>
            <id>922679</id>
            <failure>False</failure>
            <uuid>9db73628-402c-4cb1-8903-e106d83ea3d9</uuid>
            <order_id>5</order_id>
            <checklist_questions>
              <checklist_question>
                <type>text</type>
                <uuid>ad624d3e-5132-4999-b04d-f7c2821f0996</uuid>
                <answer>Average</answer>
                <question>General Condition of site</question>
                <order_id>2</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>rating</type>
                <uuid>33dcf9e1-7e0c-44ee-8898-64e14f8538c6</uuid>
                <answer>3.0</answer>
                <question>General Site Rating?</question>
                <order_id>5</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>69711c38-484e-4d44-b82e-1aea6008dc4b</uuid>
                <answer>yes</answer>
                <question>Risk assessment complete?</question>
                <order_id>0</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>a9f3b7f8-f6b9-46a7-9c1a-a71caa9603b3</uuid>
                <answer>yes</answer>
                <question>Method statement checked?</question>
                <order_id>1</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>025d6d9a-b0ff-4b22-8e46-cab8c34c148f</uuid>
                <answer />
                <question>Enter the Client's email address</question>
                <order_id>4</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>list</type>
                <uuid>61663730-7572-477e-9490-aac2a36037a7</uuid>
                <answer>XX111</answer>
                <question>Please confirm the model number</question>
                <order_id>3</order_id>
                <failed>False</failed>
              </checklist_question>
            </checklist_questions>
          </checklist>
        </checklists>
      </job>
      <created_at>2016-07-15T16:29:01+01:00</created_at>
      <updated_at>2016-07-15T17:29:01+01:00</updated_at>
      <job_status>JOB_COMPLETED</job_status>
      <valid>true</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>1.35</sub_total>
      <vat_total>0.27</vat_total>
      <care_of>Joe Bloggs</care_of>
      <invoice_number>RBY59L</invoice_number>
      <invoice_date>2016-07-15T00:00:00</invoice_date>
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>pb123</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>0.0</price>
          <unit_price>0.0</unit_price>
          <vat_amount>0.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
        <InvoiceItem>
          <description>Labour</description>
          <quantity>0.03</quantity>
          <vat_rate>20.0</vat_rate>
          <price>1.35</price>
          <unit_price>45.0</unit_price>
          <vat_amount>0.27</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>63 random lane</line>
        <line>WA10 5ZD			</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2016/7/15/3510525/invoices/invoice_RBY59L_2016-07-15_17-12-38.pdf</file>
      <total>1.62</total>
      <notes />
      <job>
        <external_id>123456789</external_id>
        <type>Field Service</type>
        <date>2016-07-15</date>
        <time>16:25:00</time>
        <status>SAGE_UPDATE</status>
        <task />
        <duration>0</duration>
        <product />
        <created_at>2016-07-15T16:16:40+01:00</created_at>
        <job_number>RBY59L</job_number>
        <customer>
          <name>Joe Bloggs ABC</name>
          <created_at>2016-07-15T14:17:35+01:00</created_at>
          <contact_name>Joe Bloggs</contact_name>
          <address_1>63 random lane</address_1>
          <postcode>WA10 5ZD</postcode>
          <contact_number>01512143102</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>ChrisBaker1</username>
          <email>chris.baker@zynk.com</email>
          <color>7D8E60</color>
        </mobile_user>
        <contact_name>Joe Bloggs</contact_name>
        <address_1>63 random lane</address_1>
        <address_2 />
        <address_3 />
        <address_4 />
        <postcode>WA10 5ZD</postcode>
        <updated_at>2016-07-15T16:29:06+00:00</updated_at>
        <contact_number_1>01512143102</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2016-07-15T16:25:00+01:00</timeslot>
        <special_instructions />
        <notes />
        <fault />
        <repair_code>JC</repair_code>
        <repair_description>Job completed at premises</repair_description>
        <signee>John</signee>
        <satisfaction>3</satisfaction>
        <activities>
          <activity>
            <type>JOB_ARRIVED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:24:39+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Fault Details</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:25:06+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>PART_ADDED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:07+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Notes</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:13+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>JOB_FINISHED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:15+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>SIGNATURE_ADDED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:28+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>JOB_SIGNATURE_MISSING (customer - John)</type>
            <created_at>2016-07-15T15:27:30+01:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_COMPLETED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:28+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
        </activities>
        <parts>
          <part>
            <name>pb123</name>
            <description />
            <code>pb123</code>
            <created_at>2016-07-15T15:27:31+01:00</created_at>
            <quantity>1</quantity>
            <uuid>41bafe40-7607-417c-894d-1e490afe1b76</uuid>
          </part>
          <part>
            <name>Manrose MF100 W 100mm Fan</name>
            <description />
            <code>CN/44FE</code>
            <created_at>2016-07-15T17:14:46+01:00</created_at>
            <quantity>6</quantity>
          </part>
          <part>
            <name>Labour</name>
            <description />
            <code>lab</code>
            <created_at>2016-07-15T17:15:53+01:00</created_at>
            <quantity>1</quantity>
          </part>
        </parts>
        <checklists>
          <checklist>
            <created_at>2016-07-15T15:25:02+01:00</created_at>
            <name>Test Screen1</name>
            <id>922679</id>
            <failure>False</failure>
            <uuid>9db73628-402c-4cb1-8903-e106d83ea3d9</uuid>
            <order_id>5</order_id>
            <checklist_questions>
              <checklist_question>
                <type>text</type>
                <uuid>ad624d3e-5132-4999-b04d-f7c2821f0996</uuid>
                <answer>Average</answer>
                <question>General Condition of site</question>
                <order_id>2</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>rating</type>
                <uuid>33dcf9e1-7e0c-44ee-8898-64e14f8538c6</uuid>
                <answer>3.0</answer>
                <question>General Site Rating?</question>
                <order_id>5</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>69711c38-484e-4d44-b82e-1aea6008dc4b</uuid>
                <answer>yes</answer>
                <question>Risk assessment complete?</question>
                <order_id>0</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>a9f3b7f8-f6b9-46a7-9c1a-a71caa9603b3</uuid>
                <answer>yes</answer>
                <question>Method statement checked?</question>
                <order_id>1</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>025d6d9a-b0ff-4b22-8e46-cab8c34c148f</uuid>
                <answer />
                <question>Enter the Client's email address</question>
                <order_id>4</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>list</type>
                <uuid>61663730-7572-477e-9490-aac2a36037a7</uuid>
                <answer>XX111</answer>
                <question>Please confirm the model number</question>
                <order_id>3</order_id>
                <failed>False</failed>
              </checklist_question>
            </checklist_questions>
          </checklist>
        </checklists>
      </job>
      <created_at>2016-07-15T17:12:38+01:00</created_at>
      <updated_at>2016-07-15T18:12:38+01:00</updated_at>
      <job_status>JOB_COMPLETED</job_status>
      <valid>true</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>1.35</sub_total>
      <vat_total>0.27</vat_total>
      <care_of>Joe Bloggs</care_of>
      <invoice_number>RBY59L1</invoice_number>
      <invoice_date>2016-07-15T00:00:00</invoice_date>
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>pb123</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>0.0</price>
          <unit_price>0.0</unit_price>
          <vat_amount>0.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
        <InvoiceItem>
          <description>Labour</description>
          <quantity>0.03</quantity>
          <vat_rate>20.0</vat_rate>
          <price>1.35</price>
          <unit_price>45.0</unit_price>
          <vat_amount>0.27</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>63 random lane</line>
        <line>WA10 5ZD			</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2016/7/15/3510525/invoices/invoice_RBY59L_2016-07-15_17-16-08.pdf</file>
      <total>563.93</total>
      <notes />
      <job>
        <external_id>123456789</external_id>
        <type>Field Service</type>
        <date>2016-07-15</date>
        <time>16:25:00</time>
        <status>SAGE_UPDATE</status>
        <task />
        <duration>0</duration>
        <product />
        <created_at>2016-07-15T16:16:40+01:00</created_at>
        <job_number>RBY59L</job_number>
        <customer>
          <name>Joe Bloggs ABC</name>
          <created_at>2016-07-15T14:17:35+01:00</created_at>
          <contact_name>Joe Bloggs</contact_name>
          <address_1>63 random lane</address_1>
          <postcode>WA10 5ZD</postcode>
          <contact_number>01512143102</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>ChrisBaker1</username>
          <email>chris.baker@zynk.com</email>
          <color>7D8E60</color>
        </mobile_user>
        <contact_name>Joe Bloggs</contact_name>
        <address_1>63 random lane</address_1>
        <address_2 />
        <address_3 />
        <address_4 />
        <postcode>WA10 5ZD</postcode>
        <updated_at>2016-07-15T16:29:06+00:00</updated_at>
        <contact_number_1>01512143102</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2016-07-15T16:25:00+01:00</timeslot>
        <special_instructions />
        <notes />
        <fault />
        <repair_code>JC</repair_code>
        <repair_description>Job completed at premises</repair_description>
        <signee>John</signee>
        <satisfaction>3</satisfaction>
        <activities>
          <activity>
            <type>JOB_ARRIVED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:24:39+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Fault Details</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:25:06+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>PART_ADDED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:07+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Notes</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:13+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>JOB_FINISHED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:15+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>SIGNATURE_ADDED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:28+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
          <activity>
            <type>JOB_SIGNATURE_MISSING (customer - John)</type>
            <created_at>2016-07-15T15:27:30+01:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_COMPLETED</type>
            <provider>gps</provider>
            <created_at>2016-07-15T16:27:28+01:00</created_at>
            <lat>54.98701378</lat>
            <lng>-1.61084657</lng>
            <accuracy>9</accuracy>
          </activity>
        </activities>
        <parts>
          <part>
            <name>pb123</name>
            <description />
            <code>pb123</code>
            <created_at>2016-07-15T15:27:31+01:00</created_at>
            <quantity>1</quantity>
            <uuid>41bafe40-7607-417c-894d-1e490afe1b76</uuid>
          </part>
          <part>
            <name>Manrose MF100 W 100mm Fan</name>
            <description />
            <code>CN/44FE</code>
            <created_at>2016-07-15T17:14:46+01:00</created_at>
            <quantity>6</quantity>
          </part>
          <part>
            <name>Labour</name>
            <description />
            <code>lab</code>
            <created_at>2016-07-15T17:15:53+01:00</created_at>
            <quantity>1</quantity>
          </part>
        </parts>
        <checklists>
          <checklist>
            <created_at>2016-07-15T15:25:02+01:00</created_at>
            <name>Test Screen1</name>
            <id>922679</id>
            <failure>False</failure>
            <uuid>9db73628-402c-4cb1-8903-e106d83ea3d9</uuid>
            <order_id>5</order_id>
            <checklist_questions>
              <checklist_question>
                <type>text</type>
                <uuid>ad624d3e-5132-4999-b04d-f7c2821f0996</uuid>
                <answer>Average</answer>
                <question>General Condition of site</question>
                <order_id>2</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>rating</type>
                <uuid>33dcf9e1-7e0c-44ee-8898-64e14f8538c6</uuid>
                <answer>3.0</answer>
                <question>General Site Rating?</question>
                <order_id>5</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>69711c38-484e-4d44-b82e-1aea6008dc4b</uuid>
                <answer>yes</answer>
                <question>Risk assessment complete?</question>
                <order_id>0</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>a9f3b7f8-f6b9-46a7-9c1a-a71caa9603b3</uuid>
                <answer>yes</answer>
                <question>Method statement checked?</question>
                <order_id>1</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>025d6d9a-b0ff-4b22-8e46-cab8c34c148f</uuid>
                <answer />
                <question>Enter the Client's email address</question>
                <order_id>4</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>list</type>
                <uuid>61663730-7572-477e-9490-aac2a36037a7</uuid>
                <answer>XX111</answer>
                <question>Please confirm the model number</question>
                <order_id>3</order_id>
                <failed>False</failed>
              </checklist_question>
            </checklist_questions>
          </checklist>
        </checklists>
      </job>
      <created_at>2016-07-15T17:16:09+01:00</created_at>
      <updated_at>2016-07-15T18:16:09+01:00</updated_at>
      <job_status>JOB_COMPLETED</job_status>
      <valid>true</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>469.94</sub_total>
      <vat_total>93.99</vat_total>
      <care_of>Joe Bloggs</care_of>
      <invoice_number>RBY59L2</invoice_number>
      <invoice_date>2016-07-15T00:00:00</invoice_date>
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>pb123</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>0.0</price>
          <unit_price>0.0</unit_price>
          <vat_amount>0.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
        <InvoiceItem>
          <description>Manrose MF100 W 100mm Fan</description>
          <quantity>6.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>419.94</price>
          <unit_price>69.99</unit_price>
          <vat_amount>83.99</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
        <InvoiceItem>
          <description>Labour</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>50.0</price>
          <unit_price>50.0</unit_price>
          <vat_amount>10.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>Unit 34</line>
        <line>Holystone Ind Estate</line>
        <line>Hebburn</line>
        <line>Tyne &amp; Wear</line>
        <line>NE31 1VB</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2017/2/3/4215205/invoices/invoice_N5MWC0_2017-02-03_10-08-40.pdf</file>
      <total>12.0</total>
      <notes />
      <job>
        <external_id>TEST1111</external_id>
        <type>Field Service</type>
        <date>2017-02-03</date>
        <time>10:00:01</time>
        <status>JOB_COMPLETED</status>
        <task />
        <duration>0</duration>
        <product>527</product>
        <created_at>2017-02-03T10:01:27+00:00</created_at>
        <job_number>N5MWC0</job_number>
        <customer>
          <external_id>ABS001</external_id>
          <name>ABS Garages Ltd</name>
          <created_at>2017-01-16T11:27:55+00:00</created_at>
          <contact_name>Mike Hall</contact_name>
          <address_1>Unit 34</address_1>
          <address_2>Holystone Ind Estate</address_2>
          <address_3>Hebburn</address_3>
          <address_4>Tyne &amp; Wear</address_4>
          <postcode>NE31 1VB</postcode>
          <contact_number>01912545909</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>ChrisBaker1</username>
          <email>chris.baker@zynk.com</email>
          <color>7D8E60</color>
        </mobile_user>
        <contact_name>Mike Hall</contact_name>
        <address_1>Unit 34</address_1>
        <address_2>Holystone Ind Estate</address_2>
        <address_3>Hebburn</address_3>
        <address_4>Tyne &amp; Wear</address_4>
        <postcode>NE31 1VB</postcode>
        <updated_at>2017-08-22T11:32:45+00:00</updated_at>
        <contact_number_1>01912545909</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2017-02-03T10:00:01+00:00</timeslot>
        <special_instructions />
        <fault />
        <repair_code>SC</repair_code>
        <parts>
          <part>
            <name>Test</name>
            <description>0001</description>
            <code>001</code>
            <created_at>2017-02-03T10:41:29+00:00</created_at>
            <quantity>1</quantity>
          </part>
        </parts>
      </job>
      <created_at>2017-02-03T10:08:41+00:00</created_at>
      <updated_at>2017-02-03T10:08:41+00:00</updated_at>
      <job_status>NEW</job_status>
      <valid>true</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>10.0</sub_total>
      <vat_total>2.0</vat_total>
      <care_of>Mike Hall</care_of>
      <invoice_number>N5MWC0</invoice_number>
      <invoice_date>2017-02-03T00:00:00</invoice_date>
      <account_no />
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>527</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>10.0</price>
          <unit_price>10.0</unit_price>
          <vat_amount>2.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>Timber Yard</line>
        <line>123 Prescot Way</line>
        <line>Alnwick</line>
        <line>Northumberland</line>
        <line>AL12 6GH</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/DRAFT</file>
      <total>83.99</total>
      <notes />
      <job>
        <type>Field Service</type>
        <date>2017-02-10</date>
        <time>11:55:51</time>
        <status>SAGE_UPDATE</status>
        <task />
        <duration>0</duration>
        <product />
        <created_at>2017-02-10T11:52:54+00:00</created_at>
        <job_number>358N57</job_number>
        <customer>
          <external_id>BBS001</external_id>
          <name>Bobs Building Supplies</name>
          <created_at>2017-01-16T11:27:57+00:00</created_at>
          <contact_name>Susan Livingstone</contact_name>
          <address_1>Timber Yard</address_1>
          <address_2>123 Prescot Way</address_2>
          <address_3>Alnwick</address_3>
          <address_4>Northumberland</address_4>
          <postcode>AL12 6GH</postcode>
          <contact_number>01983567123</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>zynktester</username>
          <email />
          <color>000aff</color>
        </mobile_user>
        <contact_name>Susan Livingstone</contact_name>
        <address_1>Timber Yard</address_1>
        <address_2>123 Prescot Way</address_2>
        <address_3>Alnwick</address_3>
        <address_4>Northumberland</address_4>
        <postcode>AL12 6GH</postcode>
        <updated_at>2017-02-10T11:56:45+00:00</updated_at>
        <contact_number_1>01983567123</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2017-02-10T11:55:51+00:00</timeslot>
        <signatures>
          <signature>
            <signature>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2017/2/10/4244142/signatures/10521935-00d0-48ab-be90-f163448f032c.png</signature>
            <created_at>2017-02-10T11:56:42+00:00</created_at>
            <signee>hehejd</signee>
            <signature_type>default_signature_capture</signature_type>
            <signature_name>customer</signature_name>
          </signature>
        </signatures>
        <special_instructions />
        <notes />
        <fault />
        <repair_code>JC</repair_code>
        <repair_description>Job completed at premises</repair_description>
        <signee>hehejd</signee>
        <satisfaction>4</satisfaction>
        <activities>
          <activity>
            <type>JOB_ARRIVED</type>
            <created_at>2017-02-10T11:53:58+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>Viewed Job Notes</type>
            <created_at>2017-02-10T11:54:46+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_FINISHED</type>
            <created_at>2017-02-10T11:56:33+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>SIGNATURE_ADDED</type>
            <created_at>2017-02-10T11:56:40+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_COMPLETED</type>
            <created_at>2017-02-10T11:56:40+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
        </activities>
        <parts>
          <part>
            <name>Manrose MF100 W 100mm Fan</name>
            <description>test</description>
            <code>PEN005</code>
            <created_at>2017-02-10T12:02:36+00:00</created_at>
            <quantity>1</quantity>
          </part>
        </parts>
        <checklists>
          <checklist>
            <created_at>2017-02-10T11:54:45+00:00</created_at>
            <name>Test Screen1</name>
            <id>1972694</id>
            <failure>False</failure>
            <uuid>a294e91c-b1b8-4b35-83f6-5c536334a9db</uuid>
            <order_id>5</order_id>
            <checklist_questions>
              <checklist_question>
                <type>text</type>
                <uuid>47fa8410-2f8b-41c3-a6db-cbdca42f728b</uuid>
                <answer>hzhshs@gdj.com</answer>
                <question>Enter the Client's email address</question>
                <order_id>4</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>0a54d944-a7d0-4163-8879-a839864f766d</uuid>
                <answer>pretty good</answer>
                <question>General Condition of site</question>
                <order_id>2</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>list</type>
                <uuid>a078af69-18bc-497d-b03d-4a6299ca65da</uuid>
                <answer>XX333</answer>
                <question>Please confirm the model number</question>
                <order_id>3</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>36243f30-9970-43b5-abf6-38794a2de435</uuid>
                <answer>yes</answer>
                <question>Risk assessment complete?</question>
                <order_id>0</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>rating</type>
                <uuid>dfac0e2b-3343-449f-b686-cf592b9a81d1</uuid>
                <answer>4.0</answer>
                <question>General Site Rating?</question>
                <order_id>5</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>a5724d77-5628-4440-a22a-bb6bff16a4d5</uuid>
                <answer>yes</answer>
                <question>Method statement checked?</question>
                <order_id>1</order_id>
                <failed>False</failed>
              </checklist_question>
            </checklist_questions>
          </checklist>
        </checklists>
      </job>
      <created_at>2017-02-14T16:27:34+00:00</created_at>
      <updated_at>2017-02-14T16:27:34+00:00</updated_at>
      <job_status>SAGE_UPDATE</job_status>
      <valid>false</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>69.99</sub_total>
      <vat_total>14.0</vat_total>
      <care_of>Susan Livingstone</care_of>
      <invoice_number>358N57</invoice_number>
      <invoice_date>2017-02-14T00:00:00</invoice_date>
      <account_no />
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>Manrose MF100 W 100mm Fan</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>69.99</price>
          <unit_price>69.99</unit_price>
          <vat_amount>14.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>Unit 34</line>
        <line>Holystone Ind Estate</line>
        <line>Hebburn</line>
        <line>Tyne &amp; Wear</line>
        <line>NE31 1VB</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/DRAFT</file>
      <total>12.0</total>
      <notes />
      <job>
        <external_id>TEST</external_id>
        <type>Field Service Demo</type>
        <date>2017-02-13</date>
        <time>09:20:14</time>
        <status>JOB_COMPLETED</status>
        <task>demo</task>
        <duration>0</duration>
        <product>demo</product>
        <created_at>2017-02-13T09:22:06+00:00</created_at>
        <job_number>2HDB3H</job_number>
        <customer>
          <external_id>ABS001</external_id>
          <name>ABS Garages Ltd</name>
          <created_at>2017-01-16T11:27:55+00:00</created_at>
          <contact_name>Mike Hall</contact_name>
          <address_1>Unit 34</address_1>
          <address_2>Holystone Ind Estate</address_2>
          <address_3>Hebburn</address_3>
          <address_4>Tyne &amp; Wear</address_4>
          <postcode>NE31 1VB</postcode>
          <contact_number>01912545909</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>ChrisBaker1</username>
          <email>chris.baker@zynk.com</email>
          <color>7D8E60</color>
        </mobile_user>
        <contact_name>Mike Hall</contact_name>
        <address_1>Unit 34</address_1>
        <address_2>Holystone Ind Estate</address_2>
        <address_3>Hebburn</address_3>
        <address_4>Tyne &amp; Wear</address_4>
        <postcode>NE31 1VB</postcode>
        <updated_at>2017-02-13T10:20:38+00:00</updated_at>
        <contact_number_1>01912545909</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2017-02-13T09:20:14+00:00</timeslot>
        <pre_job_details>
          <pre_job_detail>
            <invoice_number />
            <po_no />
          </pre_job_detail>
        </pre_job_details>
        <signatures>
          <signature>
            <signature>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2017/2/13/4250467/signatures/012f9c86-0069-4b18-80a8-507067c75507.png</signature>
            <created_at>2017-02-13T10:20:35+00:00</created_at>
            <signee>test</signee>
            <signature_type>default_signature_capture</signature_type>
            <signature_name>customer</signature_name>
          </signature>
        </signatures>
        <special_instructions />
        <notes />
        <fault>demo</fault>
        <repair_code>JC</repair_code>
        <repair_description>Job completed at premises</repair_description>
        <signee>test</signee>
        <satisfaction>5</satisfaction>
        <activities>
          <activity>
            <type>JOB_ARRIVED</type>
            <provider>gps</provider>
            <created_at>2017-02-13T09:22:28+00:00</created_at>
            <lat>50.6952560091164</lat>
            <lng>-2.10616350560343</lng>
            <accuracy>48</accuracy>
          </activity>
          <activity>
            <type>Viewed Job Notes</type>
            <provider>gps</provider>
            <created_at>2017-02-13T10:20:14+00:00</created_at>
            <lat>50.6951186518768</lat>
            <lng>-2.10606661330154</lng>
            <accuracy>64</accuracy>
          </activity>
          <activity>
            <type>JOB_FINISHED</type>
            <provider>gps</provider>
            <created_at>2017-02-13T10:20:18+00:00</created_at>
            <lat>50.6951186518768</lat>
            <lng>-2.10606661330154</lng>
            <accuracy>64</accuracy>
          </activity>
          <activity>
            <type>SIGNATURE_ADDED</type>
            <provider>gps</provider>
            <created_at>2017-02-13T10:20:34+00:00</created_at>
            <lat>50.6951186518768</lat>
            <lng>-2.10606661330154</lng>
            <accuracy>64</accuracy>
          </activity>
          <activity>
            <type>JOB_COMPLETED</type>
            <provider>gps</provider>
            <created_at>2017-02-13T10:20:34+00:00</created_at>
            <lat>50.6951186518768</lat>
            <lng>-2.10606661330154</lng>
            <accuracy>64</accuracy>
          </activity>
        </activities>
        <checklists>
          <checklist>
            <created_at>2017-02-13T09:58:01+00:00</created_at>
            <name>Test Screen1</name>
            <id>1979469</id>
            <failure>False</failure>
            <uuid>a2bcdf4c-0510-4744-b8b1-bb9a1343f59b</uuid>
            <order_id>5</order_id>
            <checklist_questions>
              <checklist_question>
                <type>rating</type>
                <uuid>edff87c6-8b5b-4d5d-82dd-bb74341b182a</uuid>
                <answer>5.0</answer>
                <question>General Site Rating?</question>
                <order_id>5</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>17cf1d95-bbfe-4e77-a4f6-99e06c0e6ccd</uuid>
                <answer>yes</answer>
                <question>Risk assessment complete?</question>
                <order_id>0</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>list</type>
                <uuid>51f6db1b-87b8-449e-875b-0f1dcd48b376</uuid>
                <answer>XX222</answer>
                <question>Please confirm the model number</question>
                <order_id>3</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>f58c9637-d948-43b2-83d7-38d5c61db3e8</uuid>
                <answer>no</answer>
                <question>Method statement checked?</question>
                <order_id>1</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>08429ebf-7586-4f31-a405-7b90b71318ad</uuid>
                <answer />
                <question>Enter the Client's email address</question>
                <order_id>4</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>0f0a97bc-2392-4437-bf4b-7e1f7de35561</uuid>
                <answer>test test test test test</answer>
                <question>General Condition of site</question>
                <order_id>2</order_id>
                <failed>False</failed>
              </checklist_question>
            </checklist_questions>
          </checklist>
        </checklists>
      </job>
      <created_at>2017-02-14T16:24:41+00:00</created_at>
      <updated_at>2017-02-14T16:24:41+00:00</updated_at>
      <job_status>JOB_COMPLETED</job_status>
      <valid>false</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>10.0</sub_total>
      <vat_total>2.0</vat_total>
      <care_of>Mike Hall</care_of>
      <invoice_number>2HDB3H</invoice_number>
      <invoice_date>2017-02-14T00:00:00</invoice_date>
      <account_no />
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>test</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>10.0</price>
          <unit_price>10.0</unit_price>
          <vat_amount>2.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>Unit 34</line>
        <line>Holystone Ind Estate</line>
        <line>Hebburn</line>
        <line>Tyne &amp; Wear</line>
        <line>NE31 1VB</line>
        <line>TEST</line>
        <line>YTE</line>
        <line>tye</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/DRAFT</file>
      <total>13.2</total>
      <notes>TEST NOTE</notes>
      <job>
        <external_id>TEST</external_id>
        <type>Field Service</type>
        <status>JOB_COMPLETED</status>
        <task />
        <duration>0</duration>
        <product>test</product>
        <created_at>2017-02-13T09:25:20+00:00</created_at>
        <job_number>MH660E</job_number>
        <customer>
          <external_id>ABS001</external_id>
          <name>ABS Garages Ltd</name>
          <created_at>2017-01-16T11:27:55+00:00</created_at>
          <contact_name>Mike Hall</contact_name>
          <address_1>Unit 34</address_1>
          <address_2>Holystone Ind Estate</address_2>
          <address_3>Hebburn</address_3>
          <address_4>Tyne &amp; Wear</address_4>
          <postcode>NE31 1VB</postcode>
          <contact_number>01912545909</contact_number>
          <Response />
        </customer>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <contact_name>Mike Hall</contact_name>
        <address_1>Unit 34</address_1>
        <address_2>Holystone Ind Estate</address_2>
        <address_3>Hebburn</address_3>
        <address_4>Tyne &amp; Wear</address_4>
        <postcode>NE31 1VB</postcode>
        <updated_at>2018-07-03T13:09:35+00:00</updated_at>
        <contact_number_1>01912545909</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <special_instructions />
        <fault />
      </job>
      <created_at>2018-07-02T15:25:20+01:00</created_at>
      <updated_at>2018-07-02T16:25:20+01:00</updated_at>
      <job_status>NEW</job_status>
      <valid>false</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>11.0</sub_total>
      <vat_total>2.2</vat_total>
      <care_of>Mike Hall</care_of>
      <invoice_number>MH660E</invoice_number>
      <invoice_date>2018-07-02T00:00:00</invoice_date>
      <account_no />
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>test aw</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>11.0</price>
          <unit_price>11.0</unit_price>
          <vat_amount>2.2</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
    <Invoice>
      <address>
        <line>12,</line>
        <line>L34 4AR</line>
      </address>
      <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/DRAFT</file>
      <total>60.01</total>
      <notes />
      <job>
        <external_id>1234</external_id>
        <type>Field Service</type>
        <date>2017-02-13</date>
        <status>JOB_COMPLETED</status>
        <task />
        <duration>0</duration>
        <product />
        <created_at>2017-02-13T11:22:18+00:00</created_at>
        <job_number>SCR2DR</job_number>
        <branch>
          <name>Zynk</name>
          <number>1</number>
          <created_at>2016-07-15T14:17:26+01:00</created_at>
          <contact_name>Chris Baker</contact_name>
          <contact_number>07841131687</contact_number>
          <contact_email>chris.baker@zynk.com</contact_email>
        </branch>
        <mobile_user>
          <username>zynktester</username>
          <email />
          <color>000aff</color>
        </mobile_user>
        <photos>
          <photo>
            <annotation />
            <file>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2017/2/13/4250966/photos/46305d40-7b69-48a9-be3e-0bfbf7337bea.jpeg</file>
            <created_at>2017-02-13T11:24:43+00:00</created_at>
            <jobNumber>SCR2DR</jobNumber>
            <photoType>job_photo</photoType>
          </photo>
        </photos>
        <contact_name>Test</contact_name>
        <address_1>12</address_1>
        <address_2 />
        <address_3 />
        <address_4 />
        <postcode>L34 4AR</postcode>
        <updated_at>2017-08-22T11:30:50+00:00</updated_at>
        <contact_number_1>01234567890</contact_number_1>
        <contact_number_2 />
        <contact_number_3 />
        <timeslot>2017-02-13T00:00:00+00:00</timeslot>
        <signatures>
          <signature>
            <signature>https://s3-eu-west-1.amazonaws.com/mmw-digital/2203/2017/2/13/4250966/signatures/01fd2e25-66af-4984-b259-15e0ad0aaafe.png</signature>
            <created_at>2017-02-13T11:24:41+00:00</created_at>
            <signee>test </signee>
            <signature_type>default_signature_capture</signature_type>
            <signature_name>customer</signature_name>
          </signature>
        </signatures>
        <special_instructions />
        <notes />
        <fault />
        <repair_code>SC</repair_code>
        <repair_description>Job completed at premises</repair_description>
        <signee>test </signee>
        <satisfaction>5</satisfaction>
        <items>
          <item>
            <external_id />
            <name>Labour</name>
            <category>
              <Response />
            </category>
            <category_id>
              <Response />
            </category_id>
            <type>D</type>
            <notes />
            <status>COMPLETED</status>
            <expected_quantity>1</expected_quantity>
            <other />
            <Response />
          </item>
          <item>
            <external_id>TEST</external_id>
            <name>test aw</name>
            <category>
              <Response />
            </category>
            <category_id>
              <Response />
            </category_id>
            <type>C</type>
            <notes>test aw</notes>
            <status>COMPLETED</status>
            <expected_quantity>1</expected_quantity>
            <other />
            <Response />
          </item>
        </items>
        <activities>
          <activity>
            <type>JOB_ARRIVED</type>
            <created_at>2017-02-13T11:22:47+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>PART_ADDED</type>
            <created_at>2017-02-13T11:24:11+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>Viewed Job Notes</type>
            <created_at>2017-02-13T11:24:31+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_FINISHED</type>
            <created_at>2017-02-13T11:24:32+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>SIGNATURE_ADDED</type>
            <created_at>2017-02-13T11:24:39+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
          <activity>
            <type>JOB_COMPLETED</type>
            <created_at>2017-02-13T11:24:39+00:00</created_at>
            <lat>0</lat>
            <lng>0</lng>
          </activity>
        </activities>
        <checklists>
          <checklist>
            <created_at>2017-02-13T11:23:27+00:00</created_at>
            <name>Test Screen1</name>
            <id>1980850</id>
            <failure>False</failure>
            <uuid>4dfef0b4-7d8e-4b9a-9a1e-7fd68ce668e0</uuid>
            <order_id>5</order_id>
            <checklist_questions>
              <checklist_question>
                <type>text</type>
                <uuid>c4909b49-4440-47ab-bcd1-2ce04185e88d</uuid>
                <answer />
                <question>Enter the Client's email address</question>
                <order_id>4</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>36b23839-dcd5-4e02-835f-0db551e7293a</uuid>
                <answer>yes</answer>
                <question>Method statement checked?</question>
                <order_id>1</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>rating</type>
                <uuid>23dfb836-0b87-413a-ba02-dcad8645d1ba</uuid>
                <answer>5.0</answer>
                <question>General Site Rating?</question>
                <order_id>5</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>list</type>
                <notes />
                <uuid>be49d648-bf4f-4255-9d44-aea22d92645c</uuid>
                <answer>XX111</answer>
                <question>Please confirm the model number</question>
                <order_id>3</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>text</type>
                <uuid>72d6055c-bb6e-4e33-9f62-31ed1dabfbb6</uuid>
                <answer>all ok</answer>
                <question>General Condition of site</question>
                <order_id>2</order_id>
                <failed>False</failed>
              </checklist_question>
              <checklist_question>
                <type>yesnona</type>
                <uuid>da2d82d7-78c4-44a6-bb39-9d5c4b2a3264</uuid>
                <answer>yes</answer>
                <question>Risk assessment complete?</question>
                <order_id>0</order_id>
                <failed>False</failed>
              </checklist_question>
            </checklist_questions>
          </checklist>
        </checklists>
      </job>
      <created_at>2017-02-14T16:26:02+00:00</created_at>
      <updated_at>2017-02-14T16:26:02+00:00</updated_at>
      <job_status>JOB_COMPLETED</job_status>
      <valid>false</valid>
      <payment_received>false</payment_received>
      <currency>gbp</currency>
      <sub_total>50.01</sub_total>
      <vat_total>10.0</vat_total>
      <care_of>Test</care_of>
      <invoice_number>SCR2DR</invoice_number>
      <invoice_date>2017-02-14T00:00:00</invoice_date>
      <account_no />
      <po_no />
      <invoice_items>
        <InvoiceItem>
          <description>Labour</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>50.0</price>
          <unit_price>50.0</unit_price>
          <vat_amount>10.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
        <InvoiceItem>
          <description>test aw</description>
          <quantity>1.0</quantity>
          <vat_rate>20.0</vat_rate>
          <price>0.01</price>
          <unit_price>0.01</unit_price>
          <vat_amount>0.0</vat_amount>
          <discount_enabled>false</discount_enabled>
          <discount_type>pc</discount_type>
          <discount_amount>0.0</discount_amount>
        </InvoiceItem>
      </invoice_items>
    </Invoice>
  </Invoices>
</MyMobileWorkersData>
```
