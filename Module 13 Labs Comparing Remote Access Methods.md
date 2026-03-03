# Module 13 Labs: Comparing Remote Access Methods
## Lab 13.1: Configure a Remote Access VPN
While completing this lab, use the following information: <br>
Create and configure the following standard remote VPN users: <br>
![Example image](images/lab13_1_table.jpg) <br>
Complete this lab as follows: <br>
### Sign in to the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Start the VPN wizard and select the authentication backend type.
From the pfSense menu bar, select VPN > OpenVPN. <br>
From the breadcrumb, select Wizards. <br>
Under Select an Authentication Backend Type, make sure Local User Access is selected. <br>
Select Next. <br>
### Create a new certificate authority certificate.
For Descriptive Name, enter CorpNet-CA. <br>
For Country Code, enter GB. <br>
For State, enter Cambridgeshire. <br>
For City, enter Woodwalton. <br>
For Organization, enter CorpNet. <br>
Select Add new CA. <br>
### Create a new server certificate.
For Descriptive Name, enter CorpNet. <br>
Verify that all of the previous changes (Country Code, State/Providence, and City) are the same. <br>
Use all other default settings. <br>
Select Create new Certificate. <br>
### Configure the VPN server.
Under General OpenVPN Server Information: <br>
&emsp; * Use the Interface drop-down menu to select WAN. <br>
&emsp; * Verify that the Protocol is set to UDP on IPv4 only. <br>
&emsp; * For Description, enter CorpNet-VPN. <br>
Under Tunnel Settings: <br>
&emsp; * For Tunnel Network, enter 198.28.20.0/24. <br>
&emsp; * For Local Network, enter 198.28.56.18/24. <br>
&emsp; * For Concurrent Connections, enter 4. <br>
Under Client Settings, in DNS Server1, enter 198.28.56.1. <br>
Select Next. <br>
### Configure the firewall rules.
Under Traffic from clients to server, select Firewall Rule. <br>
Under Traffic from clients through VPN, select OpenVPN rule. <br>
Select Next. <br>
Select Finish. <br>
### Set the OpenVPN server just created to Remote Access (User Auth).
For the WAN interface, select the Edit Server icon (pencil). <br>
For Server mode, use the drop-down and select Remote Access (User Auth). <br>
Scroll to the bottom and select Save. <br>
### Configure the following Standard VPN users.
From the pfSense menu bar, select System > User Manager. <br>
Select Add. <br>
Configure the User Properties as follows: <br>
&emsp; * Username: Username <br>
&emsp; * Password: Password <br>
&emsp; * Full name: Fullname <br>
Scroll to the bottom and select Save. <br>
Repeat steps 8b-8d to create the remaining VPN users. <br>
## Lab 13.2 : Configure an iPad VPN Connection
Complete this lab as follows: <br>
### Verify your connection to the Home-Wireless network.
Select Settings. <br>
Select Wi-Fi. <br>
From the right, notice that you are connected to the Home-Wireless network. <br>
### Add and configure a VPN.
From the left menu, select General. <br>
From the right menu, select VPN. <br>
Select Add VPN Configuration. <br>
Select IPSec. <br>
Configure the IPSec options as follows: <br>
&emsp; * Description: CorpNetVPN. <br>
&emsp; * Server: 198.28.56.22 <br>
A&emsp; * ccount: mbrown <br>
&emsp; * Secret: asdf1234$ <br>
In the upper right, select Save. <br>
### Connect to the VPN just created.
Under VPN Configuration, slide Not Connected to ON. <br>
When prompted, enter L3tM31nN0w (0 = zero) as the password. <br>
Select OK. <br>
## Lab 13.3: Configure a RADIUS Solution
To complete this lab, use the following information: <br>
![Example image](images/lab13_3_table.jpg) <br>
&emsp; * Configure routing and remote access on BranchVPN1 and CorpVPN1 <br>
Complete this lab as follows: <br>
### Add the Network Policy and Access Services Role.
From Server Manager, select Manage > Add Roles and Features. <br>
Select Next to begin the Add Roles and Features Wizard. <br>
Select Next to use the Role-based or feature-based installation type. <br>
Select Next to use Select a server from a server pool and CorpNPS.CorpNet.local as the destination server. <br>
Select the Network Policy and Access Services role. <br>
Select Add Features to include management tools and then select Next. <br>
Select Next. <br>
Select Next. <br>
Select Next to use the Network Policy Server role service. <br>
Select Install. <br>
After the installation completes, select Close. <br>
### Configure clients on the RADIUS server.
From Server Manager, select Tools > Network Policy Server. <br>
Maximize the windows for better viewing. <br>
From the left pane, expand RADIUS Clients and Servers.
Right-click RADIUS Clients and then select New. <br>
Enter the Friendly name. <br>
Enter the Address (IP or DNS). <br>
At the bottom, in the Shared secret field, enter J51nj3T% as the shared secret. <br>
In the Confirm shared secret field, re-enter the shared secret. <br>
Select the Advanced tab. <br>
In the Vendor name field, make sure Radius Standard is selected. <br>
Select OK. <br>
Repeat 2d–2k for additional Radius clients. <br>
### Create a network policy and add a group.
From the left pane, expand Policies. <br>
Right-click Network Policies and select New. <br>
Enter Sales in the Policy name field. <br>
Using the Type of network access server drop-down list, select Remote Access Server (VPN-Dialup) and then select Next. <br>
Select Add to add group membership as a condition. <br>
Under Groups, select User Groups and then select Add. <br>
Select Add Groups. <br>
Enter Sales under Enter the object names to select. <br>
Select OK. <br>
Select OK. <br>
Select Next. <br>
Select Next to use the default of Access granted. <br>
Select Add. <br>
Select OK to use the default of Microsoft: Smart card or other certificate. <br>
Under Less secure authentication methods, unmark all the authentication methods and then select Next. <br>
Select Next, to use the default settings for the Configure Constraints dialog. <br>
Select Next, to use the default settings for the Configure Settings dialog. <br>
Select Finish. <br>
### Configure a RADIUS client.
From the top left, select Sites. <br>
Select the server to be configured as a RADIUS Client. <br>
From Server Manager, select Tools > Routing and Remote Access. <br>
Right-click the server and select Properties. <br>
Select the Security tab. <br>
Use the Authentication provider drop-down list to select RADIUS Authentication. <br>
Select Configure. <br>
Select Add. <br>
Enter CorpNPS in the Server name field. <br>
Next to Shared secret, select Change. <br>
In the New secret field, enter J51nj3T% as the secret. <br>
&emsp; This password must be identical to the one that was entered on the NPS server. <br>
In the Confirm new secret field, re-enter the shared secret; then select OK. <br>
Select OK to add the RADIUS server. <br>
Select OK to close the RADIUS Authentication dialog. <br>
Use the Accounting provider drop-down list to select RADIUS Accounting. <br>
Select Configure. <br>
Select Add. <br>
Enter CorpNPS in the Server name field. <br>
Next to Shared secret, select Change. <br>
In the New secret field, enter J51nj3T% as the secret. This password must be identical to the one that was entered on the NPS server. <br>
In the Confirm new secret field, re-enter the shared secret; then select OK to add the RADIUS server. <br>
Select OK to close the Add RADIUS Server dialog. <br>
Select OK to close the RADIUS Accounting dialog. <br>
Select OK to close server properties. <br>
Repeat step 4 to add the additional RADIUS Client. <br>
## Lab 13.4: Allow Remote Desktop Connections
Complete this lab as follows: <br>
### Configure Office1 to allow connections from Remote Desktop.
Right-click Start and select Settings. <br>
From the right pane, scroll down and select Remote Desktop. <br>
Under Remote Desktop, slide the button to the right. <br>
Select Confirm. <br>
### Add Tom Plask as a user who will be able to connect to Office1 using a Remote Desktop connection.
Select Remote Desktop users. <br>
Select Add. <br>
Enter Tom Plask. <br>
Select OK to add the user. <br>
Select OK to close the dialog. <br>
### Verify that the firewall ports for the Remote Desktop are opened appropriately.
On the left, select Privacy and Security. <br>
Select Windows Security. <br>
Select Firewall & network protection. <br>
Select Allow an app through firewall. <br>
Scroll down and verify that Remote Desktop is marked. <br>
From the upper right, select. <br>
## Lab 13.5: Use PowerShell Remote
Complete this lab as follows: <br>
### On Office2, enable PowerShell remoting.
Right-click Start and then select Terminal (Admin). <br>
Run Enable-PSRemoting from PowerShell. <br>
### On ITAdmin, start a PowerShell interactive session with Office2 and test Office2's connection to the ISP.
From the top navigation tabs, select Floor 1 Overview. <br>
Under IT Administration, select ITAdmin. <br>
Right-click Start and then select Terminal (Admin). <br>
From PowerShell, run Enter-PSSession Office2 <br>
Run tracert 198.28.2.254 <br>
Run Exit-PSSession <br>
### Answer the question.
## Live Lab 13.6: Configure a Jump Box
Live Lab. <br>