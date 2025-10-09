Install Splunk on AWS EC2 Ubuntu Instance

Create a Free AWS account:
https://aws.amazon.com/free/

Splunk system requirements based on AWS EC2 instances:
- 2vCPUs
- at least 4GB RAM
- 30GiB of storage

Launch an Ubuntu EC2 instance:

<img width="1384" height="800" alt="image" src="https://github.com/user-attachments/assets/cc222858-073a-431f-815f-bc36cc51d86e" />

Choose an instance type that gives you 2 vCPUs and at least 4GiB of memory:

<img width="1385" height="800" alt="image" src="https://github.com/user-attachments/assets/d45c0e1d-e37c-4aad-a887-d2dccdbcd802" />

Create a new key pair:

<img width="1385" height="800" alt="image" src="https://github.com/user-attachments/assets/da96e928-31c9-4cdb-8d50-15a25017ec34" />
<img width="601" height="577" alt="image" src="https://github.com/user-attachments/assets/ebc3c3fc-bee5-4e38-8cb7-766460bce1d8" />
<img width="1280" height="346" alt="image" src="https://github.com/user-attachments/assets/83e5798b-becf-4e2b-94ec-5dfeb386afc2" />





Click Connect to launch the instance:




To make the Splunk web interface available, edit the inbound rules to allow TCP traffic from the Internet inbound to port 8000.


Select the security group:


Edit the inbound rules:



Allow TCP traffic from the Internet to inbound to port 8000 and click Save rules:

Click the checkbox for your Splunk-Server EC2 instance and click Launch Instances:


Create a Splunk account so you can copy the wget link to download the Splunk .deb package onto your Ubuntu AWS EC2 instance:


Install Splunk in your Splunk EC2 instance.   

Switch to root user:
	
	sudo su

Change to the directory where Splunk will be installed:

	cd /opt

Download the Splunk .deb package:

	wget -O splunk-10.0.1-c486717c322b-linux-amd64.deb "https://download.splunk.com/products/splunk/releases/10.0.1/linux/splunk-10.0.1-c486717c322b-linux-amd64.deb"

List the current directory's contents to show that the Splunk .deb package was successfully downloaded to the current directory:

	ls
	splunk-10.0.1-c486717c322b-linux-amd64.deb

Extract the Splunk .deb package:

	sudo dpkg -i splunk-10.0.1-c486717c322b-linux-amd64.deb

	Selecting previously unselected package splunk.
	(Reading database ... 71718 files and directories currently installed.)
	Preparing to unpack splunk-10.0.1-c486717c322b-linux-amd64.deb ...
	verify that this sytem has all the commands we will require to perform the preflight step
	no need to run the splunk-preinstall upgrade check
	Unpacking splunk (10.0.1) ...
	Setting up splunk (10.0.1) ...
	find: ‘/opt/splunk/lib/python3.7/site-packages’: No such file or directory
	complete

List the current directory's contents to show that a directory called "splunk" has been made after extracting the Splunk .deb package:

	ls
	splunk  splunk-10.0.1-c486717c322b-linux-amd64.deb

Change to the directory where the Splunk executable or script file is located:

	cd splunk/bin

Start Splunk and accept the license:
	
	./splunk start --accept-license

	This appears to be your first time running this version of Splunk.

	Splunk software must create an administrator account during startup. Otherwise, you cannot log in.
	Create credentials for the administrator account.
	Characters do not appear on the screen when you type in credentials.

Create a username and password to log in with:

	Please enter an administrator username: 
	Password must contain at least:
	   * 8 total printable ASCII character(s).
	Please enter a new password: 
	Please confirm new password: 
	Copying '/opt/splunk/etc/openldap/ldap.conf.default' to '/opt/splunk/etc/openldap/ldap.conf'.
	writing RSA key
	writing RSA key

	Moving '/opt/splunk/share/splunk/search_mrsparkle/modules.new' to '/opt/splunk/share/splunk/search_mrsparkle/modules'.

	Splunk> See your world.  Maybe wish you hadn't.

	Checking prerequisites...
		Checking http port [8000]: open
		Checking mgmt port [8089]: open
		Checking appserver port [127.0.0.1:8065]: open
		Checking kvstore port [8191]: open
		Checking configuration... Done.
		        Creating: /opt/splunk/var/lib/splunk
		        Creating: /opt/splunk/var/run/splunk
		        Creating: /opt/splunk/var/run/splunk/appserver/i18n
		        Creating: /opt/splunk/var/run/splunk/appserver/modules/static/css
		        Creating: /opt/splunk/var/run/splunk/upload
		        Creating: /opt/splunk/var/run/splunk/search_telemetry
		        Creating: /opt/splunk/var/run/splunk/search_log
		        Creating: /opt/splunk/var/spool/splunk
		        Creating: /opt/splunk/var/spool/dirmoncache
		        Creating: /opt/splunk/var/lib/splunk/authDb
		        Creating: /opt/splunk/var/lib/splunk/hashDb
		        Creating: /opt/splunk/var/run/splunk/collect
		        Creating: /opt/splunk/var/run/splunk/sessions
	New certs have been generated in '/opt/splunk/etc/auth'.
	New certs have been generated in '/opt/splunk/etc/auth'.
		Checking critical directories...        Done
		Checking indexes...
		        Validated: _audit _configtracker _dsappevent _dsclient _dsphonehome _internal _introspection _metrics _metrics_rollup _telemetry _thefishbucket history main summary
		Done
		Checking filesystem compatibility...  Done
		Checking conf files for problems...
		Done
		Checking default conf files for edits...
		Validating installed files against hashes from '/opt/splunk/splunk-10.0.1-c486717c322b-linux-amd64-manifest'
		All installed files intact.
		Done
	All preliminary checks passed.

	Starting splunk server daemon (splunkd)...  
	Using configuration from /opt/splunk/share/openssl3/openssl.cnf

	Warning: ignoring -extensions option without -extfile
	Certificate request self-signature ok

	Waiting for web server at http://127.0.0.1:8000 to be available............. Done

	If you get stuck, we're here to help.  
	Look for answers here: http://docs.splunk.com

You will have to get your EC2 instance's public IPv4 address to access the Splunk web interface:

	The Splunk web interface is at http://[AWS EC2 instance public IP]:8000

Find the public IPv4 address for your Splunk EC2 instance:


Browse to the web interface.  For example, if your Splunk EC2 instance has a public IPv4 address of 8.8.8.8 you will browse to http://8.8.8.8:8000.  Sign in using your username and password:

You have logged into Splunk Enterprise within an AWS Ubuntu EC2 instance.  
