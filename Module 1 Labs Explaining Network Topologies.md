# Module 1 Labs: Explaining Network Topologies Labs

## Lab 1.1: Create Network Topologies
Complete this lab as follows:
### Move Marketing's five computers and switch to the canvas.
In the tools tray, select the End Devices icon. <br>
Drag the five computers to the modeler canvas. <br>
In the tools tray, select the Switches icon. <br>
Drag the Mktg_Switch switch to the canvas. <br>
### Connect the devices to create a star topology.
In the tools tray, select the Create Link icon. <br>
Select Mktg1 and select the Ethernet port. <br>
Select Mktg_Switch and select an open port. <br>
Repeat the process for Mktg2-Mktg5. <br>
## Lab 1.2: Explore a Single Location in a Lab
Complete this lab as follows: <br>
### Add a monitor to the Office 2 computer.
Under Office 2, select Hardware to go to the workstation. <br>
Under Shelf, expand Monitors. <br>
Drag the monitor from the Shelf to the bench next to the computer. <br>
### Connect the monitor to the computer.
Above the monitor, select Back to switch to the back view of the monitor. <br>
Above the computer, select Back to switch to the back view of the computer. <br>
Under Shelf, expand Cables. <br>
Select HDMI to HDMI Cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag an HDMI Connector to the HDMI port on the back of the computer. <br>
&emsp;* Drag the other HDMI Connector to the HDMI port on the back of the monitor. <br>
### Plug in the monitor.
Under Shelf, select AC Power Cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag the AC Power Connector (Female) to the monitor power port. <br>
&emsp;* Drag the AC Power Connector (Male) to the unused power port on the wall plate. <br>
### Add the keyboard and mouse.
Under Shelf, expand Input Devices. <br>
Drag the Keyboard to an empty USB port on the back of the computer. <br>
Drag the Mouse to an empty USB port on the back of the computer. <br>
### Power on the monitor and computer.
Above the monitor, select Front to switch to the front view of the monitor. <br>
Above the computer, select Front to switch to the front view of the computer. <br>
Select the power button on the monitor. <br>
Select the power button on the computer. <br>
The computer startup process begins, and you are automatically signed into Windows 11. <br>
Right-click Start and then select Settings to explore the operating system simulator's capabilities.
From the top menu (left side), select Office 2 to switch back to the Hardware view. <br>
## Lab 1.3: Create a Home Wireless Network
Complete this lab as follows: <br>
### Add the wireless access point to the workspace.
Under Shelf, expand Wireless Access Points. <br>
Drag the Wireless Access Point, 802.11b/g/n wireless access point to the workspace. <br>
For convenience, place the access point next to the existing router. <br>
Above the router, select Back to view the back of the router. <br>
Above the access point, select Back to view the back of the wireless access point. <br>
### Connect power to the wireless access point.
Under Shelf, expand Cables. <br>
Select Power Adapter, AC to DC. <br>
From the Selected Component pane: <br>
&emsp;* Drag the DC power connector to the port on the wireless access point.
&emsp;* Drag the AC power adapter end to an empty outlet on the wall outlet or the surge protector.
Connect the Ethernet cable to the wireless access point and existing router. <br>
Under Shelf, select the Cat6a Cable, RJ45 Ethernet cable.
From the Selected Component pane:
&emsp;* Drag an RJ45 Ethernet connector to the back of the access point. <br>
&emsp;* Drag the unconnected RJ45 Ethernet connector to one of the free LAN ports on the router. <br>
Configure the homeowner's laptop to connect to a wireless network. <br>
From the front of the laptop, slide the wireless switch to the ON position (right) to enable the integrated wireless network interface. <br>
Configure the homeowner's laptop to connect automatically to the HomeNet-AC wireless network. <br>
On the Home-Laptop monitor, select Click to view Windows 11. <br>
In the notification area, select the globe icon, then select the arrow next to the wireless icon. <br>
Select the HomeNet-AC wireless network. <br>
Select Connect automatically and then select Connect. <br>
&emsp;* To confirm the connection, right-click the wireless networking icon in the notification area again and select Network and Internet settings. The image on the Status page shows a connection to the internet. <br>
## Lab 1.4 : Create a SOHO Network
Complete this lab as follows: <br>
### Add the computers to the canvas
In the tools tray, select the End Devices icon. <br>
Drag all three computers to the modeler canvas.
### Add the switch to the canvas
In the tools tray, select the Switches icon. <br>
Drag the switch to the modeler canvas. <br>
### Add the router to the canvas
In the tools tray, select the Routers icon. <br>
Drag the router to the modeler canvas. <br>
### Connect the switch to the router
In the tools tray select the Create Link icon. <br>
Click on the Router and select Port 0. <br>
Click on the switch and select an open port. <br>
### Connect the computers to the switch
In the tools tray, make sure the Create Link icon is selected.
Click on Home-PC1 and select the Ethernet port. <br>
Click on the Switch and select an open port. <br>
Click on Home-PC2 and select the Ethernet port. <br>
Click on the switch and select an open port. <br>
Click on Home-Laptop and select the Ethernet port. <br>
Click on the switch and select an open port. <br>
Select Create Link to end the link tool. <br>
### Verify that a DHCP address is assigned
Right-click Home-PC1 and select Launch Windows. <br>
In the system tray, right-click the network icon and select Network and Internet Settings. <br>
Select Ethernet and scroll down to the assigned IP address. <br>
Answer the Questions. <br>
### Verify connectivity by pinging the gateway
Right-click Start and select Terminal (Admin). <br>
In the terminal window type ping 192.168.1.1. <br>
Press Enter. <br>
## Lab 1.5: Troubleshooting Methodology
Complete this lab as follows: <br>
### First, connect the two computers to the switch using the Create Link tool.
In the tools tray, select Create Link. <br>
Select the Office1 computer and Ethernet, then select the Switch and any port. <br>
Select the Home-Laptop computer and select Ethernet, then select the Switch and select any available port. <br>
Select Create Link to end the link tool. <br>
### Verify that Office1 can reach an external website.
Right-click Office1 and select Launch Windows. <br>
Launch Chrome from the taskbar. Type in rmksupplies.com and press Enter. <br>
The browser says, "This site can't be reached." <br>
Something isn't working as expected. Let's identify the problem. <br>
### Verify that Home-Laptop can reach an external website.
In the upper left, select Network Modeler. <br>
Right-click Home-Laptop and select Launch Windows. <br>
Launch Chrome from the taskbar. Type in rmksupplies.com and press Enter. <br>
Notice that the website loads correctly. Internet access is working for this computer. <br>
The connectivity problem seems to be localized to the Office1 computer. <br>
### Let's theorize what might be causing the problem.
The IP configuration of Office1 might not be correct. <br>
The cable might be bad that we plugged into Office1. <br>
The NIC in Office1 might be bad. <br>
The port on the switch might be bad. <br>
Let's test our theories until we find one that appears to be the problem. <br>
### Compare the IP configuration of the machine that is working to the one that is not working.
On Home-Laptop, right-click the network icon and select Network & Internet settings. <br>
Select Ethernet and scroll down to view the IP assignment information. <br>
Note that Home-Laptop is configured for DHCP (Automatic configuration). <br>
In the upper left, select Network Modeler. <br>
Right-click Office1 and select Launch Windows. <br>
On Office1, right-click the network icon and select Network & Internet settings. <br>
Select Ethernet and scroll down to view the IP assignment information. <br>
Note that Office1 has a manually assigned IP address. <br>
### Implement a fix.
Let's try changing the IP configuration of Office1 to match Home-Laptop. <br>
Under IP assignment, select Edit. <br>
Under Edit IP settings, select Automatic (DHCP) and select Save. <br>
### Test the fix.
On Office1, try browsing to rmksupplies.com. <br>
Did that fix the problem? <br>