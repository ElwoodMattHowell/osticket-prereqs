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


<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-configure-iis.png" height="80%" width="80%" alt="install / configure iis"/>


Our first step is to enable Internet Information Services(IIS) with Common Gateway Interface(CGI).  IIS is a general-purpose web server that runs on Windows.  The CGI element configures default settings for CGI applications on IIS.  To enable, first open the Control Panel and click on _Programs_.  Under _Programs and Features_ click _Turn Windows features on or off_.  Scroll down until you find _Internet Information Services_.  Check the box and then expand IIS by clicking the '+' sign to the left of the box.  Inside IIS, scroll to _World Wide Web Services_, and expand that.  Finally, expand _Application Development Features_, scroll to _CGI_, check the box next to CGI, and click _Okay_.  Once it has finished loading, Internet Information Services and Common Gateway Interface will be enabled.  If you open a web browser and type 127.0.0.1 in the browser, you should now see the home page for Internet Information Services.

<br />

<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/install-php-manager.png" height="40%" width="40%" alt="Install PHP manager">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/install-rewrite-module.png" height="40%" width="40%" alt="Install rewrite module">
</p>


Download the appropriate version of _PHP Manager_ from https://github.com/phpmanager/phpmanager/releases and install.  Next, download the _Rewrite Module_ from https://www.iis.net/downloads/microsoft/url-rewrite and install.  _PHP Manager_ allows you to install, run, and manage PHP versions on a Windows server running the IIS webserver.  The _ISS URL Rewrite Module_ is a tool used to convert complex web addresses into consistent, memorable, URL's. 
<br />

<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-php.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


Next we will install _PHP_.  First navigate to the root of the C drive and create a PHP folder.  Next, go to https://windows.php.net/download#php-8.2.  Download and install the appropriate zip file.  For Windows that will most likely be _VS16 x64 Thread Safe_.  Once the zip file is downloaded, extract the file to the PHP folder you just created.  _PHP_ is a server side scripting language that osTicket uses to serve up the web pages that provide the user interface. 
<br />

<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-mysql.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>


The next step will involve downloading and installing Microsoft Visual C++ Resdistributable(vc_redist) and MySQL.  We can quickly install vc_redist by clicking on this link and installing the file https://aka.ms/vs/17/release/vc_redist.x86.exe.  The Visual C++ Redistributable installs Microsoft C and C++ (MSVC) runtime libraries. These libraries are required by many applications built by using Microsoft C and C++ tools.  Now we need to download and install MySQL.  OsTicket will use MySQL in conjunction with HeidiSQL to create and access a database.  Navigate to https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view and download MySQL.  Once MySQL is finished downloading, open the file and follow the prompts for _Typical Installation_ and click _Finish_.  We will now be promted to configure MySQL.  Proceed with the standard configuration.  Enter your choice of a password and make note, you will need it later.  Once you have entered the password click _Execute_.
<br />
