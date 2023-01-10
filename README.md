<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- To configure Active Directory on Azure Virtual Machines, you will need to do the following:

<p>
    1.  Create a new virtual machine in Azure that will be used as the domain controller.
<p>
    2.  Connect to the virtual machine using Remote Desktop Protocol (RDP).
<p>
    3.  Once connected, open the "Server Manager" and click on the "Add roles and features" option.
<p>
    4.  Follow the prompts to add the "Active Directory Domain Services" role to the virtual machine.
<p>
    5.  After the role has been installed, click on the "Promote this server to a domain controller" option.
<p>
    6.  Follow the prompts to configure the active directory domain. You will need to specify the name of the domain and the forest functional level.
<p>
    7.  Once the active directory configuration is complete, you can create user accounts and groups, and join other virtual machines to the domain.

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/S9Yg4oy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the Azure Portal and search for Virtual Machines in the search bar
</p>
<br />

<p>
<img src="https://i.imgur.com/knC6eiM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Virtual Machine
</p>
<br />

<p>
<img src="https://i.imgur.com/XxuoyXb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a New Resource Group
<p>
 Name the Virtual Machine
<p>
 Select a Region closes to you
<p>
 Select Windows Server for the image
<p>
 For the Size make sure it has at least 2 CPUs or else the server will run slow
 
</p>
<br />

<p>
<img src="https://i.imgur.com/sqpuKaY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Create a user name and password. This will be use to RDP into the VM
<p>
 Check both boxes at the bottom
<p> 
 Review + Create
</p>
<br />

<p>
<img src="https://i.imgur.com/OP5kzWD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to the VM Portal and look for the VM-Domain-Controller that you just made
</p>
<br />

<p>
<img src="https://i.imgur.com/vTHfXCz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Locate the Public IP Address and copy
</p>
<br />

<p>
<img src="https://i.imgur.com/bcYggXD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Start -> RDP in windows to pull up Romote Desktop Connection
<p>
 Paste the Public IP Address from your VM  
</p>
<br />

<p>
<img src="https://i.imgur.com/RYyo8vy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enter the same credentials that you use to make the VM. May have to go to "More choices" to enter credentials
</p>
<br />

<p>
<img src="https://i.imgur.com/DHe1LaD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once RDP into the VM locate "Server Manager"
</p>
<br />

<p>
<img src="https://i.imgur.com/Ooqphwm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add Roles and Features
<p>
Click next till you get to "Server Roles"
<p>
Check "Active Directory Domain Services"
<p>
 Click next and install
</p>
<br />

<p>
<img src="https://i.imgur.com/bhuNWTo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Promote this server as a Domain Controller
</p>
<br />

<p>
<img src="https://i.imgur.com/Dc7PJeY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add a new forest
<p>
Add a domain name
</p>
<br />

<p>
<img src="https://i.imgur.com/gGSPyQm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create Password(This is only to restore lost data)
</p>
<br />

<p>
<img src="https://i.imgur.com/rfo3MVN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Wait for NetBIOS to assign domain name
<p>
After you install Active Directory, the Vm will resart 
</p>
<br />

<p>
<img src="https://i.imgur.com/UrWbuJK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
RDP into the VM
<p>
Now that the VM is a Domain Controller. your login should be like this. (DomainName)\(LocalUser) then the password you use to create the VM
</p>
<br />

<p>
<img src="https://i.imgur.com/soIr2OI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once in the VM open Active Directory through the Server Manager program. 
<p>
Tools -> Active Directory Users and Computers
</p>
<br />

<p>
<img src="https://i.imgur.com/DCC3oG8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
And there you go! Active Directory is finaly installed on the VM!
</p>
<br />

