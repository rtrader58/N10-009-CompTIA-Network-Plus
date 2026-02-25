# Module 8 Labs: Supporting Network Management
## Live Lab 8.1: Backup and Restore Network Appliances
Live Lab <br>
## Lab 8.2: Update Firmware
Complete this lab as follows: <br>
### Import a new firmware image for the Cisco switch.
From the right pane, under Quick Access, select Upgrade Device Software. <br>
For File Name, select Choose File. <br>
Browse to and select C:\Sx300_Firmware\Sx300_FW-1.2.7.76.ros. <br>
Select Open. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
### Change the switch's active image to 1.2.7.76.
From the left pane, under Administration > File Management, select Active Image. <br>
For Active Image After Reboot, use the drop-down menu to select 1.2.7.76. <br>
Select Apply. <br>
### Reboot the switch to be able to start using the new firmware.
From the left pane, under Administration, select Reboot. <br>
From the right pane, select Reboot. <br>
Select OK. <br>
## Live Lab 8.3: Update Network Documentation
Live Lab <br>
## Lab 8.4: Scan Using Zenmap
Complete this labs as follows: <br>
### Scan the PartnerCorp servers for vulnerabilities.
From the Favorites bar, select Zenmap. <br>
At the prompt, type nmap 73.44.216.0/24. <br>
Select Scan. <br>
### Find the network vulnerabilities in the output and then answer the questions.
## Applied Live Lab 8.5: Perform Network Discovery
Live Lab <br>
## Applied Live La 8.6: Configure SNMP
Live Lab <br>
## Lab 8.7: Configure Logging in pfSense
Complete this lab as follows: <br>
### Sign in to the pfSense Management console.
From the taskbar, launch Google Chrome. Maximize the window for better viewing. <br>
Type 198.28.56.22 into the navigation bar, then press Enter. <br>
In the Username field, enter admin.
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Access the system log settings.
From the pfSense menu bar, select Status > System Logs. <br>
Answer Question 1. <br>
### Configure the general logging options.
Under the Status breadcrumb, select Settings. <br>
Set the GUI Log Entries field to 25 to show only 25 logs at a time in the GUI. <br>
Set the Log file size field to 250000 bytes (250 KB) to set the maximum size of each log file. <br>
### Configure remote logging.
Scroll to the bottom and, under Remote Logging Options, select Enable Remote Logging.
Make sure the options are set as follows: <br>
&emsp; * Source address: Default (any) <br>
&emsp; * IP protocol: IPv4 <br>
&emsp; * Remote log servers: 192.168.0.10 <br>
For Remote Syslog Contents, select the following: <br>
&emsp; * System Events <br>
&emsp; * Firewall Events <br>
Select Save. <br>
### View the results of the changes made to the number of logs shown.
Under the Status breadcrumb, select System. <br>
Answer Question 2. <br>
## Lab 8.8: Evaluate Event Logs in pfSense
Complete this lab as follows: <br>
### Sign in to the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Access pfSense logs.
From the pfSense menu bar, select Status > System Logs. <br>
Under the Status breadcrumb, select DHCP. <br>
Examine the entries. <br>
In the top right, select Questions. <br>
Answer Question 1. <br>
### Lab 8.9: Auditing Device Logs on a Cisco Switch
Complete this lab as follows: <br>
### Access the Log Settings for the switch.
From the left menu, expand Administration > System Log. <br>
Select Log Settings. <br>
### Enable Logging and Syslog Aggregator.
For Logging, select Enable. <br>
For Syslog Aggregator, select Enable. <br>
### Configure RAM and Flash memory logging:
Under RAM Memory Logging: <br>
&emsp; * Select Emergency, Alert, and Critical. <br>
&emsp; * Clear Error, Warning, Notice, Informational, and Debug. <br>
Under Flash Memory Logging: <br>
&emsp; * Select Emergency and Alert. <br>
&emsp; * Clear Critical, Error, Warning, Notice, Informational, and Debug. <br>
Select Apply. <br>
### Save the changes.
From the top menu bar, select Save. <br>
On the right, under Source File Name, make sure Running configuration is selected. <br>
On the right, under Destination File Name, make sure Startup configuration is selected. <br>
Under Copy/Save Configuration, select Apply. <br>
Select OK. <br>
Select Done. <br>
## Lab 8.10: Configure Logging on Linux
Complete this lab as follows: <br>
### Display the kernel message log from the current boot.
From the Favorites bar, select Terminal. <br>
At the prompt, type journalctl -k and press Enter. <br>
Type q to quit. <br>
### Display the system log in reverse order with the newest entries first.
Type journalctl -r and press Enter. <br>
Type q to quit. <br>
## Lab 8.11: View Event Logs
Complete this lab as follows: <br>
### View existing event logs.
Right-click Start and select Windows PowerShell (Admin). <br>
Maximize the window for easier viewing. <br>
At the prompt, type Get-Eventlog -logname * and press Enter. <br>
In the Entries column, notice the number of entries for the logs. <br>
### Clear the Application and System logs.
Type Clear-Eventlog -logname Application and press Enter. <br>
Type Clear-Eventlog -logname System and press Enter. <br>
Type Get-Eventlog -logname * and press Enter. <br>
The log entries for Application is zero. The log entries for System is one because another event occurred between when you cleared the log and viewed the entry list. <br>
## Live Lab 8.12: Configure Log Collection
Live Lab <br>
## Lab 8.13: Troubleshoot with Wireshark
Complete this lab as follows: <br>
### Begin a Wireshark capture.
From the Favorites bar, select Wireshark. <br>
Maximize the window for easier viewing. <br>
Under Capture, select enp2s0. <br>
Select the blue fin to begin a Wireshark capture. <br>
### Apply the net 192.168.0.0 filter.
In the Apply a display filter field, type net 192.168.0.0 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
Select the red square to stop the Wireshark capture. <br>
In the top right, select Questions. <br>
Answer Question 1. <br>
### Apply the host 192.168.0.45 filter.
Select the blue fin to begin a Wireshark capture. <br>
In the Apply a display filter field, type host 192.168.0.45 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
Answer Question 2. <br>
### Apply the ip.src==192.168.0.45 filter.
In the Apply a display filter field, type ip.src==192.168.0.45 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
Answer Question 3. <br>
### Apply the ip.dst==192.168.0.45 filter.
In the Apply a display filter field, type ip.dst==192.168.0.45 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
Answer Question 4. <br>
### Apply the tcp.port==80 filter.
In the Apply a display filter field, type tcp.port==80 and press Enter. <br>
Look in the Info column of the filtered packets. <br>
Answer Question 5. <br>
### Apply the eth contains 11:12:13 filter.
In the Apply a display filter field, type eth contains 11:12:13 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
Answer Question 6. <br>
### Apply the tcp contains password filter.
In the Apply a display filter field, type tcp contains password and press Enter. <br>
Select the red box to stop the Wireshark capture. <br>
From the bottom pane, locate the password. <br>
Answer Question 7. <br>