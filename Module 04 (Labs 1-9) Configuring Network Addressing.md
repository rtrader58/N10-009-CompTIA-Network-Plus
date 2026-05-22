# Module 4 Labs 4.1-4.9: Configuring Network Addressing

## Lab 4.1: Explore Packets and Frames
Complete this lab as follows: <br>
### Begin a Wireshark capture. <br>
From the Favorites bar, select Wireshark. <br>
Maximize the window for easier viewing. <br>
Under Capture, select enp2s0. <br>
Select the blue fin to begin a Wireshark capture. <br>
Wait about 5 seconds, then select the red square to stop the Wireshark capture. <br>
### Apply a filter for HTTP POST traffic.
In the Apply a display filter field, type http.request.method==POST and press Enter to show the HTTP POST requests. <br>
### Select a packet and answer the questions.
In the packet list pane, select one of the packets <br>
Select Questions <br>
In the packet details pane, expand the packet sections to view the packet details. <br>
Answer Questions 1 and 9. <br>
### Lab 4.1: Explore ARP in Wireshark
Complete this lab as follows: <br>
### Begin a Wireshark capture.
From the Favorites bar, select Wireshark. <br>
Maximize the window for easier viewing. <br>
Under Capture, select enp2s0. <br>
Select the blue fin to begin a Wireshark capture. <br>
Wait about 5 seconds,then select the red square to stop the Wireshark capture. <br>
### Apply the arp filter.
In the Apply a display filter field, type arp and press Enter. <br>
In the packet list pane, select a packet where the info starts with Who has. <br>
In the packet details pane, expand Address Resolution Protocol. <br>
Select Questions, then answer Questions 1 and 2. <br>
Minimize the Lab Questions dialog. <br>
### Apply the arp.dst.proto_ipv4==192.168.0.147 filter.
In the Apply a display filter field, type arp.dst.proto_ipv4==192.168.0.147 and press Enter. <br>
In the packet list pane, select a packet indicating where 192.168.0.47 is at. <br>
In the packet details pane, expand Ethernet and Address Resolution Protocol. <br>
Select Questions, then answer Questions 3 and 4. <br>
### Lab 4.3: Configure IP Addresses
Complete this lab as follows: <br>
### Access the properties for the NIC named Ethernet.
Right-click Start and then select Settings. <br>
Select Network & internet. <br>
From the right pane, select Ethernet. <br>
### Configure the IP version 4 TCP/IP settings for the Ethernet NIC.
For IP assignment, select Edit. <br>
Configure the IPv4 settings as follows: <br>
&emsp;* IP address: 192.168.0.254 <br>
&emsp;* Subnet mask: 255.255.255.0 <br>
&emsp;* Default gateway: 192.168.0.5 <br>
&emsp;* Preferred DNS: 163.128.78.93 <br>
&emsp;* Alternate DNS: 163.128.80.93 <br>
Select Save. <br>
### Configure the IP version 4 TCP/IP settings for the Ethernet 2 NIC.
From the left pane of the Settings app, select Network & internet. <br>
From the right pane, select Advanced network settings. <br>
Select More network adapter options. <br>
From the Network Connections window, right-click Ethernet 2 and then select Properties. <br>
Select Internet Protocol Version 4 (TCP/IPv4). <br>
Select Properties. <br>
Select Use the following IP address. <br>
Configure the Internet Protocol information as follows: <br>
&emsp;* IP address: 10.0.255.254 <br>
&emsp;* Subnet mask: 255.255.0.0 <br>
&emsp;* Default gateway: None <br>
&emsp;* Preferred DNS server: None <br>
Select OK. <br>
Select Close. <br>
### Ping the preferred DNS server assigned to the Ethernet NIC.
Right-click Start and select Terminal (Admin). <br>
From the PowerShell prompt, type one of the following: <br>
&emsp;* ping 163.128.78.93 <br>
&emsp;* ping 163.128.80.93 <br>
Press Enter. <br>
## Lab 4.4: Configure IP Addresses on Mobile Devices
Complete this lab as follows: <br>
### Access the iPad IP address settings dialog.
Select Settings. <br>
Select Wi-Fi. <br>
Under Networks, for CorpNet, select the information icon (an "i" in a circle). <br>
### Configure a static IP address.
From the right pane, select Static. <br>
Configure the IP information as follows: <br>
&emsp;* IP address: 192.168.0.85 <br>
&emsp;* Subnet mask: 255.255.255.0 <br>
&emsp;* Router (default gateway): 192.168.0.5 <br>
&emsp;* DNS: 192.168.0.11 <br>
### Join the iPad to the CorpNet network.
Select Join Network. <br>
In the Password field, type: @CorpNetWeRSecure!& <br>
Select Join. <br>
## Lab 4.5: Configure IP Addresses on Linux
Complete this lab as follows: <br>
### View the current state of the network card in the ITADMIN computer.
From the Favorites bar, select Terminal. <br>
At the prompt, type ip addr show and press Enter to view the current state of the network adapter. <br>
Type cd /etc/sysconfig/network-scripts and press Enter. <br>
Type ls and press Enter to view the files in this folder. (Take note of ifcfg-enp2s0, which is the configuration file for the network adapter.) <br>
### Configure the IP version 4 TCP/IP settings for the enp2s0 network connection.
Type nano ifcfg-enp2s0 and press Enter to edit the first adapter. <br>
Using the keyboard and arrow keys, configure the IP settings as follows: <br>
&emsp;* IPADDR=192.168.0.254 <br>
&emsp;* NETMASK=255.255.255.0 <br>
&emsp;* BROADCAST=192.168.0.255 <br>
&emsp;* GATEWAY=192.168.0.5 <br>
&emsp;* Remove the line that reads BOOTPROTO=dhcp. <br>
Type Ctrl + x to exit the editor. <br>
Type y to save the modified buffer to the disk. <br>
Press Enter to save the file using the default name. <br>
### Configure DNS.
At the prompt, type nano /etc/resolv.conf and press Enter to configure the DNS server addresses. <br>
Type nameserver 163.128.78.93 and press Enter to start a new line. <br>
Type nameserver 163.128.80.93 on the new line. <br>
Type Ctrl + x to exit the editor. <br>
Type y to save the modified buffer to the disk. <br>
Press Enter to save the file using the default name. <br>
Type ip link set enp2s0 down and press Enter to bring the interface down. <br>
Type ip link set enp2s0 up and press Enter to bring the interface back up with the new configuration. <br>
### Use ping to test the corrections to the enp2s0 interface card.
At the prompt, type ping -c4 192.168.0.5 and press Enter to confirm the connection to the network and default gateway. <br>
Type ping -c4 163.128.80.93 and press Enter to confirm the connection to the DNS server and the outside network. <br>
Type ping -c4 www.corpnet.xyz and press Enter to confirm DNS resolution. <br>
## Lab 4.6: Configure IP Networks and Subnets
Complete this lab as follows: <br>
### Gather IP information for Account2.
Right-click Account2 and select Launch Windows. <br>
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type ipconfig and press Enter. <br>
Select Questions. <br>
Answer questions 1 and 2. <br>
Minimize the lab questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Gather IP information for Marketing2.
Right-click Marketing2 and select Launch Windows. <br>
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type ipconfig and press Enter. <br>
Select Questions. <br>
Answer questions 3 and 4.
Minimize the lab questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Gather IP information for Sales2.
Right-click Sales2 and select Launch Windows. <br>
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type ipconfig and press Enter. <br>
Select Questions. <br>
Answer questions 5 and 6. <br>
Minimize the lab questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
Answer questions 7-9 regarding the IP information previously captured. <br>
Select Questions. <br>
### Answer questions 7 thru 9.
Minimize the lab questions window. <br>
### Use the ping command to test network connectivity from Marketing2 to Sales2.
Right-click Marketing2 and select Launch Windows. <br>
If the terminal is not already open, right-click Start and select Terminal (Admin). <br>
In the Terminal window, test the connection to Sales2 by typing ping 192.168.1.12 followed by Enter. <br>
Select Questions. <br>
Answer question 10. <br>
Minimize the lab questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Test network connectivity from Sales1.
Right-click Sales1 and select Launch Windows. <br>
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands and press Enter after each one. <br>
&emsp;* ping 192.168.1.12 <br>
&emsp;* ping 192.168.1.42 <br>
&emsp;* ipconfig <br>
Select Questions. <br>
Answer question 11. <br>
Minimize the lab questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Remove the connection between Switch1 and Switch2.
Right-click on the line indicating a link between switches 1 and 2. <br>
Select Remove. <br>
### Connect the switches to Router1.
In the tools tray select the Create Link icon. <br>
Select Router1 and select enp2s0. <br>
Select Switch1 and then select an open port. <br>
Select Router1 and select enp2s1. <br>
Select Switch2 and then select an open port. <br>
Select Router1 and select enp2s2. <br>
Select Switch3 and then select an open port. <br>
Select Create Link to end the link tool. <br>
### Test Connectivity from Account2.
Right-click Account2 and select Launch Windows. <br>
If the terminal is not already open, right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands and press Enter after each one. <br>
&emsp;* ping 192.168.1.12 <br>
&emsp;* ping 192.168.1.42 <br>
Select Questions. <br>
Answer question 12 <br>
## Lab 4.7: IPv4 Troubleshooting Tools
Complete this lab as follows: <br>
Right-click Start and select Terminal. <br>
Type tracert 12.34.58.102 and press Enter. <br>
&emsp; Make a note of the IP address of the first hop. <br>
View the network diagram by clicking Exhibits in the upper right. <br>
&emsp; Find the matching IP address from the first hop of the tracert command and make note of the name of the device. <br>
Close the network diagram. <br>
Select Questions in the upper right. <br>
Answer question 1. <br>
In the terminal, type ipconfig and press Enter. <br>
Find the field labeled Default Gateway. <br>
Answer question 2. <br>
In the terminal, type ping 163.128.80.93 and press Enter. <br>
In the terminal, type ping 163.128.78.93 and press Enter. <br>
## Lab 4.8: IPv4 Troubleshooting tools for Linux
Complete this lab as follows: <br>
### Locate the IP address of the external DNS server.
From the Favorites bar, select Terminal. <br>
From the top right, select Questions. <br>
From the top right, select Exhibits. <br>
Answer Question 1. <br>
Close the exhibit. <br>
### Find the route to the external DNS server.
From the prompt, type traceroute 163.128.78.93 or traceroute 163.128.80.93 and press Enter. <br>
Answer Questions 2 through 5. <br>
### Find the route to a remote computer.
From the prompt, type traceroute 10.10.20.10 and press Enter. <br>
Answer Questions 6 and 7. <br>
## Lab 4.9: Use IPv4 Test Tools
Complete this lab as follows: <br>
### Check the networking configuration of a Windows workstation.
Right-click Start and select Terminal (Admin). <br>
Type ipconfig and press Enter. <br>
In the top right, select Questions and answer question 1. <br>
Minimize the Lab Questions window. <br>
Enter the command ipconfig /all and press Enter. <br>
Select Questions and answer questions 2 and 3. <br>
Minimize the Lab Questions window. <br>
### Use ping and tracert to explore a Windows workstation's network connectivity.
At the Terminal prompt, type ping 192.168.0.5 and press Enter to verify that the default gateway is reachable. <br>
Type tracert rmksupplies.com and press Enter to map out the hops to the remote host. <br>
Select Questions and answer question 4. <br>
Minimize the Lab Questions window. <br>
### Connect to a Linux workstation and see how its networking is configured.
In the upper left, select Network Modeler. <br>
Right-click the Linux machine named Support and select Launch Linux. <br>
From the Favorites, select Terminal. <br>
Type ip a and press Enter. <br>
Select Questions and answer question 5. <br>
Minimize the Lab Questions window. <br>
### Use ping and traceroute to explore a Linux workstation's network connectivity.
Type route and press Enter to find the default route (gateway). <br>
Type ping -c4 192.168.0.5 and press Enter. The gateway is reachable. <br>
Type traceroute rmksupplies.com and press Enter. Note the number of hops. <br>
Select Questions and answer question 6. Compare the answer from question 4 to question 6. <br>
&emsp; How and why do they compare? <br>
Minimize the Lab Questions window. <br>
### Look at the Network Modeler canvas and the Exhibit to explain the network.
In the upper left, select Network Modeler. <br>
Trace the traffic from the machine to the ISP_Internet_Router (4 hops) <br>.
&emsp; How do the ping and tracert/traceroute commands help you to understand the layout of a network? <br>
## Lab 4.10: Configure an IPv6 Address
Complete this lab as follows: <br>
### Access the Network Connections window.
Right-click Start and then select Settings. <br>
Select Network & Internet. <br>
From the right pane, select Change adapter options. <br>
### Configure the external vEthernet network adapter.
Right-click the vEthernet (external) adapter and select Properties. <br>
Select Internet Protocol Version 6 (TCP/IPv6). <br>
Select Properties. <br>
Select Use the following IPv6 address and configure the settings as follows: <br>
&emsp;* IPv6 address: 2620:14F0:45EA:0001:192:168:0:10 <br>
&emsp;* Subnet prefix length: 64 <br>
Select OK. <br>
Select Close. <br>
### Verify the IPv6 address.
Right-click Start and select Windows PowerShell (Admin) to verify the address configuration. <br>
At the prompt, type ipconfig /all and press Enter view the IPv6 Address. <br>
