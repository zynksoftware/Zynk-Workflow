---
slug: export-jobs-from-my-mobile-workers
title: Export Jobs from My Mobile Workers
---
The My Mobile Workers platform will allow their users to create jobs that contain a set of items required for completion. For example, if you were fitting a new lightswitch you would require the switch, screwdrivers and wiring.

There are two separate API calls that can be used in this task. If you have _Get Jobs By Statuses in Activity History_ set to true you can find the My Mobile Workers documentation available [here](https://docs.mymobileworkers.com/index.php?title=Get_Jobs_By_Current_Status). Alternatively, if you have the same setting set to false then you can find the My Mobile Workers documentation available [here](https://docs.mymobileworkers.com/index.php?title=Get_Jobs_By_Activity_Status).

This task will export jobs from My Mobile Workers in an XML format based on the settings you configure.

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

### Get Jobs By Statuses in Activity History
_Required_
download jobs based on the status changes during the completion of a job on the device. List of Job Statuses is available from the [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses)

### Job Status
_Optional_
Jobs with this status will be exported. List of Job Statuses is available from [MyMobileWorkers API documentation](https://docs.mymobileworkers.com/index.php?title=List_of_Job_Statuses)

## XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<MyMobileWorkersData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Jobs>
    <Job>
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
    </Job>
  </Jobs>
</MyMobileWorkersData>
```
