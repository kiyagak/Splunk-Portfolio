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
- file has no time stamp
- file has time stamp, but Splunk does not understand it

In this case, this file does not have a time stamp.  
