# Splunk-Portfolio
Documentation of my use of Splunk, one of the most popular and widely used SIEM tools around.  It is a data platform that searches, monitors, and analyzes machine-generated data from almost any source, allowing real-time insights, visualization, alerting, and operational intelligence.  

## Install Splunk Enterprise on Kali Linux
Let’s install Splunk Enterprise on Kali Linux, a Debian-based distribution of Linux and log in to access the web interface.  

## Download and Install Splunk Enterprise
Open the Terminal. 
You can directly download the Splunk Enterprise .deb package that is most suitable for Kali Linux (Debian-based) via wget with this command:

	wget -O splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb "https://download.splunk.com/products/splunk/releases/9.3.0/linux/splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb"

After downloading, install it using:

	sudo dpkg -i splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb
	sudo apt-get install -f     # to fix any dependencies

## Start Splunk
After installation, move to Splunk bin directory so you can start Splunk:

	cd /opt/splunk/bin

Make sure **firewalls ports are open** to **make the Splunk web interface available**.  

Start Splunk and accept the license and make Splunk automatically answer "yes" to all yes/no prompts during startup:

	sudo ./splunk start --accept-license --answer=yes

Enter your administrator username and password when prompted in the Terminal.  
<img width="1431" height="914" alt="image" src="https://github.com/user-attachments/assets/8c53c5b4-467e-4d8c-b5fa-f459dd2922d3" />

## Log in to Splunk Enterprise
Access the web interface at http://kali:8000 and log in with the admin credentials you create during startup.
<img width="1431" height="914" alt="image" src="https://github.com/user-attachments/assets/f37ea09b-73dc-4427-b6df-d6104218f8c3" />
<img width="1431" height="914" alt="image" src="https://github.com/user-attachments/assets/e97a32e9-e19d-4b5c-abda-ca817775ac19" />

## What I Learned
I learned how to install Splunk Enterprise on Kali Linux, a Debian-based Linux distribution.  Splunk is one of the most popular and widely used SIEM tools around.  It is a data platform that searches, monitors, and analyzes machine-generated data from almost any source, allowing real-time insights, visualization, alerting, and operational intelligence.  
