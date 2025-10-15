## Objective

The goal is to get AWS S3 data into the Splunk web interface using the following steps:

- how to make an AWS S3 Bucket that will store our static file that will be ingested into Splunk
- allow the AWS S3 bucket data to be fed into Splunk
- search specifically for S3 bucket data within Splunk once ingested

## Splunk Max File Size of Ingested Files

Splunk can only ingest files or data with a maximum file size of 500MB. 

## Create an AWS S3 Bucket

- Access your [AWS console](https://console.aws.amazon.com):
- Search "S3" in the search bar
- Click **S3**
- Click **Create Bucket**

<img width="877" height="191" alt="image" src="https://github.com/user-attachments/assets/c754f350-5783-4b66-8f4c-4eda0dc9389f" />

<img width="925" height="348" alt="image" src="https://github.com/user-attachments/assets/25b80948-2dbe-4e0c-9366-7b4f637b9529" />

- Name your S3 bucket 
- Leave the other settings as default
- Uncheck **Block public access to bucket**
- Click the checkbox that says "**I acknowledge that the current settings might result in this bucket and the objects within becoming public.**"
- Click **Create Bucket**

<img width="735" height="444" alt="image" src="https://github.com/user-attachments/assets/b550611d-6146-4ba9-adc5-0e29bfd4eb08" />

<img width="980" height="580" alt="image" src="https://github.com/user-attachments/assets/d9f1c79f-3b2a-41f0-bc1f-bc0087fb2bf6" />

<img width="612" height="604" alt="image" src="https://github.com/user-attachments/assets/b3726d87-2a24-4972-b146-a43ec077d31e" />

Create your access key:
- In the top-right corner click your AWS account name
- Click **Security credentials**
- Click **Create access key**

<img width="1461" height="593" alt="image" src="https://github.com/user-attachments/assets/7f053e06-4d84-4038-aa15-8c200596cbbd" />

<img width="815" height="400" alt="image" src="https://github.com/user-attachments/assets/b91e6f14-4e0a-462a-9b53-1bba2adf270c" />

- Click the checkfor beside "**I understand creating a root access key is not a best practice, but I still want to create one.**"
  - This appears because I am using a root account since I do not recall my AWS account ID/alias or the IAM username
  - I am only proceeding using this method for the sake of following and demonstrating steps shown in the Splunk Bootcamp
- Click **Create access key**

<img width="994" height="491" alt="image" src="https://github.com/user-attachments/assets/32eb6c7a-66e5-4651-98ce-296169f38d4d" />

- If you plan to use the access key multiple times
  - click **Download .csv file** to store the access key onto your computer in a CSV file
  - or copy and store the access key in a text file or another format you like
- Click **Done**

<img width="999" height="783" alt="image" src="https://github.com/user-attachments/assets/15fd1c08-54de-4c7f-8dfa-4a54eca1f000" />

## Create a New Index

We will ingest data from the **static-data** index instead of AWS with these steps:

- Log into Splunk Enterprise web interface using your admin username and password
- Click **Settings**
- Click **Indexes**
- Click **New Index**
- Name it as aws-data
- Click **Save**

<img width="910" height="327" alt="image" src="https://github.com/user-attachments/assets/86e35912-0fbe-4864-b57f-c4bccf52322f" />

<img width="945" height="92" alt="image" src="https://github.com/user-attachments/assets/11ad7831-8666-418e-866b-9c4081d2644e" />

<img width="798" height="514" alt="image" src="https://github.com/user-attachments/assets/bfb2b5d3-7b02-4ce1-9354-9e990b28a0f5" />

## Install AWS in Splunk Enterprise

- Click Apps
- Click Find More Apps
- Search for "AWS" and press the Enter key on your keyboard
- Find **Splunk Add-on for Amazon Web Services (AWS)** and click **Install**
- Enter your Splunk.com username and password
- Click **Agree and Install**
- Click **Done** once it finishes installing.  

<img width="342" height="335" alt="image" src="https://github.com/user-attachments/assets/290b4e34-b52c-43c2-b358-a8010ac3c050" />

<img width="955" height="574" alt="image" src="https://github.com/user-attachments/assets/0aa4bd2e-01ba-413f-b191-8e1272e6d173" />

<img width="691" height="615" alt="image" src="https://github.com/user-attachments/assets/4927bb33-823a-4e60-bc57-b2d8593105d3" />

<img width="691" height="183" alt="image" src="https://github.com/user-attachments/assets/0f05e008-0abf-4cbf-9944-cfa41b816e58" />

<img width="685" height="306" alt="image" src="https://github.com/user-attachments/assets/d4c4200b-b552-4016-9cf7-7c2b0a65eed3" />

## Give Splunk Access to AWS

Add an account with the AWS credentials or access key
- Click **Done**
- Click **Open App**
- Click **Configuration**
- Click **Add**
- Name the account, such AWS-Splunk
- Enter the **key ID** generated in AWS
- Enter the **secret key** generated in AWS
- Click **Add**

<img width="942" height="323" alt="image" src="https://github.com/user-attachments/assets/90dc2661-9c18-42a9-944c-fb13fcec1b5d" />

<img width="798" height="439" alt="image" src="https://github.com/user-attachments/assets/91db7819-6d29-4b65-8149-278ca72c8219" />

<img width="942" height="323" alt="image" src="https://github.com/user-attachments/assets/2905309f-fd54-4c07-a100-b65bba6de99a" />

## Tell Splunk Where to Get the Data From

Tell Splunk where to pull the data from AWS S3 bucket using application-based input:

- Click **Inputs**
- Click **Create New Input**
- Click **Custom Data Type**
- Click **Generic S3**
- Name the input **s3-data-pulling**
- Select the AWS account you connected to Splunk
- Select **bootcamp-bucket-aws** as your S3 bucket
- Select **static-data** as your Index
- Click **Add**

<img width="955" height="650" alt="image" src="https://github.com/user-attachments/assets/cdfa2000-b3ff-44d6-8092-83a0efa24724" />

<img width="213" height="263" alt="image" src="https://github.com/user-attachments/assets/be565628-b6f2-44e0-b2fa-abc6e0c644fb" />

<img width="949" height="993" alt="image" src="https://github.com/user-attachments/assets/9f2742fc-97a8-478b-a3a9-8f9c46d487e7" />

Upload a file into the AWS S3 bucket:
- At the top in the search bar search "S3"
- click **S3**
- find the **bootcamp-bucket-aws** bucket
- Click **Upload**
- Click **Add files**
- Add the leads-10000.csv file
- Check the checkbox for the uploaded file
- Click **Upload**

<img width="660" height="179" alt="image" src="https://github.com/user-attachments/assets/9d989f34-7a14-4f5e-b0c8-23e55f844099" />

<img width="653" height="389" alt="image" src="https://github.com/user-attachments/assets/328408b7-91e2-49c3-88db-d71a8ae96bc4" />

<img width="653" height="431" alt="image" src="https://github.com/user-attachments/assets/b4241342-c111-4dc3-b6b3-3e1830875c9e" />

<img width="589" height="547" alt="image" src="https://github.com/user-attachments/assets/b9e41936-fa49-4be6-8978-f46ff9c8fc67" />

<img width="1192" height="803" alt="image" src="https://github.com/user-attachments/assets/083eb06b-9391-41b4-b3b6-df763d1b00c8" />

Verify that Splunk ingested the S3 bucket data:
- Check in Splunk to see if the data is being ingested or not
- Click **Apps**
- Click **Search & Reporting**
- Search the following to get data from the CSV file that was uploaded to the S3 bucket

      index="static-data" source="s3://bootcamp-bucket-aws/leads-10000.csv"

- Click the Search icon to show that Splunk ingested the S3 bucket data

<img width="342" height="301" alt="image" src="https://github.com/user-attachments/assets/a6b361d7-37b8-422d-8665-bf8bd80963fe" />

<img width="959" height="917" alt="image" src="https://github.com/user-attachments/assets/7b3a52ae-de46-49e2-9652-4213c49fb1d2" />

## What I Learned

I learned three key things from this project:
- how to make an AWS S3 Bucket that will store our static leads-10000.csv file that will be ingested into Splunk
- create access keys and secret keys to grant Splunk access to AWS to allow the AWS S3 bucket data to be fed into Splunk
- how to search specifically for S3 bucket data within Splunk
