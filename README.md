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
Now if we loginned successfully with mydomain.com\user we will open active directory users and computers from the tools menu and then right click on mydomain.com so we can create two organizational unit (folders) with one being _ADMINS and _EMPOLYEES. If we right click on the empty admins window we should be able to create a new user which we would name jane doe. We can make jane a admin by right clicking her name and opening properties to see what she is a memeber of, add domain and check the list and add Domain Admin to jane's groups. Finally we should be able too log out admin and login as mydomain.com\jane_admin successfully.
</p>
<br />

<p>
<img src=https://i.imgur.com/IoneYOL.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/C1FVCpZ.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/pmIHnZq.png height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<p>
Now once we are on mydomain.com\jane_admin we can right click the windows icon and pull up the system tab where we should be able to rename this pc (advanced) so that we can change the domain but you will most likely get an error since there isn't a DC. We must set the dns by using the private ip address (10.0.0.4) from Dc-1 to Client-1. Refresh Client-1 in the azure VM section and login back as a labuser on remote desktop and repeat the beginning steps from right clicking the windows icon and pulling up the system tab to rename this pc (advance) and you should have a success message pop up instead of an error message this time. 
</p>
<br />

<p>
<img src=https://i.imgur.com/uFhJLBU.png height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<img src=https://i.imgur.com/h3VN1EM.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/4XWocgm.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will now setup remote desktop for non-admin users on client-1 by opening system properties and clicking remote desktop and allowing domain users to have access to remote desktop.
</p>
<br />

<p>
<img src=https://i.imgur.com/UOTr2NO.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally we will create a bunch of additional users and attempt to login to client-1 with a user. First we must login to Dc-1 as jane_admin so that we can open powershell_ise as an admin, create a new file and paste the contents of the script into it. we should be able to run the script and observe the accounts being created and then we can pick any user name and login.
</p>
<br />

<p>
<img src=https://i.imgur.com/kA0cXpV.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/bP3CqRs.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=https://i.imgur.com/rhl9qIW.png height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>

