# Module 2: (Labs 2.9 - 2.14) - Supporting Cabling and Physical Installations 
### Lab 2.9: Explore Physical Connectivity 1
Complete this lab as follows: <br>
### View the current state of the first six ports on the Cisco switch and its accompany patch panel. <br>
Under Networking Closet, select Hardware.
Zoom in on the Cisco switch in the rack to view the power and network activity lights. <br>
Note: When a component's power light (the left light) is on, you know the device is plugged in and turned on. <br>
The network activity light (the right light) tells you which ports are connected to an active device. When this light is blinking, you know that network traffic is being transmitted through the port. <br>
![Example image](images/trb_net_comm_exp_1.jpg)
From the top right, select Questions. <br>
Answer Questions 1-3. <br>
Minimize the Lab Questions window. <br>
### Determine which computers are plugged into ports 1 and 3. <br>
From the Cisco switch, select the wires plugged into ports 1 and 3. <br>
Look at the patch panel and find the cables accompanying port. <br>
From the top right, select Questions. <br>
Answer Question 4. <br>
Minimize the Lab Questions window. <br>
### From the ITAdmin workstation, ping each of the following computers using the IP addresses shown below: <br>
![Example image](images/Lab2-9 table.jpg) <br>
From the top left, select Floor 1 Overview. <br>
Under IT Administration, select ITAdmin. <br>
Right-click Start and then select Terminal (Admin). <br>
Type ping ip_address and then press Enter. <br>
Make a note as to whether the ping was successful or not. <br>
Repeat step 3d for each remaining IP address. <br>
Answer Question 5-6. <br>
Minimize the Lab Questions window. <br>
### From ITAdmin, check for network connectivity.
From the taskbar, right-click the Network icon and select Network and Internet settings. <br>
From the diagram at the top, you are informed that you have an Ethernet connection. <br>
Below the diagram, select Ethernet. <br>
You are shown details about your network connection. <br>
Close the Settings app. <br>
### From the hardware view of ITAdmin, check for network connectivity and activity by viewing the network card's link lights.
From the top left, select IT Administration to view the hardware of the computers in this office. <br>
Above the ITAdmin workstation (not the monitor), select Back. Notice that: <br>
&emsp;* The link light for the network card is illuminated, indicating a physical connection (link) between this workstation and the next device (the network switch). <br>
&emsp;* The network activity light is blinking, indicating that network traffic is being transmitted on this connection. <br>
&emsp;* These two lights match what you saw when viewing the cables connecting ITAdmin to the Cisco switch and the patch panel. <br>
### From the Exec operating system, check for network connectivity.
From the top left, select Floor 1 Overview. <br>
Under Executive Office, select Exec. <br>
Right-click Start and then select Settings. <br>
Select Network & internet. <br>
Under the Network & internet heading, you see that this computer is not connected to any networks. <br>
Close the Settings app. <br>
### From the hardware view of Exec, check for network connectivity and activity by viewing the network card's link lights.
From the top left, select Executive Office to view the hardware for the computers in this office. <br>
Above the Exec workstation (not the laptop), select Back. <br>
Zoom in on the Ethernet cable and examine its link lights. <br>
The link and network activity lights for the Ethernet port with a cable plugged in are not illuminated. This indicates there is no connection to the switch. <br>
Possible causes for no connectivity include: <br>
&emsp;* A faulty or disconnected cable <br>
&emsp;* A bad network card (NIC) <br>
&emsp;* A faulty or disabled switch port <br>
### From Exec, test the possibility of a bad NIC by dragging the network cable from the existing network card to the onboard port.
Drag the Ethernet cable from its existing location to the Ethernet onboard port. <br>
Answer Question 7. <br>
### From the Exec operating system, check for network connectivity.
On the Exec monitor, select Click to view Windows 11. <br>
Use the ping command to try to access the following computers: <br>
&emsp;* Right-click Start and then select Terminal (Admin). <br>
&emsp;* Type ping 192.168.0.10 (the CorpServer) and press Enter. <br>
&emsp;* Type ping 163.128.1.1 (the ISP) and press Enter.
&emsp;* Both pings are successful. <br>
Right-click Start and then select Settings.
Select Network & internet. <br>
Under the Network & internet heading, you see that this computer is now connected to the internet. <br>
Close the Settings app. <br>
### In the Networking Closet, check the link light status for Exec.
From the top left, select Floor 1 Overview. <br>
Under Networking Closet, select Hardware. <br>
Zoom in on the Cisco switch. <br>
The network activity lights on the switch (port 1) are blinking, indicating that the Exec computer has a connection and network activity. <br>
### From the hardware view of Office1, check for network connectivity.
From the top left, select Floor 1 Overview. <br>
Under Office 1, select Hardware. <br>
Above the workstation, select Back. <br>
The link and network activity lights are not illuminated, indicating that there is no connection to the switch. <br>
Possible causes for no connectivity include: <br>
&emsp;* A faulty or disconnected cable <br>
&emsp;* A bad network card (NIC) <br>
&emsp;* A faulty or disabled switch port <br>
### Test the network cable for Office1.
Unplug the existing Ethernet cable from the wall plate and from the back of the computer. <br>
From the Shelf, expand Cables. <br>
Select the Cat6a Cable, RJ45 (a known good cable). <br>
From the Selected Component pane: <br>
&emsp;* Drag one RJ45 Connector to the Ethernet port (red) in the wall plate. <br>
&emsp;* Drag the other RJ45 Connector to the Ethernet port in the computer. <br>
&emsp; The link and network activity lights on the NIC still don't show an active connection. Therefore, the cable in the office wasn't the problem. <br>
### From the wiring closet, test the network patch cable for Office1.
From the top left, select Floor 1 Overview. <br>
Under Networking Closet, select Hardware. <br>
Remove the existing patch cable from Off 1 (Office 1) and from port 3. <br>
From the Shelf, select the Cat6a Cable. RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag one RJ45 Connector to the Off 1 port on the patch panel. <br>
&emsp;* Drag the other RJ45 Connector to the port 3 on the Cisco switch. <br>
&emsp; The link and network activity lights for port 3 indicate an active connection. The patch cable in the Network Closet was the problem. <br>
### From Office1, test the network connection to the following devices.
From the top left, select Floor 1 Overview. <br>
Under Office 1, select Office1. <br>
Right-click Start and then select Terminal (Admin). <br>
Ping the following devices: <br>
&emsp;* Office1: 192.168.0.30 <br>
&emsp;* Exec: 192.168.0.34 <br>
&emsp;* ISP: 163.128.1.1 <br>
&emsp; You are now able to ping all devices verifying local and internet connectivity. <br>
(Optional) <br>
Look at the Network icon in the Notification area. <br>
The icon indicates a normal network connection. <br>
Right-click Start and then select Settings. <br>
Select Network & internet. <br>
Under Status, you see that this computer is now connected to the internet. <br>
Close the Settings app. <br>
## Lab 2.10: Explore Physical Connectivity 2
Complete this lab by following these steps in order: <br>
### Locate the three servers in the rack.
Notice that three servers are listed under Networking Closet: <br>
&emsp;* CorpData <br>
&emsp;* CorpiSCSI <br>
&emsp;* CorpServer <br>
Under Networking Closet, select Hardware to view the hardware in this room. <br>
Scroll right to view all of the monitors. Notice that each is connected to a server (see the name on the monitor) and is currently running. <br>
Click on each server in the rack. Notice the name of the server in the Selected Component pane. <br>
From the top right, select Questions. <br>
Answer Question 1. <br>
Minimize the Lab Questions dialog. <br>
### From the Networking Closet, disconnect all three power plugs from the wall outlet and view the results.
Remove the three AC Power connectors from the wall outlets. <br>
&emsp;* The right two connectors come from the rack mount UPSs. <br>
&emsp;* The left connector comes from the small desktop UPS. <br>
From the top right, select Questions. <br>
Answer Question 2. <br>
Minimize the Lab Questions dialog. <br>
### Find the power source for the CorpServer.
Above the rack, select Back. <br>
Select the power cable on the back of CorpServer. <br>
Notice where the other end is plugged in. <br>
From the top right, select Questions. <br>
Answer Question 3. <br>
Minimize the Lab Questions dialog. <br>
### Find the power source for the CorpServer monitor.
Above the CorpServer (first) monitor, select Back. <br>
Select the power cable on the back of the monitor. <br>
Notice where the other end is plugged in. <br>
From the top right, select Questions. <br>
Answer Question 4. <br>
Minimize the Lab Questions dialog. <br>
### From CorpData, ping Office1 and the CorpNet router's internal interface.
On the CorpData monitor, select Click to view Linux. <br>
From the favorites bar, select Terminal. <br>
At the terminal prompt, enter the following commands: <br>
&emsp;* Type ping -c4 192.168.0.30 (Office1) and press Enter. <br>
&emsp;* Type ping -c4 198.28.56.1 (CorpNet Router's internal interface) and press Enter. <br>
&emsp; Note: The -c4 option limits the number of echo requests sent by the ping utility to four. <br>
From the top right, select Questions. <br>
Answer Question 5. <br>
Minimize the Lab Questions dialog. <br>
Close the Terminal window. <br>
### From the Networking Closet, move the male power connector for the switch from the non-critical load bank section to the critical load bank section.
From the top left, select Networking Closet. <br>
Move the AC Power Connector (Male), connected to the switch and UPS, from the UPS non-critical load bank (on the left) to the critical load bank (on the right). <br>
&emsp; Note: To identify the correct male AC Power Connector, select the power cable connected to the back of the switch (top); the other end of the cable will be outlined in the non-critical load bank section. <br>
### From the Networking Closet, switch to the Front view of the rack and observe any changes caused by moving the plug.
Above the rack, select Front. <br>
View the link and network activity lights. <br>
&emsp; The switch is now receiving power from the UPS battery and there are network activity lights. <br>
### Notice that power has not been restored to the CorpiSCSI monitor.
From CorpData, test network connectivity. <br>
On the CorpData monitor, select Click to view Linux. <br>
From the Terminal, ping the following devices: <br>
&emsp;* Type ping -c4 192.168.0.30 (Office1) and press Enter. <br>
&emsp;* Type ping -c4 198.28.56.1 (CorpNet Router's internal interface) and press Enter. <br>
&emsp;* Type ping -c4 163.128.80.93 (DNS) and press Enter. <br>
From the top right, select Questions. <br>
Answer Question 6. <br>
Minimize the Lab Questions dialog. <br>
### From the Networking Closet, reconnect the AC power cord from the UPSs back to the wall outlet.
From the top left, select Networking Closet. <br>
Under Partial Connections, select the AC Power Cable. <br>
From the Selected Component pane, drag the AC Power Connector (Male) connector to the wall plate. <br>
Repeat steps a and b for the second UPS power cable. <br>
Select the small UPS. <br>
From the Selected Component pane, drag the AC Power Connector (Male) connector to the wall plate. <br>
With these servers now receiving power from the wall plate, they can now be accessed. <br>
Select the power button on the CorpServer server. <br>
Return to the Networking Closet. <br>
Select the power button on the CorpiSCSI monitor. <br>
## Lab 2.11: Troubleshoot Physical Connectivity 1
Explanation <br>
While completing this lab, use the following information: <br>
![Example image](images/lab2_11 table.jpg) <br>
Complete this lab as follows: <br>
### From the Office1 computer, use the ping command to begin troubleshooting the connectivity problem.
Under Office 1, select Office1. <br>
Right-click Start and then select Terminal (Admin). <br>
From the PowerShell prompt, type ping workstation and then press Enter. <br>
Repeat step 1c for the remaining workstations. <br>
Notice that all the pings are successful except the ping to Office2 (192.168.0.31). <br>
From the Office2 computer, use the ping command to further troubleshoot the connectivity problem. <br>
From the top left, select Floor 1 Overview. <br>
### Under Office 2, select Office2.
Right-click Start and then select Terminal (Admin). <br>
From the PowerShell prompt, type ping workstation and then press Enter. <br>
Repeat step 2d for the remaining workstations. <br>
Notice that all the pings fail except to itself (192.168.0.31). <br>
### From Office2, check for a connection to the internet.
Right-click Start, and select Settings. <br>
Select Network & Internet. <br>
Notice that the diagram on the Status pane shows no connection to a network. <br>
Close the Settings dialog. <br>
### Check for a network connection by viewing the NIC port of the Office2 computer.
From the top left, select Office 2 to view the hardware in this office. <br>
Above the Office2 workstation, select Back to see the back of the computer tower.
The link and status lights on the NIC port are not blinking, indicating no connection to the network. This can be due to: <br>
&emsp;* A bad NIC
&emsp;* A faulty cable (easy to test)
&emsp;* An unplugged cable (easy to test)
&emsp;* A turned-off or faulty switch or hub port
Confirm that the network cable is connected to the NIC and the wall plate by selecting the cable plugged into the NIC. <br>
Notice that both ends of the cable are connected correctly. This means that the Ethernet cable could be faulty.
### Replace the network cable from Office2 and the wall.
Select the network cable plugged into Office2 and drag it to the shelf. <br>
Drag the RJ45 cable from the wall plug to the shelf. <br>
Under Shelf, select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to the network wall plug. <br> <br>
&emsp;* Drag the unconnected RJ45 Connector to the NIC on the back of the Office2 computer.
&emsp; Notice that the link and status lights for the connection are not green and active. This means that the cable may not have been bad. It's time to check for issues in the Networking Closet. <br>
### From the Networking Closet, check the switch to ensure that it's powered on.
From the top left, select Floor 1 Overview. <br>
Under Networking Closet, select Hardware. <br>
&emsp; Notice that the system light for the switch indicates that it is powered on. <br>
Observe the activity lights for all ports on the switch. <br>
&emsp; Notice that there is no activity for Port 4. Possible causes include: <br>
&emsp;* The cable between Office 2's patch panel port and the switch is bad or disconnected. <br>
&emsp;* Port 4 on the switch is disabled or shut down.
### Verify that the network cable is connected to Office2's patch panel port and the switch.
Select Port 4 on the switch. <br>
&emsp; Notice that it shows the cable is also plugged into the patch panel. This may mean that this cable is faulty. <br>
### Replace the patch panel cable for Office2 to the switch.
Select the cable plugged into Port 4 and drag it to the workspace. <br>
From the patch panel, drag the cable plugged into Off 2 to the workspace. <br>
Under Shelf, select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to Port 4 on the switch. <br>
&emsp;* Drag the unconnected RJ45 Connector to the patch panel port for Off 2 (Office 2). <br>
&emsp; Notice that the link and status lights for Port 4 are now green and active. <br>
### From Office 2, check for a network connection. <br>
From the top left, select Floor 1 Overview. <br>
Under Office 2, select Hardware. <br>
Check for an active link light on the network card of the computer. <br>
The light is blinking, indicating a network connection. <br>
On the Office2 monitor, select Click to view Windows 11. <br>
Right-click Start and select Settings. <br>
Select Network & Internet. <br>
The diagram in Status page shows a connection to the network and internet. <br>
(Optional) Ping each workstation in the network. <br>
Each ping attempt now succeeds. <br>
### From Office 1, use the ping command to verify connectivity to Office 2.
From the top left, select Floor 1 Overview. <br>
Under Office 1, select Office1. <br>
From the PowerShell prompt, type ping Office2 and then press Enter. <br>
Notice that the ping to Office 2 succeeds. The problem is resolved. <br>
&emsp; Replacing the NIC in Office 2 and making a console connection to the switch to confirm if port 2 is disabled are two viable approaches to this problem. Yet, as indicated earlier, you should look for common errors or solutions that you can test quickly. Think about and check cables, power, and connectivity first when troubleshooting. <br>
## Lab 2.12: Troubleshoot Physical Connectivity 2
While completing this lab, use the following information: <br>
![Example image](images/lab2_12 table.jpg) <br>
Complete this lab as follows: <br>
### From the IT Administration office, ping each workstation on the network.
Under IT Administration, select ITAdmin. <br>
Right-click Start and select Terminal (Admin). <br>
From the PowerShell prompt, type ping [workstation's IP] and then press Enter. <br>
&emsp; Notice that all the pings are successful except the one to Office2. This verifies that there is connectivity between all other workstations on the network except Office2. This indicates that the scope of the problem is probably limited to Office2. Because the scope of the problem is currently limited to Office2, you should look for common errors or solutions that you can test quickly. <br>
### Confirm that the network cable is connected to the NIC and the wall plate.
From the top left, select Floor 1 Overview. <br>
Under Office 2, select Hardware to view the hardware in Office 2. <br>
Above the Office2 desktop computer system, select Back to view the back of the computer.
Notice that an Ethernet cable is plugged into the network card in the computer. <br>
Select the Ethernet RJ45 shielded cable that is plugged into the computer. <br>
Scroll to the right and view the Ethernet wall plate. <br>
Notice that the cable in the computer is plugged into the Ethernet port on the wall plate. <br>
Scroll back to the computer and check for activity lights for the network port. <br>
Notice that no lights are blinking. This indicates that there is no connection to the network. <br>
### From Office2, replace the cable between the workstation and the wall plate.
Drag the Ethernet cable from the back of the computer and place it on the workspace. <br>
Drag the Ethernet cable from the wall plate and place it on the workspace. <br>
Under Shelf, expand Cables. <br>
Select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Shielded Connector to the Ethernet port on the computer. <br>
&emsp;* Drag the unconnected RJ45 Shielded Connector to the Ethernet port on the wall plate. <br>
&emsp; The lights for the network card are still not active. You could replace the NIC in Office2, but replacing cables is quicker. <br>
### From the Networking Closet, check the switch to ensure it is powered on.
From the top left, select Floor 1 Overview. <br>
Under Networking Closet, select Hardware. <br>
&emsp; Notice that the power light for the Cisco switch indicates that it is powered on. Also, since the workstation in the IT Administration office can communicate through the switch, so you know that the device is not turned off, and is functioning properly. <br>
### From the Networking Closet, observe the activity lights for all ports and check for cable connections.
Zoom in on the switch ports. <br>
&emsp; Notice that there are activity lights for other ports, yet there is a lack of activity for port 4. <br>
&emsp; Possible causes include: <br>
&emsp;* The cable between Office 2's patch panel port and the switch is bad or disconnected. <br>
&emsp;* Port 4 on the switch is disabled or shut down. <br>
Select the cable plugged into Off 2. <br>
&emsp; Notice that the other end of the cable (which is highlighted) is plugged into port 4. <br>
### From the Networking Closet, replace the patch panel cable.
Drag the Ethernet cable from Off 2 and place it on the workspace. <br>
Drag the Ethernet cable from port 4 and place it on the workspace. <br>
Under Shelf, expand Cables. <br>
Select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Shielded Connector to Off 2. <br>
&emsp;* Drag the unconnected RJ45 Shielded Connector to port 4. <br>
The activity light for port 4 still does not indicate network activity. <br>
&emsp; Making a console connection to the switch to confirm that port 4 is enabled is a viable approach to this problem, but the lab does not provide a console application to confirm the switch's port settings. <br>
### From Office 2, add a known good spare NIC to the Office2 computer and connect the Ethernet cable to the new card.
From the top left, select Floor 1 Overview. <br>
Under Office 2, select Hardware. <br>
Above the computer, select Front. <br>
Select the power button to turn the computer off. <br>
Above the computer, select Motherboard to open the case. <br>
Under Shelf, expand Network Adapters. <br>
Drag Network adapter, Ethernet 1000BaseTX, PCIe to the PCIe slot on the motherboard. <br>
Above the computer, select Back to replace the case. <br>
Drag the Ethernet cable from its existing NIC to the new NIC just added. <br>
### Power on the Office2 computer and test connectivity to the network.
Above the computer, select Front. <br>
Select the power button to turn the computer on. <br>
Right-click Start and then select Terminal (Admin). <br>
At the PowerShell prompt, type ipconfig. <br>
Notice that Office2 received a new/different IP address from the DHCP server because the new NIC makes it look like a different computer. <br>
From the PowerShell prompt, type ping [workstation's IP] and then press Enter. <br>
Repeat step 8e for each remaining computer. <br>
All pings are now successful. <br>
## Lab 2.13: Troubleshoot Physical Connectivity 3
While completing this lab, use the following information: <br>
![Example image](images/lab2_13 table.jpg) <br>
Complete this lab as follows: <br>
### From Exec, use the ping command to begin troubleshooting the connectivity problem.
Under Executive Office, select Exec. <br>
Right-click Start and then select Terminal (Admin). <br>
From the PowerShell prompt, type ping workstation IP address and then press Enter. <br>
Repeat step 1c for the remaining workstations. <br>
Notice that all the pings fail except to itself (192.168.0.34). <br>
### From Support, repeat the same troubleshooting steps used in the Executive Office to further discover the scope of the problem.
From the top left, select Floor 1 Overview. <br>
Under Support Office, select Support. <br>
From the Favorites bar, select Terminal. <br>
From the terminal prompt, type ping workstation IP address and then press Enter. <br>
If needed, press Ctrl + C to stop the pinging process. <br>
&emsp; Notice that all the pings fail except the ping to itself (192.168.0.32). <br>
With matching results from both computers, the problem is most likely shared with the other workstations. <br>
&emsp; Because the scope of the problem includes two offices, you should look for common errors or solutions that you can test quickly. <br>
### From Exec, check for a connection to the network.
From the top left, select Floor 1 Overview. <br>
Under Executive Office, select Exec. <br>
Right-click Start and select Settings. <br>
Select Network & internet. <br>
Notice that the diagram on the Status pane shows that the network connection is not connected to a network. <br>
Close the Settings dialog. <br>
### Check for a network connection by viewing the computer's NIC port.
From the top left, select Executive Office to view the hardware in this office. <br>
Above the Exec workstation, select Back to see the back of the computer tower. <br>
Notice that the link and status lights on the NIC port are not blinking, indicating no connection to the network. This can be due to: <br>
&emsp;* A bad NIC <br>
&emsp;* A faulty cable (easy to test) <br>
&emsp;* An unplugged cable (easy to test) <br>
&emsp;* A turned off or faulty switch or hub port <br>
### Replace the network cable from Exec and the wall.
Select the cable plugged into Exec and drag it to the shelf. <br>
Drag the RJ45 cable from the wall plate to the shelf. <br>
Under Shelf, select Cat6a Cable, RJ45. <br>
From the Selected Component pane: <br>
&emsp;* Drag an RJ45 Connector to the network wall plate. <br>
&emsp;* Drag the unconnected RJ45 Connector to the NIC on the back of the Exec computer. <br>
&emsp; Notice that the link and status lights for the connection are still not green and active. This means that the cable may not have been bad. It's time to check for issues in the Networking Closet. <br>
### From the Networking Closet, check the switch to ensure that it's powered on.
From the top left, select Floor 1 Overview. <br>
Under Networking Closet, select Hardware. <br>
&emsp; Notice that the system light for the switch indicates that it is powered off. In addition, since the workstations in the Support Office and the Executive Office could not successfully ping the network, you can conclude that the device is turned off. <br>
Check to see if the switch has power. <br>
Above the rack, select Back to switch to the back view of the rack. <br>
Select the switch's power cable and verify that it is plugged into the UPS. <br>
&emsp; Notice that the switch is plugged into the UPS, but it is not plugged into the critical load section. This means that if the main power goes off, the switch loses power as well. <br>
Move the switch's power cable from the non-critical load (Bank 2) outlet to the empty critical load (Bank 1) outlet. <br>
Notice that the Ethernet cables plugged into the server have link status lights that indicate they have power and a connection. <br>
Above the rack, select Front to switch to the front view of the rack. <br>
Observe the power light and activity lights for all ports on the switch. <br>
&emsp; The lights are all on and active (except for the wireless access point, as it is still connected to the non-critical load (Bank 2) on the UPS). <br>
### From the Executive Office, check for a network connection.
From the top left, select Floor 1 Overview. <br>
Under Executive Office, select Hardware. <br>
Check for an active light on the computer's network card. <br>
The light is blinking, indicating a network connection. <br>
On the Exec monitor, select Click to view Windows 11. <br>
Right-click Start and select Settings. <br>
Select Network & internet. <br>
The diagram in Status page shows a connection to the network and internet. <br>
(Optional) Ping each workstation on the network using their IP address. <br>
Each ping attempt now succeeds. <br>
## Lab 2.14: Troubleshoot Physical Connectivity 4
Complete this lab as follows: <br>
### From the Office 1 computer, use the ping command to begin troubleshooting the connectivity problem.
Under Office 1, select Office1. <br>
Right-click Start and then select Terminal (Admin). <br>
From the PowerShell prompt, ping the following computers: <br>
&emsp;* CorpServer: Type ping 192.168.0.10 and then press Enter. <br>
&emsp;* Office2: Type ping 192.168.0.31 and then press Enter. <br>
&emsp;* ITAdmin: Type ping 192.168.0.33 and then press Enter. <br>
&emsp; Notice that all the pings fail. <br>
### Check for a connection to the internet using the Settings app.
Right-click Start and then select Settings. <br>
Select Network & Internet. <br>
&emsp; Notice that the diagram on the Status pane shows that the computer is not connected to a network. <br>
Close the Settings dialog. <br>
### Check for a network connection by viewing the NIC port of the Office1 computer.
From the top left, select Office 1 to view the hardware in this office. <br>
Above the Office1 workstation, select Back to see the back of the computer. <br>
&emsp; Notice that there is no Ethernet cable attached to the computer. However, there is an Ethernet cable plugged into the wall plate. The cable could have been accidentally disconnected from the computer when the user added the speakers. <br>
### Connect the network cable from the wall outlet to Office1.
Select the Ethernet cable plugged into the wall plate. <br>
From the Selected Component pane, drag the unconnected RJ45 Shielded Connector to the NIC on the back of the Office1 computer. <br>
&emsp; Notice that the status and link lights on the NIC are green and active. <br>
### Check for network connectivity from Office1.
On the Office1 monitor, select Click to view Windows 11. <br>
Right-click Start and select Settings. <br>
Select Network & Internet. <br>
T&emsp; he diagram on the Status page shows a connection to the network and internet. <br>
(Optional) Ping each workstation on the network. <br>
Each ping attempt now succeeds. <br>