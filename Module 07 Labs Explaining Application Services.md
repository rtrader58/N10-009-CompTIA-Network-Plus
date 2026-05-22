# Module 7 Labs: Explaining Application Services
### Lab 7.1: Configure NTP on Linux
Complete this lab as follows: <br>
### Install the NTP service on the CorpData server.
Under Networking Closet, select CorpData. <br>
From the Favorites bar, select Terminal. <br>
At the terminal prompt, type dnf install ntp and then press Enter to begin the installation process. <br>
Type y and press Enter to install the NTP package. <br>
### Verify that the NTP service is running.
Type systemctl status ntp and press Enter. <br>
From the top left, select Questions. <br>
Answer Question 1. <br>
### Find the NTP server's IP address.
Type ip addr show | more to view the NTP server's IP address. <br>
Answer Question 2. <br>
### Add the NTP server as a time source for the Exec computer.
From the top left, select Floor1. <br>
Under Executive Office, select Exec. <br>
Right-click Start and select Terminal (Admin). <br>
Configure Exec to use the NTP server with the following command: <br>
w32tm /config /manualpeerlist:192.168.0.22,0x8 /syncfromflags:MANUAL /update <br>
### Verify that the Exec computer is using the NTP server for time synchronization.
In the console, type w32tm /query /status and then press Enter. <br>
### Applied Live Lab 7.2: Troubleshoot Time Synchronization Issues
Live Lab <br>
## Live Lab 7.3: Verify Secure Web Services
Live Lab <br>
### Lab 7.4: Scan for Web Services with Nmap
Live Lab <br>
### Lab 7.5: Connect VoIP 1
Complete this lab as follows: <br>
### Connect the IP phone in the Lobby to the network.
Under Lobby, select Hardware. <br>
Under Shelf, expand Phones. <br>
For the IP phone shown, select Details and then select Specifications. <br>
&emsp; Make note of the port options. <br>
Close the IP phone details window. <br>
Drag the IP phone to the Workspace. <br>
Above the IP phone, select Back to switch to the back view of the phone. <br>
Under Shelf, expand Cables. <br>
Drag Cat6a Cable, RJ45 to the LAN port on the phone. <br>
From the Selected Component pane, drag the unconnected RJ45 Connector to the Ethernet port on the wall outlet. <br>
Under Shelf, select the Power Adapter. <br>
From the Select Connector window: <br>
&emsp; * Drag the DC Power Connector to the DC power connector on the phone. <br>
&emsp; * Drag the AC Power Adapter to the wall outlet. <br>
Above the IP phone, select Front to switch to the front view of the phone. Confirm that the phone's display is on. <br>
### Connect the Exec workstation and its monitor to a surge protector.
From the top left, select Floor 1 Overview. <br>
Under Executive Office, select Exec. <br>
Right-click Start. <br>
Select Shut down or sign out > Shut down. <br>
Under Shelf, expand Outlets. <br>
Drag the Surge Protector to the Workspace. <br>
Drag both AC Power plugs from the wall outlet to an open outlet on the surge protector. <br>
Select the Surge Protector. <br>
From the Selected Component pane, drag the AC Power Connector (Male) to an open plug on the wall outlet. <br>
### Connect the IP phone in the Executive Office to the network.
Under Shelf, expand Phones. <br>
Drag the IP phone to the Workspace. <br>
Above the IP phone, select Back to switch to the back view of the phone.
Under Shelf, expand Cables. <br>
Drag Cat6a Cable, RJ45 to the LAN port on the phone. <br>
From the Selected Component pane, drag the unconnected RJ45 Connector to the Ethernet port on the wall outlet. <br>
Above the workstation, select Back to switch to the back view of the workstation. <br>
From the Shelf, drag Cat6a Cable, RJ45 to the PC port on the phone. <br>
In the Selected Component pane, drag the unconnected RJ45 Connector to the workstation's NIC. <br>
### Provide power to the IP phone.
Under Shelf, select the Power Adapter. <br>
From the Selected Component pane: <br>
&emsp; * Drag the DC Power Connector to the back of the phone. <br>
&emsp; * Drag the AC Power Adapter to an open plug on the surge protector. <br>
Above the IP phone, select Front to switch to the front view of the phone. Confirm that the phone's display is on. <br>
### Power on the workstation and confirm that it has a connection to the network and the internet.
Above the workstation, select Front. <br>
Select the monitor's power button. <br>
Select the computer's power button. <br>
&emsp; The computer is automatically signed into Windows 11. <br>
Right-click Start and then select Settings. <br>
Select Network & Internet. <br>
&emsp; From the Status view, the diagram should indicate an active connection to the network. <br>
## Lab 7.6: Connect VoIP 2
Complete this lab as follows: <br>
### From the Lobby, disconnect the AC/DC adapter from the IP phone and the wall.
Under Lobby, select Hardware. <br>
Above the IP phone, select Back to switch to the back view of the phone. <br>
Drag the DC power connector from the phone to the Shelf. <br>
Drag the AC power plug from the wall outlet to the Shelf. <br>
Above the IP phone, select Front to switch to the front view of the phone and confirm it is on. <br>
### From the Executive Office, disconnect the AC/DC adapter from the IP phone and the wall.
From the top left, select Floor 1 Overview. <br>
Under Executive Office, select Hardware. <br>
Above the IP phone, select Back to switch to the back view of the phone. <br>
Drag the DC power connector from the phone to the Shelf. <br>
Drag the AC power plug from the surge protector to the Shelf. <br>
Above the IP phone, select Front to switch to the front view of the phone and confirm it is on. <br>
### From the Support Office, connect an IP phone.
From the top left, select Floor 1 Overview. <br>
Under Support Office, select Hardware. <br>
Under Shelf, expand Phones. <br>
Drag the IP Phone to the Workspace.
Above the IP phone, select Back to switch to the back view of the phone. <br>
Above the workstation, select Back to switch to the back view of the workstation. <br>
Drag the RJ45 Ethernet cable from the workstation to the LAN port  (top port) on the IP phone. <br>
Under Shelf, expand Cables and then select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp; * Drag an RJ45 Connector to the PC port on the phone. <br>
&emsp; * Drag the other unconnected RJ45 Connector to the NIC on the workstation. <br>
### Make sure the Support computer is still connected to the internet.
On the Support monitor, select Click to view Linux. <br>
From the favorites bar, select Terminal. <br>
From the terminal, type ping -c4 198.28.2.254 (the ISP) and press Enter. <br>
## Lab 7.7: Configure NIC Teaming
Complete this lab as follows: <br>
### Move the network cable from the onboard adapter in the CorpServer to the 4-port NIC in CorpServer.
Above the rack, select Back to switch to the back view of the rack. <br>
Drag the network cable from the onboard network adapter on CorpServer (the 1U server) to a free port on the 4-port NIC in CorpServer. <br>
Above the rack, select Front to switch to the front view of the rack. <br>
### Connect network cables from the 4-port NIC on CorpServer to the switch ports 19, 20, and 21.
Under Shelf, expand Cables. <br>
Select Cat6a Cable, RJ45. <br>
From the Selected Component pane, drag an unconnected RJ45 cable to port 19, 20, or 21.
Repeat steps 2b-2c for two more cables. Use a port not previously used. <br>
Above the rack, select Back. <br>
From Partial Connections: <br>
&emsp; * Drag a cable to an open port on the 4-port NIC in CorpServer. <br>
&emsp; * Repeat the previous step until there are no more cables in Partial Connections. <br>
### Configure the adapter ports as members of a NIC team.
On the CorpServer monitor, select Click to view Windows Server 2022. <br>
From Server Manager, select Local Server from the menu on the left. <br>
Next to NIC Teaming, select Disabled to enable and configure NIC Teaming. <br>
From the Teams panel, use the Tasks drop-down list to select New Team. <br>
In the Team name field, type NetTeam. <br>
Select adapters Ethernet 3 through Ethernet 6 to be included in the team. <br>
From the top right, select Questions. <br>
Answer Question 1. <br>
Minimize the Lab Questions window. <br>
From the NIC Teaming window, expand Additional Properties. <br>
Configure the additional properties as follows: <br>
&emsp; * Teaming mode: LACP <br>
&emsp; * Load balancing mode: Address Hash <br>
&emsp; * Standby adapter: None (all adapters Active) <br>
Select OK to close the NIC Teaming dialog. <br>
Close the NIC Teaming window. <br>
### Configure the Hyper-V Virtual Switch Manager to use the new NIC team for the External network.
From Server Manager's menu bar, select Tools > Hyper-V Manager. <br>
Right-click CORPSERVER and then select Virtual Switch Manager. <br>
Under Virtual Switches, select the External switch for configuration options. <br>
Under Connection type, use the External network drop-down to select the Microsoft Network Adapter Multiplexor Driver. <br>
Select OK. <br>
### Verify the status of the team and your network connection using the Network and Sharing Center.
From the system tray, right-click on the network icon and then select Open Network and Sharing Center. <br>
Verify that the vEthernet (External) NIC has an internet connection. Also, notice that the network icon in the system tray shows that the server is connected. <br>
To check the connection speed in the Network and Sharing Center, select NetTeam connection on the right. <br>
At the top right, select Questions. <br>
Answer Question 2. <br>
## Live Lab 7.8: Configure First Hop Redundancy
Live Lab <br>