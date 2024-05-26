- <b>osTicket (Help Desk Ticketing System)</b>
- osTicket-Installation

  <h1>osTicket - Prerequisites and Installation</h1>
 - This projects outlines the requirement and process of installing the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines named: vm-osTicket)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


 ![osTicket_Admin](https://github.com/koby-nob/osTicket-Installation/assets/166937258/d77070ba-ae78-4a35-80a5-2408c34dbe64)

<h2>List of Pre-Install Files</h2>

- PHPManagerForIIS_V1.5.0.msi or current version
- rewrite_amd64_en-US.msi
- php(-7.3.8-nts-Win32-VC15-x86.zip file
- VC.redist.x86.exe
- mysql-5.5.62-win32.msi or current version
- Heidisql_12.3.0.6589_setup.exe
 


<h2>Installation Steps</h2>

- This project will display only the section of osTicket after these virtual Machine osTicket has been created in Micorsoft Azure and the Internet Information Service has been enabled:
- VM osTicket
- Remote Desktop
- Internet Information Service (IIS)

<p>
<img src="https://i.imgur.com/WDvuXdL.png"
</p>
<p>
  
    - Download and install the PHP Manager file from the install files.
    - The version PHPManagerForIIS_V1.5.0.msi or the lastest version

<p>
<img src="https://i.imgur.com/iFfu2qW.png"
</p>
<p>
  
    - Download and install the Rewrite Module from the install files.
    - The rewrite_amd64-en-US.msi or the lastest version

<p>
<img src="https://i.imgur.com/V1D7lSk.png"
</p>
<p>
  
    - Create the directory C:\PHP then from install files, download PHP.7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

<p>
<img src="https://i.imgur.com/K5W0JGl.png"
</p>
<p>
  
    - Download and install VC-redist.x86.exe file from the install files

<p>
<img src="https://i.imgur.com/7Jt7fU2.png"
</p>
<p> 
  
    - Download and install MySQl 5.5.62(mysql-5.5.62-win32.msi) from the install files or the lastest version
    - Typical Setup ->
    - Launch Configuration Wizard (after install) 
    - Standard Configuration ->
    - Password1 (for the purpose of this project).



<p>
<img src="https://i.imgur.com/URAmZwl.png"
</p>
<p>

    - Prior to installation of the Heidi SQL, these installation steps below need to be completed:
    - Register PHP from within IIS

    - Reload IIS (Open IIS, Stop and Start the server)

    - Install osTicket v1.15.8
    - Download osTicket from the install files
    - Extract and copy “upload” folder to c:\inetpub\wwwroot
    - Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

    - Reload IIS (Open IIS, Stop and Start the server)
    - Go to sites -> Default -> osTicket
    - On the right, click “Browse *:80”

    - Note that some extensions are not enabled
    - Go back to IIS, sites -> Default -> osTicket

    - Double-click PHP Manager
    - Click “Enable or disable an extension”
    - Enable: php_imap.dll
    - Enable: php_intl.dll
    - Enable: php_opcache.dll
    - Refresh the osTicket site in your browse, observe the changes

    - Rename: ost-config.php
    - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

    - Assign Permissions: ost-config.php
    - Disable inheritance -> Remove All
    - New Permissions -> Everyone -> All

    - Continue Setting up osTicket in the browser (click Continue)
    -  Name Helpdesk
    - Default email (receives email from customers)


    - Download and install the Heidisql
    - Open Heidi Sql
    - Create a new session, root/Password1(for the purpose of this project)
    - Connect to the session
    - Create a database called "osTicket"

    
<p>
<img src="https://i.imgur.com/bZFDVjS.png"
</p>
<p>
  
    - If you see congratulations page, it means installation is successful.
    - The next step is to browse to the help desk login page: http://localhost/osTicket/scp/login.php

     
<p>
<img src="https://i.imgur.com/SEW5VbT.png"
</p>
<p> 
  
    - Go to Login page. Find the End Users osTicket URL: http://localhost/osTicket/ 
    - Login to osTicket ( Username: koby001 (for the purpose of this project)
    
<p>
<img src="https://i.imgur.com/IoGCHUs.png"
</p>
<p>
   
     - Above image displays when a user succesfuly logs into the osTicket account.
     
