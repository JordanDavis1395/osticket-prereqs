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

Create an Azure Virtual Machine Windows 10, 4 vCPUs

Name: osticket-vm

Username: labuser

Password: osTicketPassword1!
![Screenshot 2025-02-24 115033](https://github.com/user-attachments/assets/cbd610a6-1352-420c-8d31-7ac3c401c583)
![Screenshot 2025-02-24 115206](https://github.com/user-attachments/assets/5cc95b4c-1723-4fac-9e90-9104d561749d)
![Screenshot 2025-02-24 115311](https://github.com/user-attachments/assets/0328a35e-b4f1-4eec-b6fa-bc7f69830313)
![Screenshot 2025-02-24 115405](https://github.com/user-attachments/assets/902dcca5-0d30-426b-9c66-c539d3dfccfc)


Log into the VM with Remote Desktop

Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop.

This is the link to the file: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

The folder should be called “osTicket-Installation-Files”

We will use the files in this folder to install osTicket and some of the dependencies.
![Screenshot 2025-02-24 115817](https://github.com/user-attachments/assets/34824508-37cd-41da-965f-659ed761bfb1)
![Screenshot 2025-02-24 115900](https://github.com/user-attachments/assets/f9541760-936c-4b74-92aa-0796fa649cf1)


Install / Enable IIS in Windows WITH CGI

World Wide Web Services -> Application Development Features -> [X] CGI
![Annotation 2025-02-24 180723](https://github.com/user-attachments/assets/4d478466-7d05-48ff-b137-c7cef6dfc958)
![Annotation 2025-02-24 180822](https://github.com/user-attachments/assets/d5c12b9f-ea40-492d-9b31-afae3c656fcf)
![Annotation 2025-02-24 180848](https://github.com/user-attachments/assets/de52b3d8-1a1a-4d5b-bcbe-86e5c38fc6d8)
![Annotation 2025-02-24 180948](https://github.com/user-attachments/assets/3ff917cd-340a-4f92-9fd6-3fe67b332454)


From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
![Annotation 2025-02-24 181208](https://github.com/user-attachments/assets/6b5de5ac-28a8-4d27-b367-8ad95d6c200d)


From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
![Annotation 2025-02-24 181249](https://github.com/user-attachments/assets/cfe88010-e8ec-4c0c-9d8c-447029005806)


Create the directory C:\PHP
![Annotation 2025-02-24 181346](https://github.com/user-attachments/assets/3722eccb-7936-41c6-8b3b-5e33fe973280)

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
![Annotation 2025-02-24 181450](https://github.com/user-attachments/assets/9f160fde-3872-456f-8f62-b2202ecd6666)

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
![Annotation 2025-02-24 181602](https://github.com/user-attachments/assets/6713ebe6-0c1f-45b5-af47-af926279f8ca)


From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

Typical Setup ->

Launch Configuration Wizard (after install) ->

Standard Configuration ->

Username: root

Password: root

![Annotation 2025-02-24 181712](https://github.com/user-attachments/assets/0004cb9b-a6d8-4904-903e-e1d56cbee909)
![Annotation 2025-02-24 181808](https://github.com/user-attachments/assets/558ead31-404b-464d-8f1a-0169eae79500)
![Annotation 2025-02-24 181904](https://github.com/user-attachments/assets/6e8dac9d-9a9e-4cec-ae0e-7d21fe859040)
![Annotation 2025-02-24 182028](https://github.com/user-attachments/assets/b6bfdb9a-5f65-4747-a3b0-d4835d0c13e1)

Open IIS as an Admin
![Annotation 2025-02-24 182112](https://github.com/user-attachments/assets/52561cae-dfbc-42e0-8f50-c3ba6a4bb1be)



Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
![Annotation 2025-02-24 182241](https://github.com/user-attachments/assets/8b834598-5d4d-4646-a73f-b3f7365262b8)
![Annotation 2025-02-24 182318](https://github.com/user-attachments/assets/8e2eb3d2-3635-45cd-82d4-71ff42b58d84)
![Annotation 2025-02-24 182349](https://github.com/user-attachments/assets/0179ee5e-6a57-4392-bccd-3d659f6b149a)


Reload IIS (Open IIS, Stop and Start the server)
![Annotation 2025-02-24 182444](https://github.com/user-attachments/assets/efd1d0e1-dc31-4cd5-a29f-71771059b38c)
![Annotation 2025-02-24 182521](https://github.com/user-attachments/assets/90d75725-6ad2-42df-a476-7e1fb0ab6579)


Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
![Annotation 2025-02-24 182623](https://github.com/user-attachments/assets/4dc8522e-7624-475a-959c-50100453390b)
![Annotation 2025-02-24 183027](https://github.com/user-attachments/assets/ce25b77f-f5e9-4bef-ad0e-817af4b49e55)
![Annotation 2025-02-24 183059](https://github.com/user-attachments/assets/884460da-b032-4ba5-aa68-e20b815ae1c7)


Reload IIS (Open IIS, Stop and Start the server)
![Annotation 2025-02-24 182444](https://github.com/user-attachments/assets/8addf4f9-db94-4af2-9685-b22a5a86afee)
![Annotation 2025-02-24 182521](https://github.com/user-attachments/assets/2a29248c-dcbc-4501-abb8-bbe877c9ac6d)

Go to sites -> Default -> osTicket

On the right, click “Browse *:80”
![Annotation 2025-02-24 183222](https://github.com/user-attachments/assets/0df79224-865a-4073-83cd-d3cac09f6b58)
![Annotation 2025-02-24 183256](https://github.com/user-attachments/assets/0cbddbc0-3a83-4594-8403-2bed35e1aa90)

Note that some extensions are not enabled

Go back to IIS, sites -> Default -> osTicket

Double-click PHP Manager

Click “Enable or disable an extension”

Enable: php_imap.dll
![Annotation 2025-02-24 183351](https://github.com/user-attachments/assets/c5f0a2cc-b4c4-4a19-bcbf-7a046706d1d5)


Enable: php_intl.dll
![Annotation 2025-02-24 183422](https://github.com/user-attachments/assets/e3f06d14-1bb5-4fb9-9d4d-e0bc9bf6fefd)


Enable: php_opcache.dll
![Annotation 2025-02-24 183502](https://github.com/user-attachments/assets/4cdad674-6f66-47e4-a3ee-ba174c36bdf5)


Refresh the osTicket site in your browser, observe the changes
![Annotation 2025-02-24 183544](https://github.com/user-attachments/assets/8396f7ee-07ae-46a0-93d8-eae608aad96d)




Rename: ost-config.php

From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
![Annotation 2025-02-24 183639](https://github.com/user-attachments/assets/8bbb3b42-6539-4b4c-86c5-e765cd8b3c4e)

To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
![Annotation 2025-02-24 183714](https://github.com/user-attachments/assets/4f3d2df1-2efd-460b-9d20-62583a945e53)


Assign Permissions: ost-config.php
![Annotation 2025-02-24 183752](https://github.com/user-attachments/assets/c36c0790-e9c4-433c-8230-a3cf776a8ac3)

Disable inheritance -> Remove All
![Annotation 2025-02-24 183923](https://github.com/user-attachments/assets/bd82cec5-43e8-450f-bef4-16224d1f3a6b)
![Annotation 2025-02-24 184005](https://github.com/user-attachments/assets/15736d98-725f-4b02-a4cc-197dec22d51d)

New Permissions -> Everyone -> All
![Annotation 2025-02-24 184113](https://github.com/user-attachments/assets/d5b0852e-1065-4c98-a81e-1c842ab4e58f)
![Annotation 2025-02-24 184136](https://github.com/user-attachments/assets/52ffaab3-968d-4a11-af85-1b36739b5575)
![Annotation 2025-02-24 184209](https://github.com/user-attachments/assets/4b3f6974-097b-46f8-9c7e-062ef52f60c1)
![Annotation 2025-02-24 184244](https://github.com/user-attachments/assets/32cafb03-61b6-4383-845a-81101c37cdf0)


Continue Setting up osTicket in the browser (click Continue)

Name Helpdesk

Default email (receives email from customers)
![Annotation 2025-02-24 184541](https://github.com/user-attachments/assets/3b8e0bf6-e697-46dc-b482-10c4dce49bdf)


From the “osTicket-Installation-Files” folder, install HeidiSQL.
![Annotation 2025-02-24 184710](https://github.com/user-attachments/assets/0f5829be-c4d4-400d-a7d7-1d2d9ca2ac38)

Open Heidi SQL
![Annotation 2025-02-24 184931](https://github.com/user-attachments/assets/4d04c5f9-2f43-4e38-920a-be2d04e8a672)

Create a new session, root/root
![Annotation 2025-02-24 184953](https://github.com/user-attachments/assets/131b40a5-c8ab-409f-827e-a5d4aec369e2)

Connect to the session

Create a database called “osTicket”
![Annotation 2025-02-24 185034](https://github.com/user-attachments/assets/003f2bf4-b403-45f9-b09b-b06bf7b1f6d4)
![Annotation 2025-02-24 185117](https://github.com/user-attachments/assets/c34b69aa-d253-4bbf-b218-506092767522)


Continue Setting up osTicket in the browser

MySQL Database: osTicket

MySQL Username: root

MySQL Password: root

Click “Install Now!”
![Annotation 2025-02-24 184541](https://github.com/user-attachments/assets/6216ba76-e377-4c1e-8392-3c3beba6649b)


Congratulations, you made it to the end! You have installed osTicket!!
