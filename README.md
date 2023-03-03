# OsTicket
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Resource Group
- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs
- When creating the VM, allow it to create a new Virtual Network (Vnet)
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/8L09Ntt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Resource Group
</p>
<br />

<p>
<img src="https://i.imgur.com/BU9mho5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Create an Azure Virtual Machine Windows 10, 4 vCPUs
 <br />Name: Vm-osticket
 <br />Username: labuser (for example/whatever you chose)
 <br />Password: osTicketPassword1! (for example/whatever you chose)
</p>

<br />

<br />

<p>
<img src="https://i.imgur.com/GpV24nO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When creating the VM, allow it to create a new Virtual Network (Vnet)
</p>
<br />



<p>
<img src="https://i.imgur.com/nGyeBOL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Open this: Installation Files
We will use these files to install osTicket and some of the dependencies. I’m using this offline version to make sure everyone is using the same version of all the files :)
<br />  
Install / Enable IIS in Windows WITH CGI <br />
World Wide Web Services -> Application Development Features -> [X] CGI <br />
From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)<br />
From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)<br />

</p>
<br />


<p>
<img src="https://i.imgur.com/7LPvC7h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <br />
From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
<br />
From the Installation Files, download and install VC_redist.x86.exe.
<br />
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1

</p>

<br />

<p>
<img src="https://i.imgur.com/Yppzs6A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>

Open IIS as an Admin
  <br />
  
Register PHP from within IIS
<br />
Reload IIS (Open IIS, Stop and Start the server)
<br />
Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

</p>

<br />

<p>
<img src="https://i.imgur.com/MZbqLqM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload IIS (Open IIS, Stop and Start the server) <br />

Go to sites -> Default -> osTicket <br />
On the right, click “Browse *:80”

Note that some extensions are not enabled <br />
Go back to IIS, sites -> Default -> osTicket <br />
Double-click PHP Manager <br />
Click “Enable or disable an extension” <br />
Enable: php_imap.dll <br />
Enable: php_intl.dll <br />
Enable: php_opcache.dll <br />
Refresh the osTicket site in your browse, observe the changes <br />

</p>

<br />

<p>
<img src="https://i.imgur.com/OWSJ3mh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign Permissions: ost-config.php <br />
Disable inheritance -> Remove All<br />
New Permissions -> Everyone -> All<br />

Continue Setting up osTicket in the browser (click Continue) <br />
Name Helpdesk 
Default email (receives email from customers) <br />

From the Installation Files, download and install HeidiSQL. <br />
Open Heidi SQL <br /> 
  Create a new session, root/Password1 <br />
Connect to the session <br />
Create a database called “osTicket” <br />
  
  Continue Setting up osticket in the browser <br />
MySQL Database: osTicket <br />
MySQL Username: root <br />
MySQL Password: Password1 <br />
Click “Install Now!” <br />


</p>

<br />

<p>
<img src="https://i.imgur.com/K7xFTHb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>

