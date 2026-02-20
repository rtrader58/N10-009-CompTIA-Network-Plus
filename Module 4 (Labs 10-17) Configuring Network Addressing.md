# Module 4 Labs 4.10-4.17: Configuring Network Addressing

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
## Lab 4.11: Use ping and tracert on Windows
Complete this lab as follows: <br>
### Under the Executive Office heading, select the Exec computer.
Right-click Start and then select Terminal (Admin). <br>
Ping the Office2 computer by typing ping 192.168.0.31 and then pressing Enter. <br>
Ping the CorpServer computer by typing ping 192.168.0.10 and then pressing Enter. <br>
&emsp; Both pings were completed successfully, which means that the local network connectivity works on the Exec computer. <br>
### From the top right, select the Exhibits button. Note the IP address for the routers for Building A and the ISP's router.
Close the Exhibits window and select Questions from the top right. <br>
From the information you reviewed on the Exhibits page, answer Questions 1 and 2. <br>
Minimize the Lab Questions window. <br>
### In the PowerShell window, type ipconfig and press Enter. Note the IPv4 Address and Default Gateway values.
Ping Building A's router by typing ping 192.168.0.5 and then pressing Enter. <br>
The ping succeeds. <br>
Check the path to the ISP's router by typing tracert 198.28.2.254 and then pressing Enter. <br>
&emsp; This ping fails. Comparing the IP address of the building's router to the IP Address of the Default Gateway of the Exec computer, we can conclude where the change should be made. <br>
### Change the Default Gateway of the Exec computer:
Right-click the Networking icon in the Notification area of the taskbar, and then select Network and Internet settings. <br>
Click on Ethernet and scroll down to IP assignment. <br>
Click Edit. <br>
Change the Gateway field to 192.168.0.5 to match the building's router IP address, and then click Save. <br>
Close the Settings window. <br>
From the PowerShell window, verify that the change has resolved the ping issues by typing ping 192.168.0.5 and pressing Enter. <br>
The ping to Building A's router is successful. <br>
From the PowerShell window, verify that the change has resolved the ping issues by typing tracert 198.28.2.254 and then pressing Enter. <br>
The trace to the ISP's router is successful. <br>
## Lab 4.12: Use ping and traceroute on Linux
While completing this lab, use the following information: <br>
![Example image](images/lab4_12 table.jpg) <br>
Complete this lab as follows: <br>
### From the IT-Laptop system, explore using the ping command.
Under IT Administration, select IT-Laptop. <br>
From the Favorites bar, select Terminal. <br>
At the prompt, type ping -c4 192.168.0.30 and press Enter to ping Office1. <br>
You can successfully ping the IP address of Office1 from IT-Laptop. (Note that the -c4 tells the ping command to only send a count of four pings.) <br>
Type ping -c4 199.92.0.32 and press Enter to ping Support. <br>
&emsp; You cannot ping Support from IT-Laptop because the IP address for Support is on a different network (Network 199.92.0.0 instead of Network  192.168.0.0). Devices on the same local network must have IP addresses in the same network range. If you want to communicate with Support, you need to change the IP address assigned to Support. <br>
Type ping -c4 192.168.0.5 and press Enter to ping the internal interface of Building A's router. <br>
&emsp; The ping is successful because IT-Laptop and the router's address (192.168.0.5) are on the same network. <br>
Type ping -c4 163.128.78.93 and press Enter to ping the external DNS server. <br>
&emsp; This ping test fails. Although IT-Laptop and the ISP are on different networks (Networks 192.168.0.0 and 163.128.78.0, respectively), they should be able to communicate if IT-Laptop has a properly configured default gateway that will eventually lead to the correct destination. <br>
### From the IT-Laptop system, view its IP configuration settings.
At the prompt, type cd /etc/sysconfig/network-scripts and press Enter. <br>
Type ls and press Enter. <br>
&emsp; Notice that there's a configuration file named ifcfg-enp2s0. This file contains the IP information on this system. <br>
Type cat ifcfg-enp2s0 and press Enter to view the contents of this IP configuration file. <br>
&emsp; Notice that there's no GATEWAY address (192.168.0.5) set, explaining why the ping to the ISP in the previous step failed. There was no other computer to route the ping request to the correct destination. <br>
### From Office2, trace the path between Office2 and the internet router's interface.
From the top left, select Floor 1 Overview. <br>
Under Office 2, select Office2. <br>
From the Favorites bar, select Terminal. <br>
At the prompt, type traceroute 198.28.56.1 and press Enter. <br>
&emsp; Which addresses appear in the path between Office2 and the CorpNet router?
&emsp; When you communicate with devices on other networks, the packets go to the default gateway first (the router between the two networks). In this example, that's the router for Building A, which has an IP address of 192.168.0.5. The packets are sent to the router interface on the same network as the sending host and then to the next hop in the path as necessary. In this case, there are two IP addresses listed in the traceroute output, but only one router (hop) between Office2 and the internet router. The last address in the traceroute output is the IP address for the internal NIC on the CorpNet router located in Building B. <br>
Type traceroute 163.128.78.93 and press Enter to trace the path to one of the ISP's DNS servers. <br>
&emsp; How does this path differ from the path you discovered in the previous step? <br>
&emsp; When you trace the path between Office2 and the ISP's DNS server, the path has additional hops. The first lines in the traceroute output are the routers (hops) between Office2 and the DNS server. The last address in the traceroute output is the IP address of the DNS server. <br>
## Lab 4.13: Assisted Troubleshooting 1
Complete this lab as follows: <br>
### Gather information on Home-Laptop
Right-click Home-Laptop and select Launch Windows. <br>
Hover over the network icon in the system tray. <br>
Note that Home-Laptop is not connected to the internet. <br>
Right-click the network icon and select Network & Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment and select Edit. <br>
Select Questions. <br>
Answer Questions 1 through 3. <br>
Minimize the Lab Questions window. <br>
Under Edit IP Settings, select Cancel. <br>
### Identify symptoms on Home-Laptop
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Select Questions. <br>
Answer Question 4. <br>
Minimize the Lab Questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Gather information on Home-PC1
Right-click Home-PC1 and select Launch Windows. <br>
Hover over the network icon in the system tray. <br>
Note that Home-PC1 is connected to the internet. <br>
Right-click the network icon and select Network & Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment and select Edit. <br>
Select Questions. <br>
Answer Questions 5 through 7. <br>
Minimize the Lab Questions window. <br>
Under Edit IP Settings, select Cancel. <br>
### Identify symptoms on Home-PC1
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Select Questions. <br>
Answer Question 8. <br>
Minimize the Lab Questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Establish a theory of probable cause
Select Questions. <br>
Answer Questions 9. <br>
Minimize the Lab Questions window. <br>
Note that Home-Laptop has a typo in the IP address and is on the wrong network. <br>
### Implement a solution
Right-click Home-Laptop and select Launch Windows. <br>
From Network & Internet > Ethernet, scroll down to IP assignment and select Edit. <br>
Correct the IP address to be on the same network as the other computers (192.168.1.20). <br>
Select Save. <br>
Verify full system functionality for Home-Laptop <br>
Hover over the network icon in the system tray. <br>
Note that Home-Laptop now shows connected to HomeNet and the Internet. <br>
From the Terminal prompt, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Note that all pings are successful from Home-Laptop. <br>
## Lab 4.14: Assisted Troubleshooting 2
Complete this lab as follows: <br>
### Gather information on Home-Laptop
Right-click Home-Laptop and select Launch Windows. <br>
Hover over the network icon in the system tray. <br>
Note that Home-Laptop is not connected to the internet. <br>
Right-click the network icon and select Network & Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment and select Edit. <br>
Select Questions. <br>
Answer Questions 1 through 3. <br>
Minimize the Lab Questions window. <br>
Under Edit IP Settings, select Cancel. <br>
### Identify symptoms on Home-Laptop
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Select Questions. <br>
Answer Question 4. <br>
Minimize the Lab Questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Gather information on Home-PC1
Right-click Home-PC1 and select Launch Windows. <br>
Hover over the network icon in the system tray. <br>
Note that Home-PC1 is connected to the internet. <br>
Right-click the network icon and select Network & Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment and select Edit. <br>
Select Questions. <br>
Answer Questions 5 through 7. <br>
Minimize the Lab Questions window. <br>
Under Edit IP Settings, select Cancel. <br>
### Identify symptoms on Home-PC1
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Select Questions. <br>
Answer Question 8. <br>
Minimize the Lab Questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Establish a theory of probable cause
Select Questions. <br>
Answer Questions 9. <br>
Minimize the Lab Questions window. <br>
Note that Home-Laptop has a typo in the subnet mask, so the gateway appears to Home-Laptop to be another network. <br>
### Implement a solution
Right-click Home-Laptop and select Launch Windows. <br>
From Network & Internet > Ethernet, scroll down to IP assignment and select Edit. <br>
Correct the Subnet mask address to be the same as the other computers (255.255.255.0). <br>
Select Save. <br>
### Verify full system functionality for Home-Laptop
Hover over the network icon in the system tray. <br>
Note that Home-Laptop now shows connected to HomeNet and the Internet. <br>
From the Terminal prompt, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Note that all pings are successful from Home-Laptop. <br>
## Lab 4.15: Assisted Troubleshooting 3
Complete this lab as follows: <br>
### Gather information on Home-Laptop
Right-click Home-Laptop and select Launch Windows. <br>
Hover over the network icon in the system tray. <br>
Note that Home-Laptop is not connected to the internet. <br>
Right-click the network icon and select Network & Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment and select Edit. <br>
Select Questions. <br>
Answer Questions 1 thru 3. <br>
Minimize the Lab Questions window. <br>
Under Edit IP Settings, select Cancel. <br>
### Identify symptoms on Home-Laptop
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
&emsp;* ping 192.168.1.254 <br>
Select Questions. <br>
Answer Question 4. <br>
Minimize the Lab Questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Gather information on Home-PC1
Right-click Home-PC1 and select Launch Windows. <br>
Hover over the network icon in the system tray. <br>
Note that Home-PC1 is connected to the internet. <br>
Right-click the network icon and select Network & Internet settings. <br>
Select Ethernet. <br>
Scroll down to IP assignment and select Edit. <br>
Select Questions. <br>
Answer Questions 5 through 7. <br>
Minimize the Lab Questions window. <br>
Under Edit IP Settings, select Cancel. <br>
### Identify symptoms on Home-PC1
Right-click Start and select Terminal (Admin). <br>
In the Terminal window, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
&emsp;* ping 192.168.1.254 <br>
Select Questions. <br>
Answer Question 8. <br>
Minimize the Lab Questions window. <br>
In the top left, select Network Modeler to return to the network diagram. <br>
### Establish a theory of probable cause
Select Questions. <br>
Answer Questions 9. <br>
Minimize the Lab Questions window. <br>
Note that Home-Laptop has a typo in the gateway address. <br>
### Implement a solution
Right-click Home-Laptop and select Launch Windows. <br>
From Network & Internet > Ethernet, scroll down to IP assignment and select Edit. <br>
Correct the gateway address to be the same as the other computers (192.168.1.1). <br>
Select Save. <br>
### Verify full system functionality for Home-Laptop
Hover over the network icon in the system tray. <br>
Note that Home-Laptop now shows connected to HomeNet and the internet. <br>
From the Terminal prompt, type the following commands followed by pressing Enter. <br>
&emsp;* ping Home-Laptop <br>
&emsp;* ping Home-PC1 <br>
&emsp;* ping Home-PC2 <br>
&emsp;* ping 192.168.1.1 <br>
Note that all pings are successful from Home-Laptop. <br>
## Live Lab 4.16: Explore the VM Lab Environment
Follow the steps in the lab environment <br>
### Applied Live Lab 4.17: Troubleshoot IP Configuration
Follow the steps in the lab environment <br>