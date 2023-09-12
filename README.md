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

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/UF88LZx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To begin IIS needs to be enablled in windows with CGI and Common HTTP features. Open Control Panel. Then from there open PROGRAMS and TURN WINDOWS FEATURES ON OR OFF. Expand INTERNET INFORMATION SERVICES, expand WEB MANAGEMENT TOOLS, and enable IIS MANAGEMENT CONSOLE. Then Click to expand WORLD WIDE WEB SERVICES and APPLICATION DEVELOPMENT. In application development enable CGI and click ok to confirm.   
</p>
<br />

<p>
<img src="https://i.imgur.com/CApgVWQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/1mguFcJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then download and install PHP MANAGER for IIS (PHPManagerForIIS_V1.5.0.msi). Then download REWRITE MODULE (rewrite_amd64_en-US.msi). After installation, create a new folder called C:PHP on the Windows (C:) drive. This will be used to unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) zip folder from the installation files.   
</p>
<br />

<p>
<img src="https://i.imgur.com/2C9oPER.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then download and install VC_redist.x86.exe from the installation files. 
</p>
<br />

<p>
<img src="https://i.imgur.com/JMsGAR4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then download MYSQL5.5.62 (mysql-5.5.62-win32.msi) from the installation files. In the MYSQL setup wizard click "Typical Install". Then launch. Select Standard Configuration and INSTALL AS WINDOWS SERVICE. For credentials the username: root and Password: Password1 for this lab.   
</p>
<br />

<p>
<img src="https://i.imgur.com/S5H1kgS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before installing osTicket configurations need to be made within IIS. Open as an admin and select PHP Manager. Select Register new PHP version. Select Browse and select the PHP CGI executable file (php-cgi.exe) within the PHP folder. After registering the PHP version, reload the IIS server within the management console.
</p>
<br />

<p>
<img src="https://i.imgur.com/6rzfF7d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/Sk0lnOV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
Now we can install osTIcket v1.15.8. Extract and copy the "upload" to c:\inetpub\wwwroot. Within the c:\inetpub\wwwroot folder, rename "upload" to "osTicket". Then reload IIS.  
</p>
<br />

<p>
<img src="https://i.imgur.com/m2hLNh8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <p>
<img src="https://i.imgur.com/dxqNTWW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the IIS console browse to Sites -> Default -> osTicket. Click "Browse *.80" which will bring up the osTicket page. Then click on PHP Manager while in the osTicket menu in IIS. Click "Enable or Disable an extension." Enable the following extensions:  php_imap.dll, php_intl.dll, php_opcache.dll.
</p>
<br />

<p>
<img src="https://i.imgur.com/IMpGyZo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <p>
<img src="https://i.imgur.com/nHVn4T1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then a file needs to be renamed and permissions changed. In C:\inetpub\wwwroot\osTicket\include, rename ost-sampleconfig.php to ost-config.php. Then open its Properties and change the following permissions: Disable inheritance -> Remove All and New Permissions -> Everyone-> All. 
</p>
<br />

<p>
<img src="https://i.imgur.com/V1aBksa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/wnLvdNg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then from the installation files download and install HeidiSQL. Create a new session and enter the password used in the MYSQL. Then Right-click on Unnamed and create a new database named osTicket. 
</p>
<br />

<p>
<img src="https://i.imgur.com/Dm9B4Mi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/w9RHsip.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<p>
Within the osTicket browser enter the necessary details to set up osTicket. For the MySQL database, use the credentials used in MySQL and HeidiSQL. 
</p>
<br />

<p>
OsTicket should now be installed! But before finishing delete the setup folder found in C:\inetpub\wwwroot\osTicket. Then change the permissions of the ost-config.php file to "Read" only. 
</p>
<br />

<h2>osTicket is Installed!</h2>

OsTicket is now installed and ready to be used. I used osTicket to see how a ticketing system works and how to resolve tickets. I get to see how a part of IT Support works through ticketing systems and SLAs.
