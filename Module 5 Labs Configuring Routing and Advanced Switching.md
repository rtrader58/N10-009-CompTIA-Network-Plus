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
R&emsp;* edirect target port: Other 5151 <br>
D&emsp;* escription: RDP from LAN to web server using custom port <br>
Select Save. <br>
Select Apply Changes. <br>
