# Module 6 (Labs 17 - 26) Implementing Network Services
## Lab 6.17: Troubleshoot IP Configuration 3
Complete this lab as follows: <br>
### roubleshooting
### From the Office1 computer, use the ping command to begin troubleshooting the problem by verifying the scope of the connectivity issues.
Right-click Office1, and select Launch Windows. <br>
Right-click Start and then select Terminal (Admin). <br>
From the Terminal prompt, run the following ping commands (press Enter after each command): <br>
&emsp; * ping 192.168.0.10 (CorpServer) <br>
&emsp; * ping 192.168.0.31 (ITAdmin) <br>
ping 198.28.2.254 (the internet service provider) <br>
&emsp; &emsp; Notice that all pings were unsuccessful. <br>
From the top left, select Network Modeler to return to the network diagram. <br>
From the ITAdmin computer, use the ping and ipconfig /all commands to continue determining the scope of the connectivity issues. <br>
Right-click ITAdmin, and select Launch Windows. <br>
Right-click Start and then select Terminal (Admin). <br>
From the Terminal prompt, run the following ping commands (press Enter after each command): <br>
&emsp; * ping 192.168.0.10 (CorpServer) <br>
&emsp; * ping 192.168.0.33 (Office2) <br>
&emsp; * ping 192.168.0.30 (Exec) <br>
&emsp; * ping 198.28.2.254 (the internet service provider) <br>
&emsp; &emsp; Notice that all the pings were successful. <br>
Type ipconfig /all and press Enter. <br>
From the top right, select Questions. <br>
Answer Questions 1-3. <br>
From the top left, select Network Modeler to return to the network diagram. <br>
From Office1, use the ipconfig /all command to analyze the differences between Office1 and ITAdmin IP information. <br>
Right-click Office1, and select Launch Windows. <br>
From the Terminal prompt, type ipconfig /all and then press Enter. <br>
Answer Questions 4-7. <br>
Minimize the Lab Questions dialog. <br>
### Fixing the Issue
From your troubleshooting steps, you found that Office1 was the only computer having connectivity issues. As you examined and compared Office1's IP settings, you found that it was using the wrong subnet mask and DNS server. Since DHCP was not being used (DHCP Enabled was set to NO), the IP information must have been manually entered using bad or outdated information. <br>
You will now rectify the issue by configuring the Office1 computer to obtain its IP information from the DHCP server. <br>
### From Office1, configure the network connection to request the IP address information from the DHCP server:
Right-click Start and then select Settings. <br>
Select Network & internet. <br>
Select Ethernet. <br>
Under IP assignment, select Edit. <br>
Under Edit IP settings, select Automatic (DHCP). <br>
Select Save. <br>
Close Settings. <br>
Verify that Office1 is now able to connect to the internet. <br>
From the Terminal prompt, type ipconfig /all. Verify the following settings: <br>
&emsp; * DHCP Enable: Yes <br>
&emsp; * Subnet mask: 255.255.255.0 <br>
&emsp; * DNS Servers: <br>
&emsp; &emsp; * 192.168.0.11 <br>
&emsp; &emsp; * 192.168.10.11 <br>
From the Terminal prompt, run the following ping commands (press Enter after each command): <br>
&emsp; * ping 192.168.0.10 (CorpServer) <br>
&emsp; * ping 192.168.0.31 (ITAdmin) <br>
&emsp; * ping 198.28.2.254 (the internet service provider) <br>
&emsp; &emsp; Notice that all pings are successful. <br>
## Lab 6.18: Configure DNS Addresses
While completing this lab, use the following DNS information: <br>
&emsp; * Preferred DNS server: 208.67.222.222 <br>
&emsp; * Alternate DNS server: 208.67.222.220 <br>
Complete this lab as follows: <br>
### Access the Ethernet properties dialog.
Under Dorm Room, select Dorm-PC. <br>
Right-click the Network icon in the taskbar's notification area and select Network and Internet settings. <br>
From the right pane, select Ethernet. <br>
Under DNS server assignment, select Edit. <br>
### Configure the new DNS addresses.
Under Edit DNS settings, select Manual. <br>
Select IPv4 to toggle it to On. <br>
Enter the Preferred DNS. <br>
Enter the Alternate DNS. <br>
Select Save. <br>
## Lab 6.19: Create Standard DNS Zones
Complete this lab as follows: <br>
### Access the CorpDC virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Double-click CorpDC to connect to the server. <br>
Maximize the window for better viewing. <br>
### Create a primary forward lookup zone.
From Server Manager, select Tools > DNS. <br>
Maximize the window for better viewing. <br>
Expand CORPDC (the server that will host the zone). <br>
Right-click Forward Lookup Zones and select New Zone. <br>
In the New Zone wizard, select Next. <br>
Make sure Primary zone is selected. <br>
Clear Store the zone in Active Directory (this option is only available for domain controllers) and then select Next. <br>
In the Zone name field, enter acct.CorpNet.local for the zone and then select Next. <br>
Verify that Create a new file with this file name is selected and then click Next. <br>
Make sure Do not allow dynamic updates is selected and then click Next. <br>
Select Finish to complete the New Zone wizard. <br>
### Configure zone transfers. <br>
Expand Forward Lookup Zones. <br>
Right-click acct.CorpNet.local (the new zone) and select Properties. <br>
Select the Zone Transfers tab. <br>
Verify that Allow zone transfers is selected. <br>
Select To any server. <br>
Select OK. <br>
### Create a forward secondary zone.
Expand CORPDC3 (the server that will host the new zone). <br>
Right-click Forward Lookup Zones and then select New Zone. <br>
Select Next. <br>
Select Secondary zone as the zone type and then select Next. <br>
In the Zone name field, enter acct.CorpNet.local and then select Next. <br>
In the Master Servers box, select Click here. <br>
Enter 192.168.0.11 or CorpDC.CorpNet.Local as the server that hosts a copy of the zone. <br>
Press Enter or click away from the IP address to begin validation. <br>
After validation is complete, select Next. <br>
Click Finish to complete the New Zone wizard. <br>
### Lab 6.20: Create Host Records
While completing this lab, use the following information: <br>
![Example image](images/lab6_20_table.jpg) <br>
Complete this lab as follows: <br>
### Access the CorpDC virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Double-click CorpDC to connect to the server. <br>
Maximize the window for better viewing. <br>
### Create a primary reverse lookup zone.
From Server Manager, select Tool > DNS. <br>
Expand CORPDC. <br>
Right-click Reverse Lookup Zones and select New Zone. <br>
Select Next. <br>
Make sure that Primary zone is selected. <br>
Make sure that Store the zone in Active Directory is selected and then select Next. <br>
Keep the default replication scope setting and select Next. <br>
Keep the default reverse lookup zone settings and select Next. <br>
For Network ID, use 192.168.0 as the network ID. <br>
Select Next. <br>
Keep the default dynamic update settings and then select Next. <br>
Select Finish. <br>
### Create a host (A) and associated pointer (PTR) record.
From DNS Manager, expand Forward Lookup Zones. <br>
Right-click CorpNet.local and select New Host (A or AAAA). <br>
In the Name field, enter the hostname. <br>
In the IP address field, enter the IP address. <br>
Select Create associated pointer (PTR) record as needed. The reverse lookup zone must exist for this record to be created. <br>
Select Add Hosts. <br>
Select OK for the prompt shown. <br>
Repeat steps 3c through 3g to add the additional host records. <br>
Select Done. <br>
## Lab 6.21: Create CNAME Records
Complete this lab as follows: <br>
### Access the CorpDC virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Double-click CorpDC to connect to the server. <br>
Maximize the window for better viewing. <br>
### For the sales.private zone, create the ALIAS (CNAME) record with a blank name pointing to CorpWeb.CorpNet.local.
From Server Manager, select Tools > DNS. <br>
Maximize the window for better viewing. <br>
Expand CORPDC > Forward Lookup Zones. <br>
Right-click the sales.private zone and select New Alias (CNAME). <br>
Configure the new record as follows: <br>
&emsp; * Alias name: Leave blank <br>
&emsp; * Fully qualified domain name (FQDN) for target host: CorpWeb.CorpNet.local <br>
Select OK. <br>
### For the sales.private zone, create the intranet ALIAS (CNAME) record pointed to CorpWeb.CorpNet.local.
Right-click the sales.private zone and select New Alias (CNAME). <br>
Configure the new record as follows: <br>
&emsp; * Alias name: intranet <br>
&emsp; * Fully qualified domain name (FQDN) for target host: CorpWeb.CorpNet.local <br>
Select OK. <br>
### For the sales.private zone, create the www ALIAS (CNAME) record pointed to CorpWeb.CorpNet.local.
Right-click the sales.private zone and select New Alias (CNAME). <br>
Configure the new record as follows: <br>
&emsp; * Alias name: www <br>
&emsp; * Fully qualified domain name (FQDN) for target host: CorpWeb.CorpNet.local <br>
Select OK. <br>
## Lab 6.22: Troubleshoot DNS Records
Complete this lab as follows: <br>
### Test the connectivity to CorpWeb using the ping command.
Right-click Start and select Windows PowerShell (Admin). <br>
At the prompt, type ping CorpWeb.CorpNet.local and press Enter. <br>
At the prompt, type ping 192.168.0.15 (the IP address for CorpWeb) and press Enter. <br>
From the top right, select Questions. <br>
Answer Question 1. <br>
Close PowerShell. <br>
### Access the CorpDC virtual server.
From Hyper-V Manager, select CORPSERVER. <br>
Double-click CorpDC to connect to the server. <br>
Maximize the window for better viewing. <br>
### Create any DNS records needed to fix the problem.
In Server Manager, select Tools > DNS. <br>
Expand CORPDC > Forward Lookup Zones. <br>
Right-click CorpNet.local and select New Host (A or AAAA). <br>
In the Name field, enter CorpWeb. <br>
&emsp; Notice that the fully qualified domain name (FQDN) is now CorpWeb.CorpNet.local. <br>
Enter 192.168.0.15 in the IP Address field. <br>
Select Create associated pointer (PTR) record to automatically create the PTR record for the new host. <br>
Select Add Host. <br>
Select OK. <br>
Select Done to close the New Host dialog. <br>
### Test the connectivity to CorpWeb using the ping command. <br>
Right-click Start and select Windows PowerShell (Admin). <br>
At the prompt, type ping CorpWeb.CorpNet.local and press Enter. <br>
At the prompt, type ping 192.168.0.15 (the IP address for CorpWeb) and press Enter. <br>
Answer Question 2. <br>
### Applied Live Lab 6.23: Configure DNS Records
Live lab <br>
### Lab 6.24: Explore nslookup
Complete this lab as follows: <br>
### Use nslookup to query the DNS for the CorpWeb server using its fully qualified domain name.
Right-click Start and select Windows PowerShell (Admin). <br>
At the PowerShell prompt, type nslookup CorpWeb.CorpNet.local and press Enter. <br>
&emsp; The CorpDC DNS server responds with the name resolution information for CorpWeb. <br>
### Use nslookup to query the CorpDC3 DNS server for CorpWeb. <br>
Type nslookup CorpWeb.CorpNet.local CorpDC3.CorpNet.local and press Enter.
&emsp; The CorpDC3 DNS server responds that it can't find CorpWeb. CorpDC3 does not have a DNS record for CorpWeb. <br>
### Consider the following questions:
&emsp; What is the Problem? <br>
&emsp; The information between the DNS databases is not consistent. Since this DNS zone is an Active Directory-integrated zone, this indicates that Active Directory is not synchronizing properly. <br>
 <br>
&emsp; How would you resolve this problem? <br>
&emsp; You would likely attempt to force replication between the Active Directory domain controllers. If CorpDC held a primary zone and CorpDC3 held a secondary zone, you would likely initiate a zone transfer to make sure that the DNS records were consistent between servers. <br>
 <br>
&emsp; How would you verify that the problem has been fixed? <br>
&emsp; After implementing the above solution, you could verify that the problem was fixed by repeating step 2. The CorpDC3 DNS server should respond with name resolution information for CorpWeb. <br>
## Lab 6.25: Use nslookup
Complete this lab as follows:
### Use nslookup to find the primary IP address for the corpnet.xyz domain.
From the Favorites bar, select Terminal.
At the prompt, type nslookup corpnet.xyz and press Enter.
From the top right, select Questions.
Answer Question 1.
### Use nslookup to find the mail server for corpnet.xyz and its IP address:
At the prompt, type nslookup -type=mx corpnet.xyz and press Enter.
At the prompt, type nslookup www3.corpnet.xyz and press Enter.
Answer Question 2.
### Use nslookup to confirm the corpnet.xyz mail server information by querying the external DNS server (ns1.nethost.net).
At the prompt, type nslookup -type=mx corpnet.xyz ns1.nethost.net and press Enter.
Answer Question 3.