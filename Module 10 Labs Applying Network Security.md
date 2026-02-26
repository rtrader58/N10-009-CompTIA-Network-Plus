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

