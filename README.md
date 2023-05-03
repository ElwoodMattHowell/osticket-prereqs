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



<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/install-configure-iis.png" height="40%" width="40%" alt="install/enable iis"/>
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/iis-homepage.png" height="40%" width="40%" alt="IIS homepage">
</p>

Our first step is to enable Internet Information Services(IIS) with Common Gateway Interface(CGI).  IIS is a general-purpose web server that runs on Windows.  The CGI element configures default settings for CGI applications on IIS.  To enable, first open the Control Panel and click on _Programs_.  Under _Programs and Features_ click _Turn Windows features on or off_.  Scroll down until you find _Internet Information Services_.  Check the box and then expand IIS by clicking the '+' sign to the left of the box.  Inside IIS, scroll to _World Wide Web Services_, and expand that.  Finally, expand _Application Development Features_, scroll to _CGI_, check the box next to CGI, and click _Okay_.  Once it has finished loading, Internet Information Services and Common Gateway Interface will be enabled.  If you open a web browser and type 127.0.0.1 in the browser, you should now see the home page for Internet Information Services.

<br />

<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/install-php-manager.png" height="40%" width="40%" alt="Install PHP manager">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/install-rewrite-module.png" height="40%" width="40%" alt="Install rewrite module">
</p>


Download the appropriate version of _PHP Manager_ from https://github.com/phpmanager/phpmanager/releases and install.  Next, download the _Rewrite Module_ from https://www.iis.net/downloads/microsoft/url-rewrite and install.  _PHP Manager_ allows you to install, run, and manage PHP versions on a Windows server running the IIS webserver.  The _ISS URL Rewrite Module_ is a tool used to convert complex web addresses into consistent, memorable, URL's. 
<br />

<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-php.png" height="80%" width="80%" alt="Install PHP"/>


Next we will install _PHP_.  First navigate to the root of the C drive and create a PHP folder.  Next, go to https://windows.php.net/download#php-8.2.  Download and install the appropriate zip file.  For Windows that will most likely be _VS16 x64 Thread Safe_.  Once the zip file is downloaded, extract the file to the PHP folder you just created.  _PHP_ is a server side scripting language that osTicket uses to serve up the web pages that provide the user interface. 
<br />

<img src="https://github.com/ElwoodMattHowell/images/blob/main/install-mysql.png" height="50%" width="50%" alt="install MySQL"/>


The next step will involve downloading and installing Microsoft Visual C++ Resdistributable(vc_redist) and MySQL.  We can quickly install vc_redist by clicking on this link and installing the file https://aka.ms/vs/17/release/vc_redist.x64.exe.  The Visual C++ Redistributable installs Microsoft C and C++ (MSVC) runtime libraries. These libraries are required by many applications built by using Microsoft C and C++ tools.  Now we need to download and install MySQL.  OsTicket will use MySQL in conjunction with HeidiSQL to create and access a database.  Navigate to https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view and download MySQL.  Once MySQL is finished downloading, open the file and follow the prompts for _Typical Installation_ and click _Finish_.  We will now be promted to configure MySQL.  Proceed with the standard configuration.  Enter your choice of a password and make note, you will need it later.  Once you have entered the password click _Execute_.  Once MySQL has completed processing the configuration, click _Finish_.
<br />

<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/register-php-1.png" height="40%" width="35%" alt="Register PHP">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/register-php-2.png" height="40%" width="45%" alt="Register PHP">
</p>


Now we have to register PHP from within IIS.  To do this we must open IIs as an administrator.  In the search panel type IIS and right click on _Internet Information Services_.  Click _Run as administrator_.  Once IIS has opened, click on _PHP Manager_.  Click on _Register new PHP version_.  You will be prompted to enter the file path to php-cgi.exe.  Provided you have followed the previous steps, the example path given will be the correct path.  You may also browse for the file.  When the correct file path is entered, click _OK_.  Under the _connections_ panel to the left of the screen, double click on your computer name and in the _Manage Server_ panel to the right, click _restart_. 
<br />

<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/osTicket-install-1.png" height="40%" width="45%" alt="Register PHP">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/osTicket-installer.png" height="40%" width="35%" alt="Register PHP">
</p>


