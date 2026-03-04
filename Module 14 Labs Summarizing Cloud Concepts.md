# Module 14 Labs: Summarizing Cloud Concepts
## Lab 14.1: Configure an iSCSI Target
Complete this lab as follows: <br>
### Access the New iSCSI Virtual Disk Wizard.
From the left pane of Server Manager, select File and Storage Services. <br>
Select iSCSI. <br>
In the iSCSI VIRTUAL DISKS panel, use the TASK drop-down to select New iSCSI Virtual Disk. <br>
### Under Select by volume, select D: and then select Next.
Under Server, make sure CorpiSCSI is selected. <br>
Under Select by volume, select D: and then select Next. <br>
In the Name field, enter iSCSIDisk1 for the virtual disk and then select Next. <br>
In the Size field, enter 5 for the virtual disk size and then use its drop-down to select TB. <br>
Make sure Dynamically expanding is selected and then select Next. <br>
Make sure New iSCSI target is selected and then select Next. <br>
In the Name field, enter iSCSITarget1 for the iSCSI target and then select Next. <br>
### Specify the iSCSI initiator that will access your iSCSI virtual disk.
Select Add. <br>
Make sure Query initiator computer for ID is selected. <br>
For the above option, select Browse to locate the server that will be allowed to access the iSCSI disk. <br>
In the Enter the object names to select field, enter the server name and then click OK. <br>
Select OK. <br>
Select Next. <br>
### Complete the creation of the virtual disk using the default options.
Select Next. <br>
Select Create. <br>
Select Close. <br>
&emsp; To view the iSCSI virtual disk and target you just created, expand the Server Manager window. <br>
## Lab: Configure an iSCSI Initiator
Complete this lab as follows: <br>
### Access the CorpFiles16 server.
From Hyper-V Manager, select CORPSERVER. <br>
Maximize the window to view all virtual machines. <br>
Double-click CorpFiles16 to connect to the computer. <br>
### Using the iSCSI Initiator, discover and log on to the target server.
From Server Manager on CorpFiles16, select Tools > iSCSI Initiator. <br>
In the Target field, enter CorpiSCSI as the target server. <br>
Select Quick Connect and verify that a target was added to the Discovered targets pane. <br>
Select Done. <br>
Select OK to close the iSCSI Initiator Properties window. <br>
### Bring the iSCSI disk online.
From the left pane of Server Manager, select File and Storage Services. <br>
Select Disks. <br>
Maximize the Server Manager window for better viewing. <br>
In the DISKS panel, find the Bus Type column and select the iSCSI disk. <br>
Right-click the iSCSI disk and select Bring Online. <br>
Select Yes to confirm <br>.
### Create a new volume for the iSCSI disk.
Right-click the iSCSI disk and select New Volume. <br>
Click Next to begin the New Volume Wizard. <br>
Under Disk, select Disk 3 and then select Next. <br>
Make sure the Volume size is using the maximum capacity available and then select Next. <br>
Change Drive letter to G and then select Next. <br>
Make sure NTFS is selected as the file system. <br>
For the Volume label field, use iSCSI as the name of the volume and then select Next.
Select Create. <br>
After the volume is created, select Close. <br>
## Live Lab 14.3: Deploy a Cloud VM
Live Lab <br>
## Live Lab 14.4: Configure Cloud Networking
Live Lab <br>
