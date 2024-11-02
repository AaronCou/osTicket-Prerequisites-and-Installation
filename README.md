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

- [URL Rewrite for IIS](https://www.iis.net/downloads/microsoft/url-rewrite)
- [PHP Manager for IIS](https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10)
- [Visual C++ Redistributable x86](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version)
- [MySQL](https://www.mysql.com/downloads/)
- [HeidiSQL](https://www.heidisql.com/download.php)

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/0Fe1P2J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Login to Azure Portal and Create a Resource Group for to contain the services required to setup osTicket  
</p>
<br />

<p>
<img src="https://i.imgur.com/qKYWk9f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Next go back home and create a virtual machine, this will allow you to run a standalone computer in the cloud, see below for important settings and steps
</p>
<br />

<p>
<img src="https://i.imgur.com/D6QxOp7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2nOnIJW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5wDktbt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
- Make sure you use the resource group you had just created.
- Use a normal Windows 10 image for the "Image" setting
- Rename the virtual network that wil get created alongside the virtual machine

<br />

<p>
<img src="https://i.imgur.com/W1hBhQp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Take note of the VM's public IP address
</p>
<br />

<p>
<img src="https://i.imgur.com/AcenkXI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Use Remote Desktop to login to the VM
</p>
<br />

<p>
<img src="https://i.imgur.com/91PeDhQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Gather all prerequisites and osTicket installation files.
</p>
<br />

<p>
<img src="https://i.imgur.com/llvZ0MB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Go to control panel -> Programs -> Programs & Features then click "Turn Windows Features On or Off" and enable "Internet Information Services" & 'cgi' (cgi is under Internet Information Services -> Application Development Features)
</p>
<br />

<p>
<img src="https://i.imgur.com/G7rTg80.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Create A folder within your C: drive named PHP and unzip the contents of the PHP zip file into it
</p>
<br />

<p>
<img src="https://i.imgur.com/91PeDhQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Now Install PHPManager for IIS, URL Rewrite and c++ visual redistributable
</p>
<br />

<p>
<img src="https://i.imgur.com/PV5i7oj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Now install MySQL with a typical installation once installed, setup using a standard config with a username and password of your choice.
</p>
<br />

<p>
<img src="https://i.imgur.com/mpyYoV4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Now open up IIS Manager and go to PHP Manager within it
</p>
<br />

<p>
<img src="https://i.imgur.com/fUdOTzb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Within PHP Manager click "Register new PHP version" then select the PHP file within the PHP folder we created within the C: drive.
</p>
<br />

<p>
<img src="https://i.imgur.com/QGR9XM6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Next scroll down and you will see a PHP Extensions section, click "Enable or disable an extension"
</p>
<br />

<p>
<img src="https://i.imgur.com/u5zfRkS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Enable the, imap, intl & opcache extensions. (use the search bar if you are having trouble)
</p>
<br />


<p>
<img src="https://i.imgur.com/dB8kQfq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Create a folder called osTicket at C:\inetpub\wwwroot\ and copy all contents of the osTicket 'Upload' folder to it
</p>
<br />


<p>
<img src="https://i.imgur.com/63QZVky.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Go into the include folder and rename the ost-sampleconfig.php file to ost-config.php
</p>
<br />


<p>
<img src="https://i.imgur.com/Ijnd0ue.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Go to the inheritance settings of the ost-config.php file and remove all inheritance, then enable full access for everyone (change this back to read only after setup for security purposes. DO NOT FORGET)
</p>
<br />


<p>
<img src="https://i.imgur.com/lhzCmfU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Next install and open HeidiSQL and login to your MySQL database through it
</p>
<br />


<p>
<img src="https://i.imgur.com/RUtwjnN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Right click on the pane in the left and create a new database and don't forget the name
<p>
</p>
<br />


<p>
<img src="https://i.imgur.com/h0sLbvj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Open a browser and navigate to http://localhost/osTicket/setup and click continue, if you get any errors you have configured something incorrectly along the way.
</p>
<br />


<p>
<img src="https://i.imgur.com/xR56c9a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Enter all details, then when you get to the SQL section, for the database, enter the name of the database you created in heidi, for the username and password, use the credentials you created when installing MySQL.
</p>
<br />


<p>
<img src="https://i.imgur.com/xR56c9a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  CONGRATULATIONS. If you did everything correctly you should be at this screen ready to configure and setup osTicket! DO NOT FORGET to change permissions on the ost-config.php file and remove the setup folder within the osTicket directory.
</p>
<br />

