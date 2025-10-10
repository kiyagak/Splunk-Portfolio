## Objective
The goal is to make Splunk ingest static data.  

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


