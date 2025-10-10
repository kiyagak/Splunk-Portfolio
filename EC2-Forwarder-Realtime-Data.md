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

## Create the Forwarder AWS EC2 Ubuntu Instance

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

## Download the Splunk Universal Forwarder onto the Forwarder EC2 Instance

Sign into Splunk and **copy the wget link** for the Linux 64-bit .deb package from [this page](https://www.splunk.com/en_us/download/universal-forwarder.html):

	wget -O splunkforwarder-10.0.1-c486717c322b-linux-amd64.deb "https://download.splunk.com/products/universalforwarder/releases/10.0.1/linux/splunkforwarder-10.0.1-c486717c322b-linux-amd64.deb"

<img width="1214" height="728" alt="image" src="https://github.com/user-attachments/assets/63cc7d82-2ef7-477d-bfc1-7e1acc9c7aab" />

Click the checkbox for the EC2 Ubuntu Forwarder instance and click **Connect** to connect to the EC2 Ubuntu Forwarder instance:

<img width="711" height="293" alt="image" src="https://github.com/user-attachments/assets/fe2cf929-40fc-42f1-91ae-22b678ad75e6" />

Click **Connect** once again:

<img width="1206" height="687" alt="image" src="https://github.com/user-attachments/assets/4f1afe00-1623-4b65-afa8-d2a9cce5dd8c" />

Change to the directory where Ubuntu log files are stored:

	cd /var/log

Run this command to see a detailed view about the log files:

	ls -la

We will **monitor the syslog log file** located at /var/log/syslog.  

## Ensure the Splunk service is Running

## Make an inputs.conf File for Splunk to Choose Log File(s) to Monitor

How inputs.conf should look like:

	[monitor://</path/of/file/abc.txt>]
	Disabled = 0
	Index = <index_name>

Make the inputs.conf file using the vi editor to tell Splunk which file to monitor:
	
	vi inputs.conf

Press I to enter insertable mode to add content to the file:

	# Splunk will monitor the file located at /var/sys/syslog on the system's file system:
	[monitor:///var/sys/syslog]
	
	# The stanza or the input is enabled:
	Disabled = 0
	
	# This specifies the index where events from that particular input are stored:
	Index = static-data

To save this file press the **ESC button** on your keyboard, then type in "**:wq**", then press the **ENTER button** on your keyboard.  

## Make an outputs.conf File to Tell Splunk Where to Send Data

How outputs.conf should look like:

	[tcpout]
	defaultGroup=my_indexers
	[tcpout:my_indexers]
	server=mysplunk_indexer1:9997

Make the outputs.conf file using the vi editor to tell Splunk which file to monitor:
	
	vi outputs.conf

Press I to enter insertable mode to add content to the file:

	# This stanza defines global settings for the TCP output processor used by Splunk forwarders to send data to receiving Splunk instances.  TCP does not have data loss because it is a reliable protocol compared to UDP:
	[tcpout]
	
	# This stanza specifies the default target group to which the forwarder sends its data automatically:
	defaultGroup=my_indexers
	
	# This stanza picks the target group called "my_indexers." This target group picks one or more receiving indexer servers that the forwarder will send data to via TCP:
	[tcpout:my_indexers]
	
	# This stanza specifies the exact receiving Splunk indexer server that the forwarder will send data to.  Use the public IPv4 address of the first Splunk AWS EC2 Ubuntu instance:
	server=[the first Splunk EC2 instance's public IPv4 address]:9997

To save this file press the **ESC button** on your keyboard, then type in "**:wq**", then press the **ENTER button** on your keyboard.  

## Enable Receiving on a Splunk Instance

## Restart Splunk Service on Forwarder(s)



# What I Learned
- Data ingestion can be verified by going to Apps -> Search & Reporting App -> Search <index=<index_name>>
- Successful data ingestion is confirmed by seeing data coming in after running the above search
