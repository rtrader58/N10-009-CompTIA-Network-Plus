# Module 10 (Labs 10-19): Applying Network Security Features
## Lab 10.10: Disable Switch Ports - GUI
Complete this lab as follows: <br>
### Log in to the CISCO switch.
In the Google Chrome URL field, enter 192.168.0.2 and press Enter. <br>
Maximize the window for better viewing. <br>
In the Username and Password fields, enter cisco (case sensitive). <br>
Select Log In. <br>
### Disable port GE9.
From the left navigation bar, expand and select Port Management > Port Settings. <br>
Select GE9 (port 9) and then select Edit. <br>
For Administrative Status, select Down. <br>
Select Apply. <br>
Select Close. <br>
### Copy GE9 port settings to ports 12 and 14-17.
Select GE9 and then select Copy Settings. <br>
Type 12,14-17 in the To: field. <br>
Select Apply. <br>
### Save the changes to the switch's startup configuration file.
From the upper right of the switch window, select Save. <br>
For Source File Name, make sure Running configuration is selected. <br>
For Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
Select Done. <br>
## Lab 10.11: Harden a Switch
While completing this lab, use the following information:
![Example image](images/lab10_11_table.jpg) <br>
Complete this lab as follows: <br>
### Shut down the unused ports.
Under Initial Setup, select Configure Port Settings. <br>
Select the GE2 port. <br>
Scroll down and select Edit. <br>
Under Administrative Status, select Down. <br>
Scroll down and select Apply. <br>
Select Close. <br>
With the GE2 port selected, scroll down and select Copy Settings. <br>
In the Copy configuration field, enter the remaining unused ports. (View the example for the proper syntax.) <br>
Select Apply. From the Port Setting Table, in the Port Status column, you can see that all the ports are down now. <br>
### Configure the Port Security settings.
From the left menu, expand Security. <br>
Select Port Security. <br>
Select the GE1 port. <br>
Scroll down and select Edit. <br>
For Interface Status, select Lock. <br>
For Learning Mode, make sure Classic Lock is selected. <br>
For Action on Violation, make sure Discard is selected. <br>
Select Apply. <br>
Select Close. <br>
Scroll down and select Copy Settings. <br>
Enter the remaining used ports. (View the example for the proper syntax.) <br>
Select Apply. <br>
## Lab 10.12: Configure Network Security Appliance Access
Complete this lab as follows: <br>
### Access the pfSense management console.
From the taskbar, select Google Chrome. <br>
Maximize the window for better viewing. <br>
In the Google Chrome address bar, enter 198.28.56.22 and then press Enter. <br>
Enter the pfSense sign-in information as follows: <br>
&emsp; * Username: admin <br>
&emsp; * Password: pfsense <br>
Select SIGN IN. <br>
### Change the password for the default (admin) account.
From the pfSense menu bar, select System > User Manager. <br>
For the admin account, under Actions, select the Edit user icon (pencil). <br>
For Password, change to P@ssw0rd (0 = zero). <br>
Enter P@ssw0rd in the Confirm Password field. <br>
Scroll to the bottom and select Save. <br>
### Create and configure a new pfSense user.
Select Add. <br>
Enter lyoung as the username. <br>
Enter C@nyouGuess!t in the Password field. <br>
Enter C@nyouGuess!t in the Confirm Password field. <br>
Enter Liam Young in Full Name field.
For Group membership, select admins and then select Move to "Member of" list. <br>
Scroll to the bottom and select Save. <br>
### Set a session timeout for pfSense.
Under the System breadcrumb, select Settings. <br>
For Session timeout, enter 20. <br>
Select Save. <br>
### Disable the webConfigurator anti-lockout rule for HTTP.
From the pfSense menu bar, select System > Advanced. <br>
Under webConfigurator, for Protocol, select HTTP. <br>
Scroll down and select Anti-lockout to disable the webConfigurator anti-lockout rule. <br>
Scroll to the bottom and select Save. <br>
## Lab 10.13: Configure a Security Appliance
Complete this lab as follows: <br>
### Access the pfSense management console.
Sign in using the following case-sensitive information: <br>
&emsp; * Username: admin <br>
&emsp; * Password: P@ssw0rd <br>
Select SIGN IN or press Enter. <br>
### Configure the DNS Servers.
From the pfSense menu bar, select System > General Setup. <br>
Under DNS Server Settings, configure the primary DNS Server as follows: <br>
&emsp; * Address: 163.128.78.93 <br>
&emsp; * Hostname: DNS1 <br>
&emsp; * Gateway: None <br>
Select Add DNS Server to add a secondary DNS Server and then configure it as follows: <br>
&emsp; * Address: 163.128.80.93 <br>
&emsp; * Hostname: DNS2 <br>
&emsp; * Gateway: None <br>
Scroll to the bottom and select Save. <br>
### Configure the WAN settings.
From the pfSense menu bar, select Interfaces > WAN. <br>
Under General Configuration, ensure Enable interface is selected. <br>
Use the IPv4 Configuration Type drop-down to select Static IPv4. <br>
Under Static IPv4 Configuration, in the IPv4 Address field, enter 65.86.24.136. <br>
Use the IPv4 Address subnet drop-down to select 8. <br>
Under Static IPv4 Configuration, select Add a new gateway. <br>
Configure the gateway settings as follows: <br>
&emsp; * Default: Select Default gateway <br>
&emsp; * Gateway name: Enter WANGateway <br>
&emsp; * Gateway IPv4: 65.86.1.1 <br>
Select Add. <br>
Scroll to the bottom and select Save. <br>
Select Apply Changes. <br>
## Lab 10.14: Configure a Perimeter Firewall
Complete this lab as follows: <br>
### Sign in to the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Create and configure a firewall rule to pass HTTP traffic from the WAN to the Web server in the DMZ.
From the pfSense menu bar, select Firewall > Rules. <br>
Under the Firewall breadcrumb, select DMZ. <br>
Select Add (either one). <br>
Make sure Action is set to Pass. <br>
Under Source, use the drop-down to select WAN net. <br>
Under Destination, use the Destination drop-down to select Single host or alias. <br>
In the Destination Address field, enter 172.16.1.5. <br>
Using the Destination Port Range drop-down, select HTTP (80). <br>
Under Extra Options, in the Description field, enter HTTP from WAN to DMZ. <br>
Select Save. <br>
Select Apply Changes. <br>
### Create and configure a firewall rule to pass HTTPS traffic from the WAN to the Web server in the DMZ.
For the rule just created, select the Copy icon (two files). <br>
Under Destination, change the Destination Port Range to HTTPS (443). <br>
Under Extra Options, change the Description field to HTTPS from WAN to DMZ. <br>
Select Save. <br>
Select Apply Changes. <br>
### Create and configure a firewall rule to pass all traffic from the LAN network to the DMZ network.
Select Add (either one). <br>
Make sure Action is set to Pass. <br>
For Protocol, use the drop-down to select Any. <br>
Under Source, use the drop-down to select LAN net. <br>
Under Destination, use the drop-down to select DMZ net. <br>
Under Extra Options, change the Description field to LAN to DMZ Any. <br>
Select Save. <br>
Select Apply Changes. <br>
## Lab 10.15: Restrict Telnet and SSH Access
Complete this lab as follows: <br>
### Enter the configuration mode for the router:
From the exhibit, select the router. <br>
From the terminal, press Enter. <br>
Type enable and then press Enter. <br>
Type config term and then press Enter. <br>
### From the terminal, create a standard numbered access list using number 5. Add a permit statement for each network to the access list.
Type access-list 5 permit 192.168.1.0  0.0.0.255 and then press Enter. <br>
Type access-list 5 permit 192.168.2.0  0.0.0.255 and then press Enter. <br>
Type access-list 5 permit 192.168.3.0  0.0.0.255 and then press Enter. <br>
### Apply the access list to VTY lines 0–4. Filter incoming traffic.
Type line vty 0 4 and then press Enter. <br>
Type access-class 5 in and then press Enter. <br>
Press Ctrl + Z. <br>
### Save your changes in the startup-config file.
Type copy run start and then press Enter. <br>
Press Enter to begin building the configuration. <br>
Press Enter. <br>
## Lab 10.16: Permit Traffic
Complete this lab as follows: <br>
### Enter the configuration mode for the Fiji router:
From the exhibit, select the Fiji router. <br>
From the terminal, press Enter. <br>
Type enable and then press Enter. <br>
Type config term and then press Enter. <br>
### From the terminal, add a permit any statement to Access List 11 to allow all traffic other than the restricted traffic.
Type access-list 11 permit any and press Enter. <br>
Press Ctrl + Z. <br>
### Save your changes in the startup-config file.
Type copy run start and then press Enter. <br>
Press Enter to begin building the configuration. <br>
Press Enter. <br>
## Lab 10.17: Block Source Hosts
Complete this lab as follows: <br>
### Enter the configuration mode for the router:
From the exhibit, select the router. <br>
From the terminal, press Enter. <br>
Type enable and then press Enter. <br>
Type config term and then press Enter. <br>
### From the terminal, create a standard numbered access list using number 25. Add statements to the access list to block traffic to the required hosts.
Type access-list 25 deny host 199.68.111.199 and press Enter. <br>
Type access-list 25 deny host 202.177.9.1 and press Enter. <br>
Type access-list 25 deny host 211.55.67.11 and press Enter. <br>
### From the terminal, add a statement to allow all other traffic from all other hosts, by typing access-list 25 permit any and pressing Enter.
### From the terminal, apply Access List 25 to the Serial0/0/0 interface to filter incoming traffic.
Type int s0/0/0 and press Enter. <br>
Type ip access <br>
### Applied Live Lab 10.18: Troubleshoot Service and Security Issues
Live Lab. <br>