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

- Enable Internet Information Services(IIS) with Common Gateway Interface(CGI)
- Install PHP Manager for IIS
- Install Rewrite Module
- Install PHP 
- Install VC_redist.x86.exe
- Install MySQL
- Register PHP within IIS
- Install osTicket
- Install HeidiSQL

<h2>Installation Steps</h2>


<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-configure-iis.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Our first step is to enable Internet Information Services(IIS) with Common Gateway Interface(CGI).  IIS is a general-purpose web server that runs on Windows.  The CGI element configures default settings for CGI applications on IIS.  To enable, first open the Control Panel and click on _Programs_.  Under _Programs and Features_ click _Turn Windows features on or off_.  Scroll down until you find _Internet Information Services_.  Check the box and then expand IIS by clicking the '+' sign to the left of the box.  Inside IIS, scroll to _World Wide Web Services_, and expand that.  Finally, expand _Application Development Features_, scroll to _CGI_, check the box next to CGI, and click _Okay_.  Once it has finished loading, Internet Information Services and Common Gateway Interface will be enabled.  If you open a web browser and type 127.0.0.1 in the browser, you should now see the home page for Internet Information Services.

<br />

<p>
<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-rewrite-module.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
Download the appropriate version of _PHP Manager_ from https://github.com/phpmanager/phpmanager/releases and install.  Next, download the _Rewrite Module_ from https://www.iis.net/downloads/microsoft/url-rewrite and install.  _PHP Manager_ allows you to install, run, and manage PHP versions on a Windows server running the IIS webserver.  
<br />

<p>
<img src="https://github.com/ElwoodMattHowell/images/blob/main/images_icons" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
