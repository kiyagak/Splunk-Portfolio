## Objective
The goal is to make Splunk ingest static data on an AWS EC2 instance that has an Ubuntu operating system.  The data must be searchable and we must change the data fields to fields that are easily understood.  

## Download the Data Source

- [The page with sample CSV files for download](https://www.datablist.com/learn/csv/download-sample-csv-files#organizations-dataset)
- [Download the Organizations CSV file with 10,000 records](https://drive.google.com/uc?id=13p-box0F9kou4wE9AyeBNKMSfE767xT-&export=download)

## Add Data in Splunk

From the Splunk Enterprise homepage click **Add Data**:

<img width="1281" height="890" alt="image" src="https://github.com/user-attachments/assets/9d35c97d-f723-44a6-b02a-10ea17e178df" />

Under **Or get data in with the following methods** click **Upload**:

<img width="1282" height="864" alt="image" src="https://github.com/user-attachments/assets/de6a180a-e699-454f-babd-0a4c1d5f6479" />

Click **Select File** and choose the downloaded CSV file:

<img width="1282" height="865" alt="image" src="https://github.com/user-attachments/assets/83f31704-8440-4186-ad8b-cecc43292b6a" />

Click **Next**:

<img width="1281" height="563" alt="image" src="https://github.com/user-attachments/assets/c1299f76-fc63-4687-a182-6dfb8005deb9" />

Failed to parse timestamp error message appears for one of two reasons:
- the data source file has no time stamp
- the data source file has time stamp, but Splunk does not understand it

In this case, this data source file does not have a time stamp.  

<img width="1281" height="684" alt="image" src="https://github.com/user-attachments/assets/c1060d3f-0518-4d67-bdbd-7bcb11667938" />

We will tell Splunk to take the current time as the time stamp.  

Use the current time as the time stamp to remove the time stamp error message:
- Expand the **Timestamp** pane.
- Select **Current Time**.

<img width="1281" height="684" alt="image" src="https://github.com/user-attachments/assets/818de7f3-0d3a-4c48-8b9d-fec8e6d021e8" />

Click **Next**, then Click **Save**:

<img width="1281" height="528" alt="image" src="https://github.com/user-attachments/assets/5f1044c9-b073-47ae-8fd2-ad24adc934da" />

Click **Save** again:

<img width="1240" height="481" alt="image" src="https://github.com/user-attachments/assets/fc2a3054-1812-4442-8480-b489675f9a0f" />

Click **OK**:

<img width="1192" height="319" alt="image" src="https://github.com/user-attachments/assets/a132c5a7-63d9-4f72-b058-dd709805dba3" />

Create a new index:

<img width="1108" height="784" alt="image" src="https://github.com/user-attachments/assets/897862b4-f30f-43bb-90ec-c37a0e147e15" />

**Indexes** are the **data repository**. When the Splunk platform indexes raw data, it transforms the data into searchable events. Indexes reside in flat files on the indexer. 
    • **Events indexes** are the default type of index that can hold any type of data. 
    • **Metrics indexes** only hold metric data, which consists of a numerical measurement called a metric, the metric type, and one or more dimensions. 

Choose **Events** as the **Index Data Type** and click **Save**.  

<img width="1358" height="947" alt="image" src="https://github.com/user-attachments/assets/efac7a05-3d43-4f24-9f75-1fbfe76abffe" />

Click on **Review**:

<img width="1202" height="780" alt="image" src="https://github.com/user-attachments/assets/81ef62ba-969d-42bb-b08b-dace987b7dcf" />

Click **Submit**:  

<img width="884" height="309" alt="image" src="https://github.com/user-attachments/assets/feabc43f-1f70-45b2-81d8-93c5aeba1a17" />

Click **Start Searching**.  

<img width="921" height="535" alt="image" src="https://github.com/user-attachments/assets/e9cb4c83-7a16-42dc-8352-b09b90c87ffd" />

Click **Skip** when prompted for a tour of Splunk:

Under the **SELECTED FIELDS** area 

- Click the **source** field to view the data source:

<img width="1025" height="664" alt="image" src="https://github.com/user-attachments/assets/3ec07d98-4b40-4f46-b679-6aeb98a30a32" />

- Click the **sourcetype** field to view the data source type:

<img width="991" height="674" alt="image" src="https://github.com/user-attachments/assets/1e832f66-471a-4452-88eb-27203ce924c7" />

- Click the **host** field to view the host:

<img width="992" height="661" alt="image" src="https://github.com/user-attachments/assets/daaa0007-29f4-4de1-90b5-2854710f9fc9" />

Fields in machine data are name-value pairs, single or multivalued (e.g., IP, time, email), used to differentiate events and enable tailored searches.

Click on **All Fields**:

<img width="1102" height="717" alt="image" src="https://github.com/user-attachments/assets/ebd2c7c2-2436-4837-a650-038df61d902d" />

<img width="1287" height="565" alt="image" src="https://github.com/user-attachments/assets/e49d55bf-b0ac-466a-aa2b-d4530aaaafb0" />

Click the checkbox for the **Country** field to include it in the **SELECTED FIELDS**:

<img width="1068" height="379" alt="image" src="https://github.com/user-attachments/assets/f92fb2f7-0092-4d7e-985d-8b2ef5f74871" />

Click the x button just above the **Extract New Fields** button to close the dialog box and to show the Country field as part of the SELECTED FIELDS:

<img width="1476" height="213" alt="image" src="https://github.com/user-attachments/assets/f9e7cc42-11cc-49c6-aa04-efd3ecbfdc93" />

Click the **All Fields** button:

<img width="610" height="386" alt="image" src="https://github.com/user-attachments/assets/7bae210f-c80e-4cde-b25e-ef3bb6bdad60" />

Click on the **Extract New Fields** button to extract new fields:

<img width="1256" height="330" alt="image" src="https://github.com/user-attachments/assets/7897d312-3a05-4d07-bf37-c0057f1afb71" />

Select any event or row and click **Next**: 

<img width="987" height="843" alt="image" src="https://github.com/user-attachments/assets/1a21954e-bd51-4601-b2f3-1b2c90589d40" />

Delimiters vs. Regular Expression:

- Splunk delimiter extraction is suited for structured data with consistent separators like commas or spaces, quickly isolating fields by splitting on these delimiters.
- Regular expressions offer flexible pattern matching for unstructured or complex data, allowing custom and precise field extraction beyond simple delimiters.

Select **Delimiter** as the method because the comma delimits each field or value within the comma-separated value file.  Click **Next**:

<img width="987" height="667" alt="image" src="https://github.com/user-attachments/assets/47fc695e-9867-43e6-a3ee-4527a341b5ea" />

Choose **Comma** as the Delimiter:

Field names do not allow periods (.) or dashes (-).  

Click each field name header to nename the fields:  
- Rename field1 to Index
- Rename field2 to ID_Org
- Rename field3 to Company
- Rename field4 to Website
- Rename field5 to Country
- Rename field6 to Description
- Rename field7 to Year_Founded
- Rename field8 to Industry
- Rename field9 to Number_Employees

<img width="1100" height="837" alt="image" src="https://github.com/user-attachments/assets/67598406-b370-4a5b-8585-4a1fab57b4f0" />

<img width="1106" height="816" alt="image" src="https://github.com/user-attachments/assets/1d4701d0-3f29-4526-bd36-ee70a2ef4745" />

<img width="1101" height="854" alt="image" src="https://github.com/user-attachments/assets/9a0c6f67-40c3-468e-aace-55e32a25ba40" />

Click **Next**:

<img width="1017" height="630" alt="image" src="https://github.com/user-attachments/assets/b62264cc-b1d0-4885-a6b4-e701a6abc320" />

Name your report, then click **Finish**.  

Click **Explore the field I just created in Search**:

<img width="1010" height="359" alt="image" src="https://github.com/user-attachments/assets/cf9c18e2-2fd3-4b8a-9265-60577194a5e3" />

You will see the fields in the left pane showing what they have been renamed to:

<img width="1135" height="675" alt="image" src="https://github.com/user-attachments/assets/8f189caa-53d9-429b-b057-84ee0b354346" />

## What I Learned

- The process to add data in Splunk via the Enterprise homepage by selecting the Upload method and choosing the downloaded CSV file.
- Handling common issues such as the "Failed to parse timestamp" error by setting the timestamp to the current time when the data source lacks a timestamp or uses an incompatible format.
- Creating a new index in Splunk and understanding the difference between event indexes and metric indexes.
- How to rename fields from the CSV and pick which ones you want to keep using Splunk’s field extraction tools.
- When to use delimiter-based field extraction (easy with CSVs) versus regular expressions for more complicated data.
- The overall flow of going from raw data to searchable fields in Splunk, plus customizing your report to explore all the fields.

This project showed me how to load static CSV data into Splunk and how to change the setup to avoid timestamp errors and get the data ready for searching.  
