## Objectives
The goals are to:
- have a Splunk package installed on another server
- install a universal forwarder on this server and ensure the Splunk service is running
- make a inputs.conf file to monitor log files to tell Splunk what file to monitor
- make an outputs.conf file to help Splunk know where to send data
- enable receiving on a Splunk instance
- restart Splunk service on forwarder(s)

## Install Splunk on Another Server

Splunk Enterprise has already been installed on another [AWS EC2 Ubuntu instance](https://github.com/kiyagak/Splunk-Portfolio/blob/main/EC2-Install.md).  

## System Requirements

 Within an AWS instance Splunk Enterprise has these system requirements:
- at least 2 vCPUs
- 4GB of memory
- 30 GiB of storage data

## Install a Universal Forwarder on This Server 

Launch a new instance in AWS by clicking **Launch Instances**:

<img width="1107" height="256" alt="image" src="https://github.com/user-attachments/assets/866be89c-cf8e-4c66-8ba2-7292fb640512" />

Name your instance and choose **Ubuntu** as the operating system:

<img width="835" height="772" alt="image" src="https://github.com/user-attachments/assets/40a9c09a-2a08-40cb-8507-170d9e159606" />

Choose an instance type that has at least 2 vCPUs and 4GB of memory:

<img width="828" height="869" alt="image" src="https://github.com/user-attachments/assets/72a3ace9-9028-4d14-9ffe-b814edacab35" />

Choose the existing key pair that was made on the first Splunk AWS EC2 Ubuntu instance:

<img width="838" height="344" alt="image" src="https://github.com/user-attachments/assets/360b642f-0bac-4785-9d0d-06cdc615f4f4" />

Choose the existing security group that was made on the first Splunk AWS EC2 Ubuntu instance:

<img width="839" height="410" alt="image" src="https://github.com/user-attachments/assets/a78af88a-27cc-4196-ba0b-e0f68d5127cd" />

Give the instance 30 GiB of storage, then click **Launch Intance**:

<img width="1153" height="625" alt="image" src="https://github.com/user-attachments/assets/c8c16e33-a142-4cb8-97de-315a1dd4287f" />

The instance was launched successfully:

<img width="509" height="290" alt="image" src="https://github.com/user-attachments/assets/5b174443-a2d4-48f1-a81a-fcea7ec87f51" />

## Ensure the Splunk service is Running

## Make an inputs.conf File for Splunk to Choose Log File(s) to Monitor

## Make an outputs.conf File to Tell Splunk Where to Send Data

## Enable Receiving on a Splunk Instance

## Restart Splunk Service on Forwarder(s)



# What I Learned
- Data ingestion can be verified by going to Apps -> Search & Reporting App -> Search <index=<index_name>>
- Successful data ingestion is confirmed by seeing data coming in after running the above search