It is now time to download and install osTicket.  Go to https://osticket.com/download/, choose the most recent version of OsTicket and follow the steps to download.  At this point, do not add any of the plugins.  Once osTicket is downloaded, unzip the contents.  There should be two folders; scripts and upload.  Copy the upload folder to c:\inetpub\wwwroot and within c:\inetpub\wwwroot rename the upload folder to osTicket.  Now, reopen IIS, and again restart the server in the _Manage Server_ panel to the right.  Open _Sites -> Default Web Site -> osTicket_, click on _osTicket_ and click _Browse *.80(http)_ in the panel to the right.  This should open the osTicket installer web page in your browser. 
<br />


<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/enable-extensions.png" height="40%" width="40%" alt="ost configure permissions">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/enable-extensions-II.png" height="40%" width="40%" alt="ost configure permissions">
</p>


Note that some extensions in osTicket are not enabled.  Go back to IIS, click through _Sites -> Default Web SIte -> osTicket_.  Double click _PHP Manager_.  Click _Enable or disable an extension_.  Scroll down until you see _php_imap.dll_ and click on it.  Then, in the upper right panel, click _Enable_. Repeat the process for _php_intl.dll_ and _php_opcache.dll_.
<br />


<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/ost-config-permissions-1.png" height="40%" width="40%" alt="ost configure permissions">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/ost-config-permissions.png" height="40%" width="40%" alt="ost configure permissions">
</p>


Now that osTicket is installed, we have to rename osTicket\include\ost-sampleconfig.php to osTicket\include\ost-config.php and assign permissions to the file.  Navigate to C:\inetpub\wwwroot\osTicket\include, scroll down to the bottom and rename ost-sampleconfig.php to ost-config.php.  Next, right click on the file and click _Properties_, click through to _Security_, and click _Advanced_.  Click _Disable inheritance_ and _Remove all inherited permissions from this object_.  Then click _Add_ and _Select a principal_.  In the box _Enter the object name to select_, type everyone and click _Check Names_.  Click _OK_, and under _Basic Permissions_, check _Full control_.  Click _OK_, _Apply_, _OK_.
<br />


<img src="https://github.com/ElwoodMattHowell/images/blob/main/osTicket-setup.png" height="40%" width="40%" alt="osTicket setup">


Next we will return to osTicket and continue to set it up.  At the bottom of the first page click _Continue_.  On the next page, you can choose a name for your Helpdesk and enter a default email(this address will recieve emails from customers).  Next fill out the Admin User information keeping track of the email, username, and password entered.  Pause at Database settings.
<br />

<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/HeidiSQL-setup1.png" height="40%" width="40%" alt="HeidiSQL install">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/HeidiSQL-setup.png" height="40%" width="40%" alt="\HeidiSQL install">
</p>


At this point we will install HeidiSQL.  HeidiSQL will allow us to see and edit data and structures from our MySQL database.  Click the following link to install https://www.heidisql.com/download.php?download=installer.  Once it has been downloaded, click the file to install and follow through with the default settings.  After installation, HeidiSQL should open automatically.  In the bottom right corner click _New_.  In the password field, enter the password you used for MySQL and press _Enter_.  Right click on _Unnamed_ in the left panel and click _Create New_, _Database_.  Name the database osTicket and click _OK_. 
<br />


<p float="left">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/osTicket-database.png" height="40%" width="35%" alt="osTicket final setup">
  <img src="https://github.com/ElwoodMattHowell/images/blob/main/osTicket-complete.png" height="40%" width="45%" alt="osTicket final setup">
</p>


Now we can finish setting up the database in osTicket.  Return to osTicket enter osTicket for the database name, the username should be root, the password is again your MySQL password, and click install.  You have completed the installation, congratulations!  You can browse to your desktop login page at http://localhost/osTicket/scp/login.php.  End users can log in at http://localhost/osTicket/.  There are two quick clean up tasks to do.  Navigate to C:\inetpub\wwwroot\osTicket and delete the setup file.  Next Navigate to C:\inetpub\wwwroot\osTicket\include\ost-config.php and set the permissions to 'Read' only.
<br />
