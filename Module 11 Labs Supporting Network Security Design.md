# Module 11 Labs: Supporting Network Security Design
## Lab 11.1: Configure a Screened Subnet (DMZ)
Complete this lab as follows: <br>
### Sign in to the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Configure an interface for the screened subnet.
From the pfSense menu bar, select Interfaces > Assignments. <br>
Select Add. <br>
Select OPT1. <br>
Select Enable interface. <br>
Change the Description field to DMZ.
Under General Configuration, use the IPv4 Configuration Type drop-down menu to select Static IPv4. <br>
Under Static IPv4 Configuration, in the IPv4 Address field, enter 172.16.1.1. <br>
Use the subnet mask drop-down menu to select 16. <br>
Select Save. <br>
Select Apply Changes. <br>
(Optional) Verify the change as follows: <br>
&emsp; * From the menu bar, select pfsense COMMUNITY EDITION. <br>
&emsp; * Under Interfaces, verify that the screened subnet is shown with the correct IP address. <br>
### Add a firewall rule to the screened subnet interface.
From the pfSense menu bar, select Firewall > Rules. <br>
Under the Firewall breadcrumb, select DMZ. (Notice that no rules have been created.) <br>
Under the Firewall breadcrumb, select LAN. <br>
Under the Actions column, select the copy icon (two files) for the rule with a source of LAN net. <br>
For the Action field, make sure Pass is selected. <br>
For the Interface field, use the drop-down menu to select DMZ. <br>
For Protocol, make sure it's set to Any. <br>
Under Source, use the drop-down menu to select DMZ net. <br>
Under Destination, make sure it is configured for any. <br>
Under Extra Options, change the description to Allow DMZ to any rule. (Is case sensitive.) <br>
Scroll to the bottom and select Save. <br>
Select Apply Changes. <br>
### Configure pfSense's DHCP server for the screened subnet interface.
From the menu bar, select Services > DHCP Server. <br>
Under the Services breadcrumb, select DMZ. <br>
Select Enable. <br>
Configure the Range field as follows: <br>
&emsp; * From: 172.16.1.100 <br>
&emsp; * To: 172.16.1.200 <br>
Scroll to the bottom and select Save. <br>
## Lab 11.2: Configure Screened Subnets
Complete this lab as follows: <br>
### Place the routers on the canvas and complete the connection from the Corp_Router to the InternetRouter.
In the tools tray, select the Routers icon. <br>
Drag the routers to the modeler canvas. <br>
In the tools tray, select the Create Link icon. <br>
Select the Corp_Router and then an open port. <br>
Select the Choke_Firewall and then an open port. <br>
Select the Choke_Firewall again and then select an open port. <br>
Select the Screening_Firewall and then an open port. <br>
Select the Screening_Firewall again and then select an open port. <br>
Select the InternetRouter and then an open port. <br>
### Use the additional switch to place the web and email servers in the screened subnet.
In the tools tray, select the Switches icon. <br>
Drag the Screened_Subnet_Switch to the modeler canvas. <br>
In the tools tray, make sure the Create Link tool is selected. <br>
Select the Screening_Firewall and then an open port. <br>
Select the Screened_Subnet_Switch and then an open port. <br>
In the tools tray, select the End Devices icon. <br>
Drag both servers to the modeler canvas. <br>
Select the Screened_Subnet_Switch and then an open port. <br>
Select Web_Server and then Ethernet. <br>
Select the Screened_Subnet_Switch again and then an open port. <br>
Select Email_Server and then Ethernet. <br>
## Lab 11.3: Implement Intrusion Prevention
Complete this lab as follows: <br>
### Sign in to the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Access Snort Global Settings.
From the pfSense menu bar, select Services > Snort. <br>
Under the Services breadcrumb, select Global Settings. <br>
### Configure the required rules to be downloaded.
Select Enable Snort VRT. <br>
In the Snort Oinkmaster Code field, enter 992acca37a4dbd7. You can copy and paste this from the scenario. <br>
Select Enable Snort GPLv2. <br>
Select Enable ET Open. <br>
### Configure the Sourcefire OpenAppID Detectors to be downloaded.
Under Sourcefire OpenAppID Detectors, select Enable OpenAppID. <br>
Select Enable RULES OpenAppID. <br>
### Configure when and how often the rules will be updated.
Under Rules Update Settings, use the Update Interval drop-down menu to select 4 DAYS. <br>
For Update Start Time, change to 00:10 (12:10 a.m. in 24-hour format). <br>
Select Hide Deprecated Rules Categories. <br>
### Configure Snort General Settings.
Under General Settings, use the Remove Blocked Hosts Interval drop-down menu to select 1 Day. <br>
Select Startup/Shutdown Logging. <br>
Select Save. <br>
### Configure the Snort Interface settings for the WAN interface.
Under the Services breadcrumb, select Snort Interfaces and then select Add. <br>
Under General Settings, make sure Enable interface is selected. <br>
For Interface, use the drop-down menu to select WAN (CorpNet_pfSense_L port 1). <br>
For Description, use Snort-WAN. <br>
Under Alert Settings, select Send Alerts to System Log. <br>
Select Block Offenders. <br>
Scroll to the bottom and select Save. <br>
### Start Snort on the WAN interface.
Under the Snort Status column, select the arrow to start Snort. <br>
Wait for a checkmark to appear, indicating that Snort was started successfully. <br>
## Lab 11.4: Scan for IoT Devices
Complete this lab as follows: <br>
### Access the CompTIA Vulnerability Scanner.
URL: http://192.168.0.52 <br>
Username: securityadmin <br>
Password: P@ssw0rd (with a zero, not the letter o) <br>
Select Sign In. <br>
### Scan the hosts at 192.168.0.1-192.168.0.100.
Select the Targets tab. <br>
Select Add Target. <br>
Name the target Floor 1 or a name of your choice.
In the Hosts field, enter 192.168.0.1-192.168.0.100, then select OK. <br>
Select the Tasks tab. <br>
Select Add Task. <br>
Enter Floor 1 task (or a name of your choice) for the Name. <br>
Select Floor 1 (or the name you chose) from the Add Target list box. Click OK <br>
On the right, select Run to start the scan. <br>
### View the Vulnerability Scanner report.
Select the Reports tab. <br>
Review the contents of the report under Floor 1 task (or the name you chose) and answer the questions. <br>
## Lab 11.5: Implement Physical Security
Complete this lab as follows: <br>
### Install the IP security cameras:
From the Shelf, expand CCTV Cameras. <br>
Drag the IP Security Camera from the Shelf to the highlighted circle inside the networking closet. <br>
Drag the IP Security Camera from the Shelf to the highlighted circle just outside the networking closet. <br>
### Install the smart card key readers:
From the Shelf, expand Door Locks. <br>
Drag a smart card reader from the Shelf to the highlighted location outside the building's front door. <br>
Drag a smart card reader from the Shelf to the highlighted location outside the networking closet's door. <br>
### Install the Restricted Access sign:
From the Shelf, expand Restricted Access Signs. <br>
Drag the Restricted Access sign from the Shelf to the networking closet door. <br>
### Place the visitor log on the lobby desk:
From the Shelf, expand Visitor Logs. <br>
Drag the visitor log from the Shelf to the lobby desk. <br>