# Module 10 Labs: Applying Network Security Features
## Live Lab 10.1: Deploy a Digital Certificate
Live Lab. <br>
## Lab 10.2: Manage Account Policies
While completing this lab, use the following information: <br>
![Example image](lab10_2table.jpg) <br>
Complete this lab as follows: <br>
### Access the CorpDC virtual server.
In Hyper-V Manager, select CORPSERVER. <br>
Under Virtual Machines, double-click CorpDC to connect to the virtual server. <br>
### Modify password policies.
From Server Manager, select Tools > Group Policy Management. <br>
Maximize the window for better viewing. <br>
From the left pane, expand Forest: CorpNet.local > Domains > CorpNet.local. <br>
Right-click Default Domain Policy and select Edit. <br>
Maximize the window for better viewing. <br>
Under Computer Configuration, expand Policies > Windows Settings > Security Settings > Account Policies. <br>
Select Password Policy. <br>
From the right pane, double-click the policy that you want to edit. <br>
Make sure that Define this policy setting is selected. <br>
Edit the value for the policy and then select OK. <br>
Repeat steps 2h–2j for each policy. <br>
### Modify account lockout policies.
From the left pane, select Account Lockout Policy. <br>
From the right pane, double-click the policy that you want to edit. <br>
Make sure that Define this policy setting is selected. <br>
Edit the value for the policy and then select OK. <br>
Repeat steps 3b–3d for additional policies. <br>
## Live Lab 10.3: Configure Management Privileges
Live Lab. <br>
## Lab 10.4: View Linux Services
Complete this lab as follows: <br>
### Start the Bluetooth service using the systemctl command.
From the Favorites bar, select Terminal. <br>
At the prompt, type systemctl start bluetooth.service and then press Enter. <br>
Type systemctl is-active bluetooth.service to verify that the service is active. <br>
### Stop the Bluetooth service using the systemctl command.
At the prompt, type systemctl stop bluetooth.service and then press Enter. <br>
Type systemctl is-active bluetooth.service to verify that the service is inactive. <br>
### Restart the Bluetooth service using the systemctl command.
At the prompt, type systemctl restart bluetooth.service and then press Enter. <br>
Type systemctl is-active bluetooth.service to verify that the service is active. <br>
## Lab 10.5: Scan for Unsecure Protocols
Complete this lab as follows: <br>
### From the Analyst-Lap computer, find the domain name servers used by partnercorp.xyz.
From the taskbar, select Google Chrome. <br>
Maximize the windows for better viewing. <br>
In the URL field, type whois.org and press Enter. <br>
In the Search for a domain name field, enter partnercorp.xyz. <br>
Select Search <br>
In the top right, select Questions. <br>
Answer Question 1. <br>
### Find the IP address used by www.partnernetcorp.xyz.
Right-click Start and select Terminal (Admin). <br>
At the PowerShell prompt, type nslookup www.partnercorp.xyz name_server (see the answer to question 1) and press Enter. <br>
Answer Question 2. <br>
Minimize the question dialog. <br>
### Use Zenmap to run an Nmap command to scan for open ports.
From the navigation tabs, select Buildings. <br>
Under Blue Cell, select Analyst-Lap2. <br>
From the Favorites bar, select Zenmap. <br>
Maximize Zenmap for easier viewing. <br>
In the Command field, use nmap --top-ports 50 73.44.215.0/24 to scan for open ports. <br>
Select Scan to scan for open ports on all servers located on this network. <br>
In the top right, select Questions. <br>
Answer Question 3. <br>
## Lab 10.6: Enable and Disable Linux Services
Complete this lab as follows:
### Enable the Anaconda service.
From the favorites bar, launch a terminal. <br>
At the prompt, type systemctl enable anaconda.service and then press Enter. <br>
Type systemctl is-enabled anaconda.service and then press Enter to check the service's status.
### Disable the VMware tools service.
Type systemctl disable vmtoolsd.service and press Enter. <br>
Type systemctl is-enabled vmtoolsd.service and press Enter to check the service's status. <br>
## Lab 10.7: Disable Network Service
While completing this lab, use the following information: <br>
Ports to scan: <br>
&emsp; * 3389 - Remote Desktop Services (TermServices) <br>
&emsp; * 5900 - VNC Server (vncserver) <br>
&emsp; * Computer identification: <br>
![Example image](lab10_7table.jpg) <br>
Complete this lab as follows: <br>
### Using Zenmap, scan the network for open remote access ports.
From the Favorites bar, select Zenmap. <br>
Maximize the window for better viewing. <br>
In the Command field, use nmap -p [port number] 192.168.0.0/24 to scan the port. <br>
Select Scan (or press Enter) to scan the subnet for a given service. <br>
Using the table in the scenario, identify the computer(s) with the open port using the IP address found. <br>
From the top right, select Questions. <br>
Answer Question 1. <br>
Repeat steps 1c-1e and then answer Question 2. <br>
### For computers that have a remote access service port open, disable and then stop the applicable service from running.
From the top left, select Floor 1 Overview. <br>
Select the computer with the remote access service port open. If needed, minimize or move the Lab Questions dialog. <br>
Right-click Start and select Computer Management. <br>
From the left pane, expand and select Services and Applications > Services. <br>
Maximize the window for better viewing. <br>
Double-click the service (Remote Desktop Services or VNC Server) that needs to be stopped. <br>
Using the Startup type drop-down menu, select Disabled. <br>
Under Service status, select Stop. <br>
Select OK. <br>
Repeat step 2a-2i. <br>
From the top right, select Questions. <br>
&emsp; You would also want to remove or uninstall these services. <br>
## Lab 10.7: Disable Network Service
While completing this lab, use the following information: <br>
&emsp; * Ports to scan: <br>
&emsp; &emsp; * 3389 - Remote Desktop Services (TermServices) <br>
&emsp; &emsp; * 5900 - VNC Server (vncserver) <br>
&emsp; * Computer identification: <br>
![Example image](images/lab10_7_table.jpg) <br>
Complete this lab as follows: <br>
### Using Zenmap, scan the network for open remote access ports.
From the Favorites bar, select Zenmap. <br>
Maximize the window for better viewing. <br>
In the Command field, use nmap -p [port number] 192.168.0.0/24 to scan the port. <br>
Select Scan (or press Enter) to scan the subnet for a given service. <br>
Using the table in the scenario, identify the computer(s) with the open port using the IP address found. <br>
From the top right, select Questions. <br>
Answer Question 1. <br>
Repeat steps 1c-1e and then answer Question 2. <br>
### For computers that have a remote access service port open, disable and then stop the applicable service from running.
From the top left, select Floor 1 Overview. <br>
Select the computer with the remote access service port open. If needed, minimize or move the Lab Questions dialog. <br>
Right-click Start and select Computer Management. <br>
From the left pane, expand and select Services and Applications > Services. <br>
Maximize the window for better viewing. <br>
Double-click the service (Remote Desktop Services or VNC Server) that needs to be stopped.
Using the Startup type drop-down menu, select Disabled. <br>
Under Service status, select Stop. <br>
Select OK. <br>
Repeat step 2a-2i. <br>
From the top right, select Questions. <br>
&emsp; You would also want to remove or uninstall these services. <br>
### Lab 10.8: Secure Access to a Switch
Complete this lab as follows: <br>
### Create and configure an Access Profile named MgtAccess.
From the left pane, expand and select Security > Mgmt Access Method > Access Profiles. <br>
Select Add. <br>
Enter the Access Profile Name of MgtAccess. <br>
Enter the Rule Priority of 1. <br>
For Action, select Deny. <br>
Select Apply and then select Close. <br>
### Add a profile rule to the MgtAccess profile.
From the left pane, under Security > Mgmt Access Method, select Profile Rules. <br>
From the right pane, select the MgtAccess profile and then select Add. <br>
Enter a Rule Priority of 2. <br>
For Management Method, select HTTP. <br>
For Applies to Source IP Address, select User Defined. <br>
For IP Address, enter 192.168.0.10. <br>
For Mask, enter a Network Mask of 255.255.255.0. <br>
Select Apply and then select Close. <br>
### Set the MgtAccess profile as the active access profile.
From the left pane, under Security > Mgmt Access Method, select Access Profiles. <br>
Use the Active Access Profile drop-down list to select MgtAccess. <br>
Select Apply. <br>
Select OK. <br>
S### ave the changes to the switch's startup configuration file. <br>
At the top, select Save. <br>
On the right, under Source File Name, make sure Running configuration is selected. <br>
For the Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
## Lab 10.9: Secure Access to a Switch 2
While completing this lab, use the following information: <br>
&emsp; * Configure the GameConsoles MAC-based access control entry (ACE) settings as follows: <br>
![Example image](images/lab10_9_table.jpg) <br>
Complete this lab as follows: <br>
### Create the GameConsoles ACL.
From the Getting Started page, under Quick Access, select Create MAC-Based ACL. <br>
Select Add. <br>
In the ACL Name field, enter GameConsoles. <br>
Select Apply and then select Close. <br>
Create a MAC-based access control. <br>
### Select MAC-Based ACE Table.
Select Add. <br>
Enter the priority. <br>
Select the action. <br>
For Destination MAC Address, make sure Any is selected. <br>
For Source MAC Address, select User Defined. <br>
Enter the source MAC address value. <br>
Enter the source MAC address mask. <br>
Select Apply. <br>
Repeat steps 2c–2i for the remaining ACE entries. <br>
Select Close. <br>
### Bind the GameConsoles ACL to all of the interfaces.
From the left pane, under Access Control, select ACL Binding (Port). <br>
Select GE1. <br>
At the bottom of the window, select Edit. <br>
Select Select MAC-Based ACL. <br>
Select Apply and then select Close. <br>
Select Copy Settings. <br>
In the Copy configuration's to field, enter 2-30. <br>
Select Apply. <br>
### Save the Configuration.
From the top of the window, select Save. <br>
Under Source File Name, make sure Running configuration is selected. <br>
Under Destination File Name, make sure Startup configuration is selected. <br>
Select Apply. <br>
Select OK. <br>
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