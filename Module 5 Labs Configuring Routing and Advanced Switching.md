# Module 5 Labs: Configuring Routing and Advanced Switching

## Lab 5.1: Install an Enterprise Router
Complete this lab as follows: <br>
### Add the router to the empty slot near the top of the rack.
Under Shelf, expand Routers. <br>
Drag the Router to the first open space at the top of the rack in the Workspace. <br>
### Insert an SFP Transceiver (RJ45) into the WAN port on the router.
Under Shelf, expand Adapters. <br>
Drag the SFP Transceiver (RJ45) to the WAN port on the router. <br>
### Insert an SFP Transceiver (LC) into the LAN 1-4 ports.
Under Shelf, expand Adapters. <br>
Drag an SFP Transceiver (LC) to each of the LAN 1-4 ports on the router. <br>
### Use the AC power cable with C14 end to connect the router to a critical load bank outlet on one of the UPSs.
Above the rack, select Back to switch to the back view of the rack. <br>
Under Shelf, expand Cables. <br>
Select the AC Power Cable with C14 end. <br>
From the Selected Component pane, drag the AC Power Connector to the router and the AC Power Connector C14 to a critical load bank outlet on a UPS. <br>
### Connect the LAN 1 port on the router to ports 1 and 2 on the fiber patch panel using an SC to LC fiber cable.
Above the rack, select Front to switch to the front view of the rack. <br>
Select the SC to LC fiber cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag the Duplex LC Fiber Connector to the LAN 1 port on the router. <br>
&emsp;* Drag the Fiber Optic SC Connector (A) to port 1 on the fiber patch panel. <br>
&emsp;* Drag the Fiber Optic SC Connector (B) to port 2 on the fiber patch panel. <br>
### Connect the LAN 2 port on the router to ports 3 and 4 on the fiber patch panel using an SC to LC fiber cable.
Under Cables on the Shelf, select the SC to LC fiber cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag the Duplex LC Fiber Connector to the LAN 2 port on the router. <br>
&emsp;* Drag the Fiber Optic SC Connector (A) to port 3 on the fiber patch panel. <br>
&emsp;* Drag the Fiber Optic SC Connector (B) to port 4 on the fiber patch panel. <br>
### Connect the LAN 3 port on the router to ports 5 and 6 on the fiber patch panel using an SC to LC fiber cable.
Under Cables on the Shelf, select the SC to LC fiber cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag the Duplex LC Fiber Connector to the LAN 3 port on the router. <br>
&emsp;* Drag the Fiber Optic SC Connector (A) to port 5 on the fiber patch panel. <br>
&emsp;* Drag the Fiber Optic SC Connector (B) to port 6 on the fiber patch panel. <br>
### Connect the LAN 4 port on the router to ports 7 and 8 on the fiber patch panel using an SC to LC fiber cable.
Under Cables on the Shelf, select the SC to LC fiber cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag the Duplex LC Fiber Connector to the LAN 4 port on the router. <br>
&emsp;* Drag the Fiber Optic SC Connector (A) to port 7 on the fiber patch panel. <br>
&emsp;* Drag the Fiber Optic SC Connector (B) to port 8 on the fiber patch panel. <br>
### Connect the WAN port on the router to a port on the pfSense device at the top of the rack.
Under Cables on the Shelf, select the Cat6a Cable. <br>
From the Selected Component pane, drag one of the RJ45 Shielded Connectors to the WAN port on the router and the other to a port on the pfSense device above the router. <br>
## Lab 5.2: Cisco Troubleshooting Tools
Complete this lab as follows: <br>
### Prepare to enter commands on the SFO router.
Select SFO and press Enter. <br>
Type enable (or en) and press Enter to access privilege EXEC mode. <br>
### Verify the version of software in use.
Type show version (or sh ver) and press Enter. <br>
Press the space bar to advance and view the file. <br>
Select Questions and answer questions 1-3. <br>
Minimize the Lab Questions dialog. <br>
### Check the status of the interfaces.
Type show interfaces (or sh int) and press Enter. <br>
Press the space bar to advance and view the file. <br>
Select Questions and answer questions 4 and 5. <br>
Minimize the Lab Questions dialog. <br>
### Verify the settings in the router configuration files.
Type show startup-config (or sh start) and press Enter. <br>
Press the space bar to advance and view the file. <br>
Type show running-config (or sh run) and press Enter. <br>
Press the space bar to advance and view the file. <br>
Select Questions and answer question 6. <br>
Minimize the Lab Questions dialog. <br>
### View information about neighboring routers.
Type show cdp neighbors (or sh cdp ne) and press Enter. <br>
Select Questions and answer question 7. <br>
Minimize the Lab Questions dialog. <br>
### Test the connection from the SFO router to Wrk1 (192.168.11.1).
Type ping 192.168.11.1 and press Enter. <br>
Select Questions and answer question 8. <br>
Minimize the Lab Questions dialog. <br>
Close the SFO terminal window. <br>
### Switch to the Branch1 device and prepare to enter commands.
Select Branch1 and press Enter. <br>
Type en and press Enter to access privilege EXEC mode. <br>
### Test the path from Branch1 to the LAX router (172.17.12.97).
Type traceroute 172.17.12.97 and press Enter. <br>
Select Questions and answer question 9. <br>
### Lab 5.3: Configure NAT
Complete this lab as follows: <br>
### Sign into the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Configure NAT port forwarding for the PC1 computer.
From the pfSense menu bar, select Firewall > NAT. <br>
Select Add (either one). <br>
Configure or verify the following settings: <br>
&emsp;* Interface: LAN <br>
&emsp;* Protocol: TCP <br>
&emsp;* Destination type: LAN address <br>
&emsp;* Destination port range (From and To): MS RDP <br>
&emsp;* Redirect target IP: 172.16.1.100 <br>
&emsp;* Redirect target port: MS RDP <br>
&emsp;* Description: RDP from LAN to PC1 <br>
Select Save. <br>
### Configure NAT port forwarding for the Kali Linux server.
Select Add (either one). <br>
Configure or verify the following settings: <br>
&emsp;* Interface: LAN <br>
&emsp;* Protocol: TCP <br>
&emsp;* Destination type: LAN address <br>
&emsp;* Destination port range (From and To): SSH <br>
&emsp;* Redirect target IP: 172.16.1.6 <br>
&emsp;* Redirect target port: SSH <br>
&emsp;* Description: SSH from LAN to Kali <br>
Select Save. <br>
### Configure NAT port forwarding for the web server.
Select Add (either one). <br>
Configure or verify the following settings: <br>
&emsp;* Interface: LAN <br>
&emsp;* Protocol: TCP <br>
&emsp;* Destination type: LAN address <br>
&emsp;* Destination port range (From and To): Other <br>
&emsp; &emsp;* Custom (From and To) 5151 <br>
&emsp;* Redirect target IP: 172.16.1.5 <br>
&emsp;* Redirect target port: Other 5151 <br>
&emsp;* Description: RDP from LAN to web server using custom port <br>
Select Save. <br>
Select Apply Changes. <br>
## Lab 5.4: Create a Three-Tier Network
Complete this lab as follows: <br>
### Create the default connection for each access layer switch as follows:
In the tools tray, select Create Link. <br>
Create the connections by doing the following: <br>
&emsp;* Select Access1 and then Access 1 port 0. <br>

&emsp;* Select Dist1 and then enp2s0. <br>
&emsp;* Select Access2 and then Access 2 port 0. <br>
&emsp;* Select Dist2 and then enp2s0. <br>
&emsp;* Select Access3 and then Access 3 port 0. <br>
&emsp;* Select Dist3 and then enp2s0. <br>
### Make the redundant connections from each distribution layer router to the other two switches.
From the top right, select Exhibits. <br>
Create the redundant connections as specified in the following table: <br>
![Example image](images/lab5_4_1_table.jpg)  <br>
### Implement the connections from the core layer to the distribution layer.
Use the network information from the exhibit to connect the core routers as follows: <br>
![Example image](images/lab5_4_2_table.jpg)  <br>
### Lab 5.5: Configure Switch IP and VLAN - GUI
Complete this lab as follows: <br>
### Log in to the Cisco switch.
In the Google Chrome URL field, type 192.168.0.2 and press Enter. <br>
Maximize the window for better viewing. <br>
In the Username and Password fields, enter cisco (case-sensitive). <br>
Select Log In. <br>
### Assign a static IPv4 address to VLAN 1.
From the left navigation pane, expand and select Administration > Management Interface > IPv4 Interface. <br>
From the right pane, for IP Address Type, select Static. <br>
Configure the IPv4 interface as follows: <br>
&emsp;* IP address: 192.168.45.72 <br>
&emsp;* Mask: 255.255.255.0 <br>
&emsp;* Administrative Default Gateway: 192.168.45.1 <br>
Select Apply. <br>
Select OK. <br>
The switch will automatically log you out. <br>
### Log in to the Cisco switch.
In the Username and Password fields, enter cisco (case-sensitive). <br>
Select Log In. <br>
### Change the default VLAN ID for the switch to VLAN 16.
From the left pane, expand and select VLAN Management > Default VLAN Settings. <br>
Set Default VLAN ID After Reboot to 16. <br>
Select Apply and then select OK. <br>
### Save the changes to the switch's startup configuration file.
From the upper right of the switch window, select Save. <br>
For Source File Name, make sure Running configuration is selected. <br>
For Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
### Reboot the switch for changes to take effect.
From the left pane, expand and select Administration > Reboot. <br>
From the right pane, select Reboot. <br>
Select OK. <br>
Wait for the switch to restart. <br>
## Lab 5.6: Create VLANs - GUI
Complete this lab as follows:
### Log in to the Cisco switch.
In the Username field for the Cisco switch, enter ITSwitchAdmin (case-sensitive). <br>
In the Password field, enter Admin$only (case-sensitive). <br>
Select Log In. <br>
### Create the IPCameras VLAN.
From the Getting Started pane (right), under Initial Setup, select Create VLAN. <br>
Select Add. <br>
For VLAN ID, enter 2. <br>
For VLAN Name, enter IPCameras. <br>
Select Apply. <br>
Select Close. <br>
### Configure the IPCameras VLAN ports.
From the left pane, under VLAN Management, select Port to VLAN. <br>
Using the VLAN ID equals to drop-down menu, select 2. <br>
Select Go. <br>
For ports GE18 through GE21, use the drop-down menus to select Untagged. <br>
Select Apply. <br>
### Connect the IP camera in the lobby to the VLAN and mount the IP cameras.
From the top left, select Floor 1. <br>
Under Lobby, select Hardware. <br>
Under Shelf, expand CCTV Cameras. <br>
Drag the IP Camera (Lobby) to the workspace. <br>
Under Workspace, for the IP camera, select Back to switch to the back view of the IP camera. <br>
Under Shelf, expand Cables and then select the Cat6a Cable, RJ45 cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to the RJ-45 port on the IP camera wall mount plate. <br>
&emsp;* Drag the unconnected RJ45 Connector to the RJ-45 port on the back of the IP camera. <br>
Drag the IP camera to the IP camera wall plate. <br>
### Connect the IP camera in the Networking Closet to the VLAN and mount the IP cameras.
From the top left, select Floor 1. <br>
Under Networking Closet, select Hardware. <br>
Under Shelf, expand CCTV Cameras. <br>
Drag the IP Camera (Networking Closet) to the workspace. <br>
Under Workspace for the IP camera, select Back to switch to the back view of the IP camera. <br>
Under Shelf, expand Cables and then select the Cat6a Cable, RJ45 cable. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to the RJ-45 port on the IP camera mount wall plate. <br>
&emsp;* Drag the unconnected RJ45 cable to the RJ-45 port on the back of the IP camera. <br>
Drag the IP camera to the IP camera wall plate to mount the IP camera. <br>
### Connect the DHCP server and laptop to the VLAN.
From the Networking Closet, under Shelf, select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to port 21 on the switch. <br>
&emsp;* Drag the unconnected RJ45 Connector to port 21 on the patch panel. <br>
### Connect IT-Laptop5 to the VLAN.
From the top menu, select Floor 1. <br>
Under IT Administration, select Hardware. <br>
Above IT-Laptop5, select Back to switch to the back view of the laptop. <br>
Under Shelf, select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to the RJ-45 port on the laptop. <br>
&emsp;* Drag the unconnected RJ45 Connector to the open RJ-45 port on the wall plate. <br>
&emsp; Note: To verify that all components are connected, you can change the location to the Network Closet hardware view. You should see green link/activity lights on ports 18 - 21 of the switch. <br>
### Launch the IP camera monitoring software.
Under the laptop's workspace, select Front. <br>
On the IT-Laptop5, select Click to view Windows 10. <br>
From the taskbar, select Start. <br>
Select IP Cameras. <br>
Verify that both cameras are detected on the network. <br>
## Lab 5.7: Configure Trunking
Complete this lab as follows: <br>
### Log in to the CISCO switch.
Click the Start button, then select Google Chrome. <br>
In the URL field, enter 192.168.0.2 and press Enter. <br>
Maximize the window for better viewing. <br>
In the Username and Password fields, enter cisco (the password is case sensitive). <br>
Select Log In. <br>
### Examine the switch port defaults.
From the left navigation bar, expand and select VLAN Management > Interface Settings. <br>
Using the interface shown in the right pane, examine the settings for all ports. <br>
&emsp;* Note: For a detailed view of a single port, you can select Edit. <br>
From the upper right, select Questions. <br>
Answer Question 1. <br>
Minimize the Lab Questions dialog. <br>
### Set ports GE1 through GE26 to Access Mode.
From the Interface Settings pane, select GE1. <br>
Select Edit. <br>
Maximize the window for better viewing. <br>
For Interface VLAN Mode, select Access. <br>
Select Apply and then select Close. <br>
With GE1 still selected, click Copy Settings. <br>
In the to field, type 2-26 and then select Apply. <br>
Notice that under the Interface VLAN Mode column, ports GE1-GE26 are now set to Access. <br>
### Set the port VLAN ID (PVID) for ports GE27-GE28 to the value of 2.
Select the desired port and then select Edit. <br>
For the Administrative PVID, enter 2. <br>
Select Apply and then Close. <br>
Repeat steps 4a - 4c for the second port. <br>
### Add VLANs 22, 44, and 67 to ports GE27 and GE28.
From the left pane, under VLAN Management, select Port VLAN Membership. <br>
Select port GE27 and then select Join VLAN. <br>
From the new window, hold down the Shift key and select VLANs 22, 44, and 67; then select the > button to assign the VLANs. <br>
Select Apply and then select Close. <br>
Repeat steps 5b - 5d for port GE28. <br>
### Save the changes to the switch's startup configuration file.
From the top of the switch window, select Save. <br>
For Source File Name, make sure Running configuration is selected. <br>
For Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
## Lab 5.8: Configure Switch IP Settings - CLI
Complete this lab as follows: <br>
### Find the IP address assigned to the FastEthernet0/0 interface on the SFO router.
Select the Branch1 switch. <br>
From the Terminal, press Enter to get started. <br>
Type enable and press Enter to change to the EXEC or Global Configuration mode. <br>
Type show cdp neighbors detail and press Enter. <br>
Find the IP address for the SFO router. <br>
Answer the question. <br>
Move the question dialog to the side and keep working. <br>
### Configure the IP address and subnet mask for the Branch1 switch.
At the Branch1# prompt, type config t and press Enter. <br>
At the Branch1(config)# prompt, type interface vlan1 and press Enter. <br>
At the Branch1(config-if)# prompt, type ip address 192.168.11.250 255.255.255.0 and press Enter. <br>
At the Branch1(config-if)# prompt, type exit and press Enter. <br>
### Configure the switch to use the FastEthernet0/0 interface on the SFO router as the default gateway.
At the Branch1(config)# prompt, type ip default-gateway routers_IP_address and press Enter. <br>
At the Branch1(config)# prompt, type exit and press Enter. <br>
### Save your changes to the startup-config file.
At the Branch1# prompt, type copy run start and press Enter. <br>
Press Enter to begin building the configuration. <br>
When you see OK, press Enter. <br>
### Lab 5.9: Configure Management VLAN Settings - CLI
Complete this lab as follows: <br>
### Configure the IP address and subnet mask for the VLAN 1 interface.
Select Switch. <br>
From the switch terminal, press Enter to get started. <br>
At the Switch> prompt, type enable and press Enter. <br>
At the Switch# prompt, type configure terminal and press Enter. <br>
At the Switch(config)# prompt, type interface vlan1 and press Enter. <br>
At the Switch(config-if)# prompt, type ip address 192.168.11.250 255.255.255.0 and press Enter. <br>
Type exit and press Enter. <br>
### Configure the default gateway.
At the Switch(config)# prompt, type ip default-gateway 192.168.11.254 and press Enter. <br>
At the prompt, type exit and press Enter. <br>
### Verify the configuration changes.
At the prompt, type show run and press Enter. <br>
Press the space bar as needed to verify that the correct changes were made. <br>
### Type any key to exit show command.
Save your changes to the startup-config file. <br>
At the Switch# prompt, type copy run start and press Enter. <br>
Press Enter to begin building the configuration. <br>
Press Enter to return to the prompt. <br>