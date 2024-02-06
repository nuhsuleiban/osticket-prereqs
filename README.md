<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Ticket Lifecycle: Intake Through Resolution</h1>
This tutorial outlines the lifecycle of a ticket from intake to resolution within the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Requirements

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop- Working the Issue
- Internet Information Services (IIS)

<h2>Tutorial Instructions
 
<h2> Step 1: Install / Enable IIS in Windows


Access the "Control Panel", "Programs", then "Programs and Features". Then select "Turn Windows features on or off" on the left. On the pop up window, select the box for "Internet Information Services."

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/1f6a4588-9975-48a3-b8ba-a22fdf760be9">

Step 2: Install Web Platform Installer

Click the following link for the required downloads https://bit.ly/3WFRPdg. Now download the Web Platform Installer and open it.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/73e07363-a01f-4573-852e-f81c18764cf1">

From inside the application you will search and install "MySQL 5.5," all "PHP" versions up until 7.3.25. As pictured below, some of the files will fail to download, however the links for those can also be found on the aforementioned install link.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/013736a9-3b3d-4032-8330-fb3c4edddf52">

Step 3: Install osTicket v1.15.8

Click the link from within the lab files to download osTicket. Once it is in your "Downloads" folder, right click the folder and click "Extract All" to create another folder that we will use later.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/c30b84c1-5819-4502-8a80-7d0a6228d0ab">

In the "Downloads" folder open osTicket, and we are going to copy the upload folder. Navigate to "This PC', "Windows (C:)", "inetpub", "wwwroot", and paste within wwwroot. Next, simply rename the "upload" folder to "osTicket".



Step 4: Reload IIS


Go back to IIS by typing it in the Start menu. Click "Restart" on the right side. On the left side click "Sites", "Default Web Site", "osTicket", then on the right side click "Browse *:80". This should open a web browser to osTicket.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/4792d33f-2aef-41fd-8914-05e2259c1473"> 

Step 5: Enable Extensions in IIS

Now we are going to go back to IIS Manager. Once again, you can find this by typing it in the Start menu. Navigate to "Sites", "Default", "osTicket", double click on "PHP Manager" and then click "Enable or Disable an Extension". Enable the following extensions: "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Then, you can refresh osTicket site in your browser.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/b939836c-166b-4adf-b5a7-87e2608c20a3">

Step 6: Rename ost-config.php

In file explorer go back to the osTicket folder and click on the file "Include". Next rename "ost-sampleconfig.php" to "ost-config.php". It's critical that you do not make an error at this step.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/7f735453-a8b7-4f56-a691-188f52a6c3aa">

Step 7: Assign Permissions to ost-config.php

Next we need to assign permissions to ost-config.php. To do that, right click on ost-config.php, go to "Properties", "Security", "Advanced", and "Disable Inheritance". From here we are going to click "Add" so we can add our own permissions. Next click "Select Principal", and type in "Everyone" in the space provided. Click "Check Names", "Ok", and then you want to allow "Full Control".

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/c1b51538-4e6e-48d9-b4b4-f7cb4c5f82d5"> 

Step 8: Continue osTicket Setup in Browser

Setup the name and database information in osTicket. It is important to keep note of the login and password information for later.

Step 9: Download and Install HeidiSQL

Go to the install files I have provided, and download HeidiSQL. Open the file in "Downloads" and install.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/2b7b1e61-ca9e-4c32-8718-2b62decd741f">

Next click "New" in HeidiSQL and enter the password you created for MySQL at the beginning of this lab, and open. Right click "Unnamed" and create a new database called "osTicket".

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/8b0f614f-226d-479f-9847-7497877f7d34">

Back in osTicket in the browser you can enter the information for MySQL database which we named "osTicket", the MySQL Username which at the beginning of the lab we named "root", and finally the password you created. Click "Install Now", and osTicket should now be installed successfully.

<img width="1436" alt="image" src="https://github.com/nuhsuleiban/osticket-prereqs/assets/153963865/1b49b166-fc00-4215-9d40-450a7b4ae611"> 




