# Module 6 (Labs 1 - 13) Implementing Network Services
## Lab 1.2: Explore Three-Way Handshake in Wireshark
Complete this lab as follows: <br>
### Begin a Wireshark capture.
From the Favorites bar, select Wireshark. <br>
Maximize the window for easier viewing. <br>
Under Capture, select enp2s0. <br>
Select the blue fin to begin a Wireshark capture. <br>
Wait about 5 seconds, then select the red square to stop the Wireshark capture. <br>
### Apply a filter for tcp traffic from the computer at 192.168.0.45 and examine a SYN packet.
In the Apply a display filter field, type tcp and host 192.168.0.45 and press Enter. <br>
Look at the source and destination addresses of the filtered packets. <br>
### Examine a SYN packet
Select a packet that includes SYN in the Info column. <br>
In the center pane, expand Internet Protocol Version 4 and Transmission Control Protocol. <br>
Select Questions, then answer Questions 1 and 2. <br>
Minimize the Lab Questions dialog. <br>
### Examine an ACK, SYNPacket.
Select a packet that includeACK, SYN in the Info column. <br>
Select Questions, then answer Questions 3 and 4. <br>
Minimize the Lab Questions dialog. <br>
### Examine an ACK Packet.
Select a packet that includes ACK in the Info column. <br>
Select Questions, then answer Questions 5 and 6. <br>
## Lab 1.2: View Open Ports with netstat
### While completing this lab, use the following information:
![Example image](Images/tablelab6-2.jpg)  <br>
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
Expand Scope 192.168.0.1 Subnet1. <br>
Right-click Scope Options and select Configure Options. <br>
Under Available Options, select 003 Router. <br>
Enter 192.168.0.5 under IP address. <br>
Select Add to add the IP address to the list. <br>
Select OK to save the options you defined. <br>
&emsp; Note: Server options apply to every scope on the server. Scope options override the server settings for a specific scope. <br>
## Lab 6.5: Create DHCP Exclusions
Complete this lab as follows: <br>
### Access the CorpDHCP Hyper-V server.
From Hyper-V Manager, select CORPSERVER. <br>
Resize the window to view all virtual machines. <br>
Double-click CorpDHCP to access the server. <br>
### Exclude the IP address range.
From Server Manager's menu bar, select Tools > DHCP. <br>
Maximize the window for better viewing. <br>
Expand CorpDHCP.CorpNet.local > IPv4 > Scope 192.168.0.1 Subnet1. <br>
Right-click the Address Pool node and select New Exclusion Range. <br>
Enter 192.168.0.1 in the Start IP address field. <br>
Enter 192.168.0.29 in the End IP address field. <br>
Select Add. <br>
Select Close to close the Add Exclusion Range dialog. <br>
## Lab 6.6: Create DHCP Client Reservations
While completing this lab, use the following information: <br>
![Example image](images/lab6_6_table.jpg) <br>
Complete this lab as follows: <br>
### Access the CorpDHCP virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Maximize the Hyper-V Manager window to view the available server. <br>
Double-click CorpDHCP to connect to the server. <br>
### Configure the IP address.
From Server Manager, select Tools > DHCP. <br>
Maximize the window for better viewing. <br>
From the left pane, expand CorpDHCP.CorpNet.local > IPv4 > Scope 192.168.0.1 Subnet1. <br>
Right-click Reservations and select New Reservation. <br>
In the Reservation name field, enter a reservation name. <br>
In the IP address field, enter the IP address. <br>
In the MAC address field, enter the MAC address. <br>
Under Supported types, select DHCP only (as needed). <br>
Select Add to create the client reservation. <br>
Select Yes to the DHCP prompt. <br>
Repeat steps 2e - 2j for additional reservations. <br>
Select Close. <br>
## Lab 6.7: Configure Client Addressing for DHCP
Complete the following in order: <br>
###View the current connection status. <br>
From the Floor 1 Overview, under Office 2, select Office2. <br>
Perform one of the following: <br>
&emsp; Hover over the network icon in the system tray or <br>
&emsp; Select Start > Settings > Network & internet. <br>
Select Questions and answer question 1. <br>
Minimize the Lab Questions dialog. <br>
### Determine how the IP address is currently assigned.
From Network & internet settings, select Ethernet. <br>
Select Questions and answer question 2. <br>
Minimize the Lab Questions dialog. <br>
### Make any necessary changes to fix the connection issues.
To the right of the IP assignment, select Edit. <br>
In the Edit IP settings dialog, use the dropdown menu and select Automatic (DHCP). <br>
Select Save and notice Office2 has a connection. <br>
## Lab 6.8: Explore APIPA Addressing
Complete this lab as follows: <br>
### To answer questions:
Select the Questions button to open the Lab Questions dialog. <br>
Answer the specified question. <br>
Minimize the Lab Questions dialog. <br>
### Discover the Exec computer IP address, and explore connectivity to other computers.
From Executive Office, select Exec. <br>
Right-click Start and select Terminal (Admin). <br>
At the command prompt, type ipconfig and press Enter. <br>
Answer question 1. <br>
Type ping 192.168.0.5 (Default Gateway) and press Enter. <br>
Type ping Office1 and press Enter. <br>
Type ping Office2 and press Enter. <br>
Answer question 2. <br>
### Discover the Office1 computer IP address, and explore connectivity to other computers.
From the top left, select Floor 1 Overview and under Office 1, select Office1. <br>
Right-click Start and select Terminal (Admin). <br>
At the command prompt, type ipconfig and press Enter. <br>
Answer question 3. <br>
Type ping 192.168.0.5 and press Enter. <br>
Type ping Office2 and press Enter. <br>
Type ping Exec and press Enter. <br>
Answer question 4. <br>
### Discover the Office2 computer IP address, and explore connectivity to other computers.
Select Floor 1 Overview and under Office 2, select Office2. <br>
Right-click Start and select Terminal (Admin). <br>
At the command prompt, type ipconfig and press Enter. <br>
Answer question 5. <br>
Type ping 192.168.0.5 (Default Gateway) and press Enter. <br>
Type ping Office1 and press Enter. <br>
Type ping Exec and press Enter. <br>
Answer questions 6 and 7. <br>
### From CorpServer in Hyper-V Manager, activate CorpDHCP Subnet1.
Select Floor 1 Overview and under Networking Closet, select CorpServer. <br>
Maximize the Hyper-V Manager window. <br>
In Hyper-V Manager, select CORPSERVER. <br>
In the middle pane, under Virtual Machines, double-click CorpDHCP. <br>
From the Server Manager dialog menu, select Tools and then DHCP. <br>
In the DHCP dialog, from the left pane, expand CorpDHCP > IPv4. <br>
Notice that the folder icon for the Subnet1 Scope displays a red arrow, indicating it is not active. <br>
Right-click Scope [198.168.0.1] Subnet1 and select Activate. <br>
### Verify that the Office1 computer is receving an IP adddress from CorpDHCP.
Select Floor 1 Overview and under Office 1, select Office1. <br>
(Conditional) If a PowerSehll window is not already open, right-click Start and select Terminal (Admin). <br>
At the command prompt, type ipconfig and press Enter. <br>
Answer question 8. <br>
Type ping 192.168.0.5 and press Enter. <br>
Notice that Office1 can now communicate with the CorpDHCP server. <br>
## Lab 6.9: Explore APIPA Addressing in Network Modeler
### Explanation
&emsp; The router in this lab is configured for DHCP and has an assigned gateway of 192.168.1.1 on Port 0. <br>
Complete this lab as follows: <br>
### Add the computers to the canvas
In the tools tray, select End Devices. <br>
Drag all three computers to the modeler canvas. <br>
### Add the switch to the canvas
In the tools tray, select Switches. <br>
Drag the switch to the modeler canvas. <br>
### Connect the computers to the switch
In the tools tray, select Create Link. <br>
Click on Home-PC1 and select the Ethernet port. <br>
Click on the Switch and select an open port. <br>
Click on Home-PC2 and select the Ethernet port. <br>
Click on the switch and select an open port. <br>
Click on Home-Laptop and select the Ethernet port. <br>
Click on the switch and select an open port. <br>
Select Create Link to end the link tool. <br>
### Test connectivity and ping Home-PC2
Right-click Home-PC1 and select Launch Windows. <br>
Right-click Start and select Terminal (Admin). <br>
Type ipconfig /all and press Enter. <br>
Type ping Home-PC2 and press Enter. <br>
Answer questions 1 through 3. <br>
### Add the router to the canvas
In the upper left, select Network Modeler to return to the diagram. <br>
In the tools tray, select Routers. <br>
Drag the router to the canvas. <br>
### Connect the switch to the router
In the tools tray, select Create Link. <br>
Click on the Router and select Port 0. <br>
Click on the switch and select an open port. <br>
Select Create Link to end the link tool. <br>
### Renew the IP address for Home-PC1
Right-click Home-PC1 and select Launch Windows. <br>
Right-click Start and select Terminal (Admin) (if a terminal window is not already open). <br>
In the terminal window, type ipconfig /renew. <br>
Type ipconfig /all. <br>
Answer question 4. <br>
### Test connectivity by pinging Home-PC2 and the gateway
In the terminal window, type ping Home-PC2. <br>
In the terminal window, type ping 192.168.1.1. <br>
Answer question 5. <br>
### Renew the IP address for Home-PC2
In the upper left, select Network Modeler to return to the diagram. <br>
Right-click Home-PC2 and select Launch Windows. <br>
Right-click Start and select Windows PowerShell (Admin). <br>
In the terminal window, type ipconfig /renew. <br>
Type ipconfig /all. <br>
### Test connectivity by pinging Home-PC1 and the gateway
In the terminal window, type ping Home-PC1. <br>
In the terminal window, type ping 192.168.1.1. <br>
Answer questions 6. <br>
&emsp; Note: Being connected to the same switch physically doesn't guarantee that the devices are on the same network. A switch only forwards packets based on MAC addresses at the Layer 2 level. The IP addresses (Layer 3) determine which network a computer belongs to. While a switch facilitates communication between devices connected to it, it doesn't determine their logical network. <br>
## Lab 6.10: Configure a DHCP Relay Agent
Complete this lab as follows: <br>
### Add the DHCP Relay Agent routing protocol.
From Server Manager, select Tools > Routing and Remote Access. <br>
Expand IPv4. <br>
Right-click General and select New Routing Protocol. <br>
Select DHCP Relay Agent and then select OK. <br>
### Add and configure a Relay Agent interface.
From the left pane, right-click DHCP Relay Agent and select New Interface. <br>
Select NetTeam and then select OK. <br>
Make sure Relay DHCP packets is selected. <br>
Set the boot threshold to 0 (zero). <br>
Select OK. <br>
### Configure the DHCP Relay Agent properties to identify the DHCP server.
Right-click DHCP Relay Agent and select Properties. <br>
In the Server address field, enter 192.168.0.14 (the IP address of the DHCP server). <br>
Select Add and then select OK. <br>
### Renew the TCP/IP address and verify the connection.
From the top left, select Floor 1. <br>
Under Manager Office, select Exec2. <br>
Right-click Start and select Terminal (Admin). <br>
In PowerShell, type ipconfig. <br>
Notice that the current IP address is on the 169.254.0.0 network. <br>
In PowerShell, type ipconfig /renew and then press Enter. <br>
The computer should receive an address on the 192.168.10.0 network. <br>
From the taskbar, right-click the network icon, and select Network and Internet settings to view the connection status. <br>
## Lab 6.11: Add a DHCP Server on Another Subnet
Complete this lab as follows: <br>
### Access the CorpDHCP virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Maximize the Hyper-V Manager window to view the available server. <br>
Double-click CorpDHCP to connect to the server. <br>
#### Create an IPv4 scope on the CorpDHCP.
From Server Manager, select Tools > DHCP. <br>
Expand the CorpDHCP.CorpNet.local server node. <br>
Right-click IPv4 and then select New Scope. <br>
Select Next. <br>
In the Name field, enter Sales and then select Next. <br>
Enter 192.168.10.21 in the Start IP address field. <br>
Enter 192.168.10.199 in the End IP address field. <br>
Select Next > Next > Next > Next. <br>
From the Router (Default Gateway) dialog, enter an IP address of 192.168.10.5 and then select Add. <br>
Select Next. <br>
From the Domain Name and DNS Server dialog, add two DNS server addresses as follows: <br>
&emsp; * In the IP address field, enter 198.28.56.108 and then select Add. <br>
&emsp; * In the IP address field, enter 163.128.78.93 and then select Add. <br>
Select Next > Next.
From the Activate Scope dialog, make sure that Yes, I want to activate this scope now is selected and then select Next. <br>
Select Finish to complete the process of creating the DHCP scope. <br>
## Lab 6.12: Troubleshoot Address Pool Exhaustion
Complete this lab as follows: <br>
### Run ipconfig /all on the seven marketing computers.
Under Marketing Group A, select Marketing1. <br>
At the top right, select Questions, then review (but do not answer) questions 1-4. <br>
Minimize the Lab Questions dialog. <br>
Right-click Start and then select Windows PowerShell (Admin). <br>
Maximize the terminal window for better viewing. <br>
From the terminal window, type ipconfig /all and press Enter. <br>
Note the DHCP results (as outlined in questions 1-3). <br>
From the top left, select Floor 2. <br>
Repeat Steps 1d-1g for the remaining marketing computers (2-7). <br>
&emsp; * Select Terminal (Admin) instead of Windows PowerShell (Admin). <br>
At the top right, select Questions. <br>
Use the ethernet adapter information to answer questions 1-3. <br>
Minimize the Lab Questions dialog. <br>
### On the first floor, under the Networking Closet, view the properties of CorpServer subnet1 scope.
From the top left, select Building A. <br>
Under Building A, select Floor 1. <br>
Under Networking Closet, select CorpServer. <br>
Maximize the Hyper-V Manager window for better viewing. <br>
Under Hyper-V Manager, select CORPSERVER. <br>
Double-click CorpDHCP to connect to the CorpDHCP virtual server. <br>
From the Server Manager dialog menu, select Tools and then select DHCP. <br>
On the left, expand CorpDHCP.CorpNet.local > IPv4. <br>
Right-click Scope 192.168.0.1 Subnet1 and select Properties. <br>
At the top right, select Questions. <br>
Answer question 4 and then minimize the Lab Questions dialog. <br>
### Set the End IP address for the Scope [192.168.0.1] Subnet1 to 192.168.0.254.
From the Scope 192.168.0.1 Subnet1 Properties dialog, change the End IP address to 192.168.0.254. <br>
Select OK. <br>
### Select a computer with a connectivity issue and run ipconfig /renew.
From the top left, select Building A. <br>
Under Building A, select Floor 2. <br>
Select a computer that previously had an APIPA address. <br>
From the open terminal window, type ipconfig /renew and press Enter. <br>
At the top right, select Questions. <br>
Answer question 5. <br>
## Applied Live Lab 6.13: Troubleshoot Address Pool Exhaustion
Live lab environment <br>