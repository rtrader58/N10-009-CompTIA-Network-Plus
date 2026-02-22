# Module 5 (Labs 1 - 13 ) Implementing Network Services
## Lab 1.2: Explore Three-Way Handshake in Wireshark
Complete this lab as follows: <br>
### Begin a Wireshark capture.
From the Favorites bar, select Wireshark. <br>
Maximize the window for easier viewing. <br>
Under Capture, select enp2s0. <br>
Select the blue fin to begin a Wireshark capture. <br>
Wait about 5 seconds, then select the red square to stop the Wireshark capture. <br>
### Apply a filter for tcp traffic from the computer at 192.168.0.45 and examine a [SYN] packet.
In the Apply a display filter field, type tcp and host 192.168.0.45 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
### Examine a [SYN] packet
Select a packet that includes [SYN] in the Info column. <br>
In the center pane, expand Internet Protocol Version 4 and Transmission Control Protocol. <br>
Select Questions, then answer Questions 1 and 2. <br>
Minimize the Lab Questions dialog. <br>
### Examine an [ACK, SYN] Packet.
Select a packet that includes [ACK, SYN] in the Info column. <br>
Select Questions, then answer Questions 3 and 4. <br>
Minimize the Lab Questions dialog. <br>
### Examine an [ACK] Packet.
Select a packet that includes [ACK] in the Info column. <br>
Select Questions, then answer Questions 5 and 6. <br>
## Lab 1.2: View Open Ports with netstat
### While completing this lab, use the following information:
![Example image](lab6_2_table.jpg) 
Complete this lab as follows: <br>
### Use Zenmap to scan for open ports running VNC.
From the Favorites bar, select Zenmap. <br>
In the Command field, type nmap -p 5900 192.168.0.0/24. <br>
Select Scan. <br>
From the results, find the computer with port 5900 open. <br>
### Uninstall VNC from the suspect computer.
From the top navigation tabs, select Floor 1 Overview. <br>
Under Support Office, select Support. <br>
From the Favorites bar, select Terminal. <br>
At the prompt, type netstat -l and press Enter to confirm the port is open on the machine. <br>
Type dnf list vnc and press Enter to find the package name. <br>
Type dnf erase libvncserver and press Enter. <br>
Press y and press Enter to uninstall the package. <br>
### Type netstat -l and press Enter to confirm that the port has been closed on the machine.
## Lab 6.3: Configure a DHCP Server
Complete this lab as follows: <br>
### Access the CorpDHCP Hyper-V server.
From Hyper-V Manager, select CORPSERVER. <br>
Resize the window to view all virtual machines. <br>
Double-click CorpDHCP to access the server. <br>
Maximize the CorpDHCP server for better viewing. <br>
### Access the DHCP New Scope Wizard.
From Server Manager's menu bar, select Tools > DHCP. <br>
Expand CorpDHCP.CorpNet.local. <br>
Right-click IPv4 and select New Scope. <br>
### Name the scope and configure the IP address range.
From the New Scope Wizard, select Next. <br>
In the Name field, enter Subnet1 and then select Next. <br>
Enter 192.168.0.20 in the Start IP address field. <br>
Enter 192.168.0.200 in the End IP address field. <br>
Make sure the length is set to 24. <br>
Make sure the subnet mask is 255.255.255.0 and then select Next. <br>
From the Add Exclusions and Delay window, select Next. <br>
Use the default lease duration and select Next. <br>
Make sure Yes, I want to configure these options now is selected and then select Next. <br>
### Configure the default gateway and DNS server.
In the IP address field, enter 192.168.0.5 as the default gateway address. <br>
Select Add and then select Next. <br>
In the IP address field, enter 163.128.78.93 as the DNS server address. <br>
Select Add and then select Next. <br>
From the WINS Servers window, select Next. <br>
A### ctivate the scope just created. <br>
Make sure Yes, I want to activate this scope now is selected and then select Next. <br>
Click Finish to close the wizard and create the scope. <br>
### Configure the laptop in the Lobby to obtain IP and DNS addresses automatically from the DHCP server.
From the top left, select Floor 1 Overview. <br>
Under Lobby, select Gst-Lap. <br>
In the notification area of the taskbar, right-click the network icon and select Network and Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment: and select Edit. <br>
Change the top drop down from Manual to Automatic (DHCP), then click Save. <br>
## Lab 6.4: Configure DHCP Server Options
Explanation <br>
While completing this lab, the 006 DNS Servers options are 192.168.0.11 and 192.168.10.11 (in that order). <br>
Complete this lab as follows: <br>
### Access the CorpDHCP virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Maximize the Hyper-V Manager window to view the available server. <br>
Right-click CorpDHCP and select Connect. <br>
### Configure the DHCP server options.
From Server Manager, select Tools > DHCP. <br>
Maximize the DHCP window for better viewing. <br>
Expand CorpDHCP.CorpNet.local > IPv4. <br>
Right-click Server Options and select Configure Options. <br>
Under Available Options, select the 006 DNS Servers. <br>
Enter 192.168.0.11 under IP Address. <br>
Select Add to add the IP address to the list. <br>
Under IP Address, enter 192.168.10.11 for the second server and then select Add. <br>
From the top pane, scroll down and select 015 DNS Domain Name. <br>
In the String value field, enter CorpNet.local. <br>
Select OK to save the options that you have defined. <br>
### Configure DHCP scope options.
Expand Scope [192.168.0.1] Subnet1. <br>
Right-click Scope Options and select Configure Options. <br>
Under Available Options, select 003 Router. <br>
Enter 192.168.0.5 under IP address. <br>
Select Add to add the IP address to the list. <br>
Select OK to save the options you defined. <br>
&emsp; Note: Server options apply to every scope on the server. Scope options override the server settings for a specific scope. <br>
