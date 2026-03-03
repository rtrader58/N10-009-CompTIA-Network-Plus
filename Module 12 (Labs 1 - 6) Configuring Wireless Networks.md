# Module 12 (Labs 1 - 6): Configuring Wireless Networks
## Lab 12.1: Configure Wireless Profiles
Complete this lab as follows: <br>
### Manually create the wireless network profile on the laptop.
Right-click Start and then select Settings. <br>
Select Network & Internet. <br>
Select Wi-Fi. <br>
Select Manage known networks. <br>
Select Add Network. <br>
In the Network name field, enter PoliceVan. <br>
Use the Security type drop-down menu to select WPA2-Personal AES. <br>
In the Security Key field, enter 4WatchingU. <br>
Select Connect automatically. <br>
Select Connect even if the network is not broadcasting and then click Save. <br>
### Delete the out-of-date profile.
From Manage known networks, next to the TrendNet-BGN profile select Forget. <br>
## Lab 12.2: Design an Indoor Wireless Network
Only three WAPs are required to complete this lab (one omnidirectional WAP and two directional WAPs). <br>
The following WAP configuration provides adequate coverage and reduces signal emanation. <br>
![Example image](images/lab12_2Image.jpg) <br>
Complete this lab as follows: <br>
### Under Shelf, expand Wireless Access Points.
&emsp; * Drag the Wireless Access Point (Indoor, omnidirectional Antenna) to the installation area in the Lobby. <br>
&emsp; * Drag one Wireless Access Point (Indoor, directional Antenna) to the installation area on the west wall of the IT Administration office. <br>
&emsp; * Drag another Wireless Access Point (Indoor, directional Antenna) to the installation area on the east wall of the Networking Closet. <br>
## Lab 12.3: Design an Outdoor Wireless Network
Complete this lab as follows: <br>
### Install the High-gain Antenna (Directional) on buildings A and B.
Under Shelf, expand High-gain Antennas. <br>
Drag the High-gain Antenna (Directional) to the installation area on the roof of Building A. <br>
Drag the remaining High-gain Antenna (Directional) to the installation area on the roof of Building B. <br>
### Install the wireless access point for buildings A and B.
Under Shelf, expand Wireless Access Points. <br>
Drag a Wireless Access Point (Outdoor) to the installation area on the roof of Building A. <br>
Drag the remaining Wireless Access Point (Outdoor) to the installation area on the roof of Building B. <br>
### Install the antennas.
Under Shelf, expand WAP Antennas. <br>
Drag the WAP Antenna (Directional) to one of the installed outdoor WAPs. <br>
Drag the remaining WAP Antenna (Directional) to the other installed outdoor WAP. <br>
## Lab 12.4: Implement an Enterprise Wireless Network
Complete this lab as follows: <br>
### Access the Ruckus zone controller.
From the taskbar, select Google Chrome. <br>
In the URL field, enter 192.168.0.6 and press Enter. <br>
Maximize the window for better viewing. <br>
### Log into the Wireless Controller console.
In the Admin field, enter admin (case-sensitive). <br>
In the Password field, enter password as the password. <br>
Select Login. <br>
### Create a new WLAN. <br>
Select the Configure tab. <br>
From the left menu, select WLANs. <br>
From the right, under WLANs, select Create New. <br>
In the New Name field, enter CorpNet Wireless. <br>
In the ESSID field, enter CorpNet. <br>
Under Type, make sure Standard Usage is selected. <br>
Under Authentication Options, make sure Open is selected. <br>
Under Encryption Options, select WPA2. <br>
For Algorithm, make sure AES is selected. <br>
In the Passphrase field, enter @CorpNetWeRSecure!. <br>
Select OK. <br>
### Switch to the Exec-Laptop.
From the top left, select Floor 1. <br>
Under Executive Office, select Exec-Laptop. <br>
### Connect to the new CorpNet wireless network.
In the notification area, select the globe icon, then the arrow next to the wireless icon to view the available networks. <br>
Select CorpNet. <br>
Make sure Connect automatically is selected. <br>
Select Connect. <br>
Enter @CorpNetWeRSecure! for the security key. <br>
Select Next. <br>
## Lab 12.5: Configure a Captive Portal
Complete this lab as follows: <br>
### Sign in to the pfSense management console.
In the Username field, enter admin. <br>
In the Password field, enter P@ssw0rd (zero). <br>
Select SIGN IN or press Enter. <br>
### Add a Captive Portal zone. <br>
From the pfSense menu bar, select Services > Captive Portal. <br>
Select Add. <br>
For Zone name, enter Guest_WiFi. <br>
For Zone description, enter Zone used for the guest Wi-Fi. <br>
Select Save & Continue. <br>
### Enable and configure the Captive Portal. <br>
Under Captive Portal Configuration, select Enable. <br>
For Interfaces, select GuestWi-Fi. <br>
For Maximum concurrent connections, select 100. <br>
For Idle timeout, enter 30. <br>
For Hard timeout, enter 120. <br>
Scroll down and select Per-user bandwidth restriction. <br>
For Default download (Kbit/s), enter 8000. <br>
For Default upload (Kbit/s), enter 2500. <br>
Under Authentication, use the drop-down menu to select None, don't authenticate users. <br>
Scroll to the bottom and select Save. <br>
### Allow a MAC address to pass through the portal. <br>
From the Captive Portal page, select the Edit Zone icon (pencil). <br>
Under the Services breadcrumb, select MACs. <br>
Select Add. <br>
Make sure the Action field is set to Pass. <br>
For Mac Address, enter 00:00:1B:12:34:56. <br>
Select Save. <br>
### Allow an IP address to pass through the portal.
Under the Servic <br>es breadcrumb, select Allowed IP Addresses. <br>
Select Add. <br>
For IP Address, enter 198.28.1.100. <br>
Use the IP address drop-down menu to select 16. This sets the subnet mask to 255.255.0.0. <br>
For the Description field, enter Admin's Laptop. <br>
Make sure Direction is set to Both. <br>
Select Save. <br>
## Lab 12.6: Create a Guest Network for BYOD
Complete this lab as follows: <br>
### Open the Ruckus ZoneDirector.
In the Google Chrome URL field, enter 192.168.0.6 and press Enter. <br>
Maximize Google Chrome. <br>
Log in using the following information: <br>
&emsp; * Admin Name: WirelessAdmin (case sensitive). <br>
&emsp; * Password: Adminsonly! (case sensitive). <br>
Select Login. <br>
### Set up Guest Access Services. <br>
Select the Configure tab. <br>
From the left menu, select Guest Access. <br>
Under Guest Access Service, select Create New. <br>
In the Name field, use Guest_BYOD. <br>
For Authentication, make sure Use guest pass authentication is selected. <br>
For Terms of Use, select Show terms of use. <br>
For Redirection, make sure Redirect to the URL that the user intends to visit is selected. <br>
Expand Restricted Subnet Access. <br>
Verify that 192.168.0.0/16 is listed. <br>
Select OK. <br>
### Create a guest WLAN.
From the left menu, select WLANs. <br>
Under WLANs, select Create New. <br>
In the Name field, use Guest. <br>
In the ESSID field, use Guest_BYOD. <br>
For Type, select Guest Access. <br>
Confirm the following settings are set: <br>
&emsp; * Authentication Options: Open <br>
&emsp; * Encryption Options: None <br>
&emsp; * Guest Access Service: Guest_BYOD <br>
For Wireless Client Isolation, select Isolate wireless client traffic from other clients on the same AP. <br>
Select OK. <br>
Close the Google Chrome browser. <br>
### Request a guest password.
Open a new Google Chrome browser window. <br>
Maximize the window for better viewing. <br>
In the URL field, enter 192.168.0.6/guestpass and press Enter. <br>
Log in using the following information: <br>
&emsp; * Admin Name: BYODAdmin (case sensitive). <br>
&emsp; * Password: @dmin1s (case sensitive). <br>
Select Log In. <br>
In the Full Name field, enter any full name. <br>
In the Key field, highlight the key and press Ctrl + C to copy the key. <br>
Select Next. <br>
### Access the wireless Guest Access service from the guest laptop in the lobby.
From the top left, select Floor 1. <br>
Under Lobby, select Gst-Lap. <br>
In the Notification area, select the wireless network icon. <br>
Select Guest_BYOD. <br>
Select Connect. <br>
Select Yes to allow the device to be discoverable. <br>
After checking network requirements, the browser opens to the Guest Access login page. <br>
In the Guest Pass field, press Ctrl + V to paste the key copied from the Key field. <br>
Select Log In. <br>

