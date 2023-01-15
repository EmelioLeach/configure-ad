<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>
To begin this demonstration we will create a two virtual machines, one will be the Domain Controller vm and the other will be the Client vm. Also we must set the NIC'S private ip address to be static.
<p>
<img src=https://i.imgur.com/AOesk7z.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/opIIYYm.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The next step we are going login to DC-1 and enable ICMPv4 on the windows firewall, so that we can see if we can ping Clinet-1 to DC-1 with ping -t meaning it won't stop pinging until we stop it. Also we will need DC-1 private ip address to ping.
</p>
<br />

<p>
<img src=https://i.imgur.com/VIiSJLD.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/H8vXv4k.png height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
Now we can log back into DC-1 and install Active directory domain services and promote as a dc. When we setup a new forest it should mydomain.com but it can be anything you want, so that when you the system restarts you should be able to login to DC-1 as mydomain.com\labuser.
</p>
<br />

<p>
<img src=https://i.imgur.com/3sdn88y.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now if we loginned successfully with mydomain.com\user we will open active directory users and computers from the tools menu and then right click on mydomain.com so we can create two organizational unit (folders) with one being _ADMINS and _EMPOLYEES. If we right click on the empty admins window we should be able to create a new user which we would name jane doe. Finallly we can make jane a admin by right clicking her name and opening properties to see what she is a memeber of, add domain and check the list and add Domain Admin to jane's groups.
</p>
<br />

<p>
<img src=https://i.imgur.com/IoneYOL.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/C1FVCpZ.png height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src=https://i.imgur.com/3sdn88y.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
