# Module 12 (Labs 7 - 12): Configuring Wireless Networks
## Lab 12.7: Secure an Enterprise Wireless Network
### To complete this lab, use the following MAC addresses:
&emsp; * 00:18:DE:01:34:67 <br>
&emsp; * 00:18:DE:22:55:99 <br>
&emsp; * 00:02:2D:23:56:89 <br>
&emsp; * 00:02:2D:44:66:88 <br>
Complete this lab as follows:
### Log into the Ruckus Wireless ZoneDirector.
In the Google Chrome URL field, type 192.168.0.6 and press Enter. <br>
Log in using the following: <br>
&emsp; * Admin Name: admin <br>
&emsp; * Password: password <br>
Select Login. <br>
### Change the admin's username and password for the Ruckus Wireless ZoneDirector.
Select the Administer tab. <br>
Ensure Authenticate using the admin name and password is selected. <br>
In the Admin Name field, enter WxAdmin <br>
Enter password in the Current Password field. <br>
In the New Password field, enter ZDAdminsOnly!$ (Note: O is the capital letter O). <br>
Enter ZDAdminsOnly!$ in the Confirm New Password field. <br>
On the right of the section, select Apply. <br>
### Enable MAC address filtering.
From the top, select the Configure tab. <br>
From the left menu, select Access Control. <br>
Expand L2-L7 Access Control. <br>
Under L2/MAC address Access Control, select Create New. <br>
In the Name field, enter Allowed Devices. <br>
Under Restriction, make sure Only allow all stations listed below is selected. <br>
Enter a MAC address. <br>
Select Create New. <br>
Repeat steps 3g–3h for each of the remaining MAC addresses that need to be added to the ACL. <br>
Select OK. <br>
## Configure access controls.
Under Access Control, expand Device Access Policy. <br>
Select Create New. <br>
In the Name field, enter NoGames. <br>
Select Create New. <br>
Use the OS/Type drop-down menu to select Gaming. <br>
Use the Type drop-down menu to select Deny. <br>
Under Uplink, ensure Disabled is selected. <br>
Under Downlink, ensure Disabled is selected. <br>
Select Save. <br>
Select OK. <br>
## Lab 12.8: Secure a Home Wireless Network
Complete this lab as follows: <br>
### Access, and sign into, the TPLink-AC1750 wireless access point.
In the URL field of Google Chrome, enter 192.168.0.254 and press Enter. <br>
Maximize Google Chrome for easier viewing. <br>
From the top menu bar, select the Wireless tab. <br>
Enter the sign-in credentials: <br>
&emsp; * Username: admin <br>
&emsp; * Password: password <br>
Select Sign In. <br>
### Change the Wireless Network Name (SSID) to PoliceVan.
Make sure the Wireless submenu of Basic Settings is selected. <br>
Under Wireless Interface wlan0, change the Wireless Network Name (SSID) to PoliceVan. <br>
Scroll down and select Apply Settings. <br>
### Configure the wireless security settings. <br>
From the submenu bar, select the Wireless Security tab. <br>
For Wireless Mode, use the drop-down list to select WPA. <br>
Under Network Authentication, select WPA2 Personal. <br>
Under WPA Algorithms, select CCMP-128 AES. <br>
In the WPA Shared Key field, enter 4WatchingU. <br>
(Optional) Select Unmask to verify your new shared key. <br>
Scroll to the bottom and select Apply Settings. <br>
### Change the wireless access point's administration authentication credentials.
From the top menu bar, select the Administration tab. <br>
Make sure the Management submenu is selected. <br>
Change the Router Password settings as follows: <br>
&emsp; * Router Username: @dm1n (1 is the number 1) <br>
&emsp; * Router Password: StayOut! (O is the capital letter O). <br>
&emsp; * Re-enter to confirm: StayOut! (O is the capital letter O). <br>
Scroll to the bottom and select Apply Settings. <br>
Select Save. <br>
Select Reboot Router. <br>
When prompted, select Continue. <br>
### Configure the laptop to connect to the wireless network and save the wireless profile settings.
From the top left, select Computer Desk. <br>
On the Home-Laptop monitor, select Click to view Windows 11. <br>
From the Notification area of the taskbar, select the Network icon. <br>
To the right of the wireless icon, select the > icon. <br>
Select the PoliceVan wireless network. <br>
Make sure Connect automatically is selected. <br>
Select Connect. <br>
Enter 4WatchingU (the passphrase/network security key). <br>
Select Next. <br>
From the Notification area of the taskbar, right-click the network icon and select Network & Internet settings to confirm the connection. <br>
## Lab 12.9: Enable Wireless Intrusion Prevention
Complete this lab as follows: <br>
### Configure the wireless controller to protect against denial-of-service (DOS) attacks.
Click on the Start button, then select Google Chrome. <br>
Enter the address of 192.168.0.6 and press Enter. <br>
Maximize the Google Chrome browser for better viewing. <br>
From the Ruckus controller, select the Configure tab. <br>
From the left menu, select WIPS. <br>
From the right pane, select: <br>
&emsp; * Protect my wireless network against excessive wireless requests. <br>
&emsp; * Temporarily block wireless clients with repeated authentication failures. <br>
Enter a threshold of 120 seconds. <br>
On the right, for this area, select Apply. <br>
### Configure intrusion detection and prevention.
Select Enable report rogue devices. <br>
Select Report all rogue devices. <br>
Select Protect the network from malicious rogue access points. <br>
On the right, for this area, select Apply. <br>
### Select Enable rogue DHCP server detection and then select Apply.
## Lab 12.10: Explore Wireless Network Problems
Complete this lab as follows: <br>
### Identify the wireless connections on the Office2-Lap.
Under Office 2, select Office2-Lap. <br>
In the notification area, select the wireless network icon, then click the right arrow next to the wireless icon to see the available wireless networks. <br>
Which wireless networks are available to Office2-Lap? Which wireless network is Office2-Lap connected to? <br>
Available networks are: CorpNet, StarSky, and NetGearWireless. <br>
### Forget the HomeWireless network on Office2-Lap.
Right-click Start and then select Settings. <br>
Select Network & Internet. <br>
Select Wi-Fi. <br>
Select Manage known networks. <br>
Which known networks are displayed? CorpNet and HomeWireless. <br>
Select Forget next to HomeWireless. <br>
Close the Settings app. <br>
### View the wireless controller's configuration interface using Google Chrome.
Click on Start, then select Google Chrome. <br>
In the URL field, enter 192.168.0.6 and then press Enter. <br>
Maximize the window for better viewing. <br>
In the Admin Name field, enter admin. <br>
In the Password field, enter password. <br>
Select Login. <br>
Select the Configure tab. <br>
From the left menu, select WLANs. <br>
Under WLANs, select Edit located in the table under Actions. <br>
From the top right, select Questions. <br>
Answer Questions 1 and 2. <br>
Minimize the Lab Questions dialog. <br>
### Identify the wireless connections on Gst-Lap.
From the top left, select Floor 1 Overview. <br>
Under Lobby, select Gst-Lap to switch to laptop located in the lobby. <br>
From the top right, select Questions. <br>
Move the question dialog to the left. <br>
In the notification area, select the globe icon, then the arrow next to the wireless icon. <br>
Answer Question 3. <br>
Minimize the Lab Questions dialog. <br>
Right-click Start and then select Settings. <br>
Select Network & Internet. <br>
Select Wi-Fi. <br>
Select Manage known networks. <br>
Which known networks are displayed? CorpNet. <br>
In the notification area, select the globe icon, then the arrow next to the wireless icon. <br>
Select the CorpNet wireless network name. <br>
Select Connect automatically and then click Connect. <br>
&emsp; Why did Gst-Lap connect without you entering the network security key? It's already a managed/known network. <br>
### Identify the wireless connections on Exec-Laptop.
From the top left, select Floor 1 Overview. <br>
Under Executive Office, select Exec-Laptop. <br>
In the notification area, select the globe icon. Notice that the wireless icon is not blue, meaning WiFi is not turned on. <br>
What wireless networks are available to Exec-Laptop? None. <br>
From the top left, select Executive Office to switch to the hardware of the devices in the executive office. <br>
Examine the position of the wireless switch found in the lower left of the laptop's case. <br>
What is the position of this switch? Off. <br>
Slide the wireless switch to the On position to turn the wireless network interface card on. <br>
On the Exec-Laptop monitor, select Click to view Windows 11 to switch to the operating system. <br>
Select the globe icon in the notification area, then the arrow next to the wireless icon to view the available networks. <br>
Which wireless networks are available to Exec-Laptop now? <br>
Manually connect to the CorpNet wireless network as follows: <br>
&emsp; * Select the CorpNet wireless network name. <br>
&emsp; * Select Connect. <br>
## Lab 12.11: Troubleshoot Wireless Network Problems
Complete this lab as follows: <br>
### Check to see if the ITAdmin computer can connect to the wireless network.
Under IT Administration, select ITAdmin. <br>
In the Notification Area, select the globe icon, then the arrow next to the wireless icon to view the available networks. <br>
Select the CorpNet wireless network. <br>
Select Connect. <br>
The ITAdmin computer is now connected to the CorpNet wireless network. Because this computer can connect to the wireless network, the problem may be limited to only the Exec-Laptop laptop in the Executive Office. <br>
### Troubleshoot and fix the wireless networking on Exec-Laptop.
From the top left, select Floor 1 Overview to switch to Exec-Laptop. <br>
Under Executive Office, select Exec-Laptop. <br>
In the Notification Area, select the globe icon. Note that the Wi-Fi icon is not blue, meaning it is turned off. Possible causes for this include: <br>
&emsp; * The wireless network interface card is not turned on (the wireless switch on the exterior of the laptop is in the OFF position). Since no wireless networks are shown in the list, you must take additional steps. <br>
&emsp; * The wireless network's SSID is not broadcasting. However, from Step 1, you know that the wireless access point is broadcasting the SSID. <br>
&emsp; * The wireless access point is not powered on. However, from Step 1, you know that the wireless access point is powered on.
From the top left, select Executive Office to switch to the devices found in the executive office. <br>
On the front of the Exec-Laptop, check to see if the switch for the wireless network interface card is in the On position. <br>
Notice that it is in the OFF position instead. <br>
Slide the wireless switch to the On position to turn the wireless network interface card on. <br>
On the laptop monitor, select Click to view Windows 11. <br>
In the Notification Area, select the wireless network icon to view the available networks, then the arrow next to the wireless icon to view the available networks. <br>
The CorpNet wireless network is now displayed in the list of available networks. <br>
Select the CorpNet wireless network. <br>
Select Connect. <br>
&emsp; Since the laptop has previously been connected to the CorpNet wireless network, it connects without needing to re-enter the security key. <br>
## Lab 12.12: Optimize a Wireless Network
Configure your wireless access points as follows: <br>
### Configure Self Healing on the wireless network.
From the Ruckus ZoneDirector, select the Configure tab. <br>
From the left menu, select Services. <br>
Under Self Healing, select Automatically adjust AP radio power to optimize coverage when interference is present. <br>
Use the Automatically adjust 2.4GHz channels using drop-down arrow to select Background Scanning. <br>
Use the Automatically adjust 5GHz channels using drop-down arrow to select Background Scanning. <br>
On the right, select Apply (in the Self Healing pane). <br>
### Configure Background Scanning.
&emsp; * Under Background Scanning, select Run a background scan on 2.4GHz radio. <br>
&emsp; * Enter 30 seconds. <br>
&emsp; * Select Run a background scan on 5GHz radio. <br>
&emsp; * Enter 30 seconds. <br>
&emsp; * On the right, select Apply. <br>
### Configure Load Balancing.
&emsp; * Under Load Balancing, select Run load balancing on 2.4GHz radio. <br>
&emsp; * In the Adjacent radio threshold(dB) field, enter 40. <br>
&emsp; * Select Run load balancing on 5GHz radio. <br>
&emsp; * In the Adjacent radio threshold(dB) field, enter 40. <br>
&emsp; * On the right, select Apply. <br>
### Configure Band Balancing.
Under Band Balancing, select Percent of clients on 2.4GHz radio. <br>
Enter 30.
On the right, select Apply. <br>
### Adjust the AP Power Level.
From the left menu, select Access Points. <br>
From the top right, select Exhibit to determine which access points to adjust; then close the exhibit. <br>
Under Access Points, select Edit next to the access point to be modified. <br>
Under Radio B/G/N(2.4G) next to TX Power, make sure Override Group Config is selected. <br>
From the TX Power drop-down list, select -3dB (1/2). <br>
Under Radio A/N/AC(5G) next to TX Power, make sure Override Group Config is selected. <br>
From the TX Power drop-down list, select -3dB (1/2). <br>
Select OK. <br>
Repeat steps 5b - 5h for additional access points. <br>