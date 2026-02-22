# Module 3 Labs: Configuring Interfaces and Switches

## Lab 3.1: Select and Install a Network Adapter
Complete this lab as follows: <br>
### Insert the PCI adapter into the motherboard.
Above the computer, select Motherboard to switch to the motherboard view of the computer. <br>
Under Shelf, expand Network Adapters. <br>
Drag the Network Adapter, Ethernet 10/100/1000BaseTX, PCIe card to a free PCIe slot on the computer's motherboard. <br>
![Example image](images/pcie.jpg) <br>
### Move the Ethernet cable from the computer's built-in network adapter to the new PCIe network card.
Above the computer, select Back to switch to the back view of the computer. <br>
Drag the Ethernet cable from the built-in port to the port on the PCIe network adapter. <br>
### Confirm that the computer is connected to the local network and the internet.
Above the computer, select Front to switch to the front view of the computer. <br>
Select the power button on the computer case to turn on the computer. <br>
Wait for the operating system to load. <br>
Right-click Start and then select Terminal (Admin). <br>
From the PowerShell prompt, type ping 192.168.0.10 and then press Enter to test connectivity to the local network server. <br>
From the PowerShell prompt, type ping 198.28.2.254 and then press Enter to test connectivity to the internet. <br>
## Lab 3.2: Connect a Media Converter
Complete this lab as follows: <br>
### Add the media converter to the rack.
Under Shelf, expand Networking Devices. <br>
Drag the Media Converter to the bottom shelf of the rack in the Workspace. <br>
### Connect the SC to LC fiber cable to the media converter.
Above the rack, select Back to switch to the back view of the rack. <br>
Drag the Ethernet cable from the left wall outlet to the Ethernet port on the media converter. <br>
Under Shelf, expand Cables. <br>
Select the Cable, Fiber, SC to LC cable. <br>
From the Selected Component pane, drag the Connector, Fiber Duplex LC male connector to the media converter. <br>
### Connect the SC to LC cables to the patch panel.
Above the rack, select Front to switch to the front view of the rack. <br>
From the Selected Component pane: <br>
&emsp;* Drag the Fiber Optic SC Connector (A) to port 23 on the fiber patch panel. <br>
&emsp;* Drag the Fiber Optic SC Connector (B) to port 24 on the fiber patch panel. <br>
### Connect the power adapter to the media converter, and then plug it into a critical load bank outlet on the UPS using the adapter on the shelf.
From the Shelf, drag the Power Adapter, AC to DC to the DC power port on the media converter. <br>
From the Select Connector pane, select DC Power Connector. <br>
Above the rack, select Back to switch to the back view of the rack. <br>
Under Shelf, expand Adapters. <br>
Drag the C14 Power Adapter to an open critical load bank outlet on the rack UPS <br>
Under Partial Connections, select the Power Adapter, AC to DC. <br>
From the Selected Component pane, drag the AC Power Adapter to the C14 Power Adapter installed in the UPS. <br>
The lights on the media converter should turn on. <br>
### Navigate to any workstation on Floor 1 to confirm internet connectivity.
From the top left, select Building A. <br>
Under Building A, select Floor 1. <br>
Select a workstation (such as Office1). <br>
From the notification area, right-click the Network icon and select Open Network & Internet settings. <br>
Verify that the workstation has internet connectivity.
## Lab 3.3: Install a Switch in the Rack
Complete this lab as follows: <br>
### Add the new network switch to the rack.
Under Shelf, expand Switches. <br>
Drag the Switch to the space available at the top of the rack under the router. <br>
### Connect the power adapter to the switch, and then plug it into a critical load bank outlet using the AC Power Cable with C14 end.
Above the rack, select Back to switch to the back view of the rack. <br>
Under Shelf, expand Cables. <br>
Select the AC Power Cable with C14 end. <br>
From the Selected Component pane, drag the AC Power Connector to the switch and the AC Power Connector C14 to a critical load bank outlet on the UPS. <br>
### Connect port 5 on the switch to ITAdmin port 5 on the Patch Panel. <br>
Under Shelf, expand Cables. <br>
Drag a Cat6a Cable to port 5 on the switch. <br>
From the Selected Component pane, drag the unconnected RJ45 Shielded Connector to port 5 on the fiber patch panel, labeled as IT Adm. <br>
### Connect port 8 on the switch to Lobby port 8 on the Patch Panel.
If you do not see the front view of the switch, select Front above the rack. <br>
Under Shelf, expand Cables. <br>
Drag a Cat6a Cable to port 8 on the switch. <br> <br>
### Connect port 24 on the switch to the LAN 1 port on the router.
If you do not see the front view of the switch, select Front above the rack. <br>
Under Shelf, expand Cables. <br>
Drag a Cat6a Cable to port 24 on the switch. <br>
From the Selected Component pane, drag the unconnected RJ45 Shielded Connector to the LAN 1 port on the router. <br>
### Connect port 21 on the switch to the CorpServer.
If you do not see the front view of the switch, select Front above the rack. <br>
Under Shelf, expand Cables. <br>
Drag a Cat6a Cable to port 21 on the switch. <br>
Above the rack, select Back to switch to the back view of the rack. <br>
From the Selected Component pane, drag the unconnected RJ45 Shielded Connector to the left network port on the first server from the top. <br>
### Ping the CorpServer IP address (192.168.0.10) from the Lobby laptop to test connectivity.
From the top left, select Floor 1. <br>
Select the Gst-Lap laptop in the lobby. <br>
Right-click Start and then select Terminal (Admin). <br>
At the prompt, enter ping 192.168.0.10. <br>
Notice the ping was successful, indicating connectivity. <br>
## Lab 3.4: Secure a Switch
Complete this lab as follows: <br>
### Log in to the CISCO switch.
Click Start, then select Google Chrome. <br>
In the URL field, enter 192.168.0.2 and press Enter. <br>
Maximize the window for easier viewing. <br>
In the Username and Password fields, enter cisco (case sensitive). <br>
Select Log In. <br>
### Create a new user account.
Under Quick Access on the Getting Started menu, select Change Device Password. <br>
Select Add. <br>
For the username, enter ITSwitchAdmin (case sensitive). <br>
For the password, enter Admin$only1844 (case sensitive). <br>
For Confirm Password, enter Admin$only1844. <br>
For User Level, make sure Read/Write Management Access (15) is selected. <br>
Select Apply. <br>
Select Close. <br>
### Edit the default user account.
Under the User Account Table heading, select cisco (the default user) and then select Edit. <br>
For Password, enter CLI$only1958. <br>
For Confirm Password, enter CLI$only1958. <br>
For User Level, select Read-Only CLI Access (1). <br>
Select Apply. <br>
### Save the changes to the switch's startup configuration file.
From the top of the switch window, select Save. <br>
Under Source File Name, make sure Running configuration is selected. <br>
Under Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
## Lab 3.5: Cisco IoS Basics
To complete this lab, do the following: <br>
### Finding and entering commands:
Select the SFO router and press Enter in the terminal window. <br>
Type ? to see the list of commands available in this mode. <br>
If the output exceeds the terminal window, you will see --More-- at the bottom. <br>
&emsp;* Press the Enter key to see what happens.
&emsp;* Press the space bar to see what happens. <br>
&emsp;* Select the Questions button to open the Lab Questions dialog. <br>
&emsp;* (Optional) If necessary, move the terminal window to the left to view the window and the Lab Questions dialog at the same time. <br>
&emsp;* Answer question 1. <br>
&emsp;* Select the Questions button to close the Lab Questions dialog. <br>
Type s? to see commands that start with the letter s. Notice that sh would uniquely identify the show command. <br>
T&emsp;* ype sh h? to see options that start with h. <br>
&emsp;* Notice that show history can be replaced with sh hi or sh hist. <br>
&emsp;* Type sh v? at the prompt. <br>
&emsp;* Select the Questions button to open the Lab Questions dialog. <br>
&emsp;* Answer question 2. <br>
&emsp;* Select the Questions button to close the Lab Questions dialog. <br>
### Navigating router modes:
Enter en (or enable). This will change to the privileged EXEC mode. <br>
&emsp;* Select the Questions button to open the Lab Questions dialog. <br>
&emsp;* Answer question 3. <br>
&emsp;* Select the Questions button to close the Lab Questions dialog. <br>
Enter disable to exit this mode, and notice the change in the command prompt. <br>
Enter en to return to the privileged EXEC mode. <br>
&emsp;* Enter conf t (or configure terminal) to change to the global configuration mode. <br>
&emsp;* Select the Questions button to open the Lab Questions dialog. <br>
&emsp;* Answer question 4. <br>
&emsp;* Select the Questions button to close the Lab Questions dialog. <br>
Enter exit to return to the global configuration mode and notice the change in the command prompt. <br>
Enter conf t to return to the global configuration mode. <br>
&emsp;* Enter int fa0/1 (or interface FastEthernet0/1) to switch to the interface mode. <br>
&emsp;* Select the Questions button to open the Lab Questions dialog. <br>
&emsp;* Answer question 5. <br>
&emsp;* Select the Questions button to close the Lab Questions dialog. <br>
Enter exit to return to the global configuration mode and notice the change in the command prompt. <br>
## Lab 3.6: Configure Port Aggregation
Complete this lab as follows: <br>
### Log in to the Cisco switch.
In the Username and Password fields, enter cisco (case-sensitive). <br>
Select Log In. <br>
### Create a new Link Aggregation Group (LAG1).
From the left pane, expand and select Port Management > Link Aggregation > LAG Management. <br>
From the right pane, select LAG 1 and then select Edit. <br>
In the LAG Name field, type windows_server. <br>
Select LACP to enable the Link Aggregation Control Protocol (LACP). <br>
Under Port List, press and hold the Shift key; then select GE1 and GE2. <br>
Select > to add the ports to the LAG Members pane. <br>
Select Apply. <br>
Select Close. <br>
### Configure LAG1 to the VLAN mode of access.
From the left pane, expand and select VLAN Management > Interface Settings. <br>
Using the Filter: Interface Type equals to drop-down menu, select LAG and then select Go. <br>
Select LAG1 and then select Edit. <br>
For Interface VLAN Mode, select Access. <br>
Select Apply. <br>
Select Close. <br>
### Join LAG1 to VLAN13.
From the left pane, expand and select VLAN Management > Port VLAN Membership. <br>
Using the Filter: Interface Type equals to drop-down menu, select LAG and then select Go. <br>
Select LAG1 and then select Join VLAN. <br>
Under Select VLAN, from the right pane, select 1U and then select < to remove VLAN1. <br>
From the left pane, select VLAN13; then select > to add the VLAN to the selected VLANs pane. <br>
Select Apply. <br>
Select Close. <br>
### Verify the status of the new LAG1 group.
From the left navigation bar, expand and select Port Management > Link Aggregation > LAG Management. <br>
From the top right, select Questions. <br>
Answer the questions. <br>
This connection is now ready to use LACP. <br>
Minimize the Lab Questions window. <br>
### Save the changes to the switch's startup configuration file.
From the upper right of the switch window, select Save. <br>
For Source File Name, make sure Running configuration is selected. <br>
For Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
### Lab 3.7: Enable Jumbo Frame Support
Complete this lab as follows: <br>
### Log in to the CISCO switch.
Maximize the Google Chrome window for better viewing. <br>
In the Username and Password fields, enter cisco (the password is case sensitive). <br>
Select Log In. <br>
### Enable Jumbo Frames.
From the left pane, expand and select Port Management > Port Settings. <br>
For Jumbo Frames, select Enable. <br>
Select Apply. <br>
### Save the changes to the switch's startup configuration file.
From the upper right of the switch window, select Save. <br>
For Source File Name, make sure Running configuration is selected. <br>
For Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
### Reboot the switch.
From the left pane, under Administration, select Reboot. <br>
Select Reboot to reboot the switch immediately. <br>
Select OK. <br>
### Log in to the Cisco switch and check switch statistics for any errors.
In the Username and Password fields, enter cisco (the password is case sensitive). <br>
Select Log In. <br>
From the left pane, expand and select Status and Statistics > RMON > Statistics. <br>
For Interface, use the drop-down list to select GE28. <br>
Review the statistics for Undersize, Oversize, Jabbers, and Collisions. <br>
Answer the questions. <br>
### Lab 3.8: Configure PoE
Complete this lab as follows: <br>
### Log in to the Cisco switch.
Maximize the Google Chrome window for better viewing. <br>
In the Username and Password fields, enter cisco (case-sensitive). <br>
Select Log In. <br>
### Set the Power over Ethernet (PoE) switch properties.
From the left pane, expand and select Port Management > PoE > Properties. <br>
Select Class Limit. <br>
Select Apply. <br>
From the top right, select Questions. <br>
Answer the questions. <br>
Minimize the Lab Questions dialog. <br>
### Configure the PoE priority for port GE23 to be Critical.
From the left pane, under PoE, select Settings. <br>
From the right pane, select port GE23 and click Edit. <br>
For Power Priority Level, select Critical. <br>
Select Apply. <br>
Select Close. <br>
### Save the changes to the switch's startup configuration file.
From the upper right of the switch window, select Save. <br>
For Source File Name, make sure Running configuration is selected. <br>
For Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
## Lab 3.9: Troubleshoot Disabled Ports
Complete this lab as follows: <br>
### Replace the cable on the Office1 computer
From the top left, select Floor 1 to view the map of the offices. <br>
On the map, select Hardware under Office 1 to view the computer hardware in that office. <br>
Drag the networking cable out of the wall plate and drop it on the workspace. <br>
Above the Office1 workstation tower, select the Back button. <br>
Drag the other end of the networking cable from the back of the workstation and drop it on the workspace. <br>
Drag a Cat6a cable from the Shelf to the wall plate to connect one end. <br>
Drag the other end of the same cable to the back of the workstation and plug it into the motherboard. <br>
Click the computer monitor where it says Click to view Windows 11. <br>
Notice that the networking icon shows no internet connection. <br>
### Check the physical connection of the cables on the switch for the Office1 computer.
From the top left, select Floor 1, then select Hardware in the Networking Closet. <br>
Zoom in close to the switch and patch panel in the hardware rack (the second and third items from the top of the rack). <br>
On the patch panel, select the cable under the label Off 1 (for Office 1). <br>
Notice that the other end is highlighted in the switch in port number 3. As you can see, the port does not show a link light or any activity. <br>
### Check the configuration of the switch in the Networking Closet.
From the top left, select Floor 1, then select ITAdmin in the IT Administration office. <br>
Select the Chrome icon on the taskbar. <br>
Access the switch management console from the ITAdmin computer using the following credentials: <br>
&emsp;* Address: http://192.168.0.2 (maximize the Chrome window) <br>
&emsp;* Username: ITSwitchAdmin (case-sensitive) <br>
&emsp;* Password: Admin$only (case-sensitive) <br>
From the left menu in the switch management console, select Port Management. <br>
From the Port Setting Table, notice that port 3 is listed as Down under Operational Status. <br>
Select port 3, then scroll to the bottom and select Edit. <br>
Change the Administrative Status to Up. <br>
Select Apply. <br>
Select Close. <br>
## Lab 3.10: Switching Loop
To complete this lab, do the following: <br>
### Enable all ports on each device.
Select the Internet and LAN ports on the router to enable the ports. <br>
Repeat step 1 for all the ports on Switch1, Switch2, and Switch3. <br>
### To prevent a switching loop, select (disable) at least one of the redundant connections on a switch.