## Objective

The goal is to get AWS S3 data using the following steps:

- Create s3 bucket in aws
- Create Access key and Secret Access keys in AWS
- Login in to splunk web
- Create a new index to capture data in splunk
- Go to Apps — Find more Apps = Install AWS Add-on on splunk
  - Open App
- Add Account with Aws credentials
- Click on Create New Input > Custom Data Type > Generic S3
- Fill all the required fields and click on save
- Verify inputs has been created.
- Upload any csv file on s3 bucket.

## Notes

friend A needs to get parsel or champagne from friend B's house

they need
    address 
    access to house via key or biometrics
once they have these 2 things they can get the parsel/champagne bottle
    
    
for Splunk to pull data from S3 bucket it needs
    address tells Splunk where to fetch data = AWS cloud platform
    a key gives Splunk access to go inside AWS and fetch the data from S3 bucket
        S3 bucket works as storage drive
        
why not ingest data directly?
    putting in a drive one after another will make Splunk ingesting or pull it from AWS

cant ingest data for a file exceeding 500MB
only files/data at a max file size of 500MB can be ingested

## Create an AWS S3 Bucket

- Access your [AWS console](https://console.aws.amazon.com):
- Search "S3" in the search bar

      S3

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

- Log into Splunk Enterprise web interface using your admin username and password
- Click **Settings**
- Click **Indexes**
- Click **New Index**
- Name it as aws-data
- Click **Save**

we will ingest data from static-data index and not from AWS

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

## What I Learned
