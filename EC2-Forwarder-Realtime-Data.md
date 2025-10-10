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

## Install a Universal Forwarder on This Server 

## Ensure the Splunk service is Running

## Make an inputs.conf File for Splunk to Choose Log File(s) to Monitor

## Make an outputs.conf File to Tell Splunk Where to Send Data

## Enable Receiving on a Splunk Instance

## Restart Splunk Service on Forwarder(s)



# What I Learned
- Data ingestion can be verified by going to Apps -> Search & Reporting App -> Search <index=<index_name>>
- Successful data ingestion is confirmed by seeing data coming in after running the above search
