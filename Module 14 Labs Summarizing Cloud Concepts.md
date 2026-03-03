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
&emsp; To view the iSCSI virtual disk and target you just created, expand the Server Manager window. <br> <br>
# Work still in progress