<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites]
(https://youtu.be/fWX1Lj-rOa0?si=BA1g1VMXSFhgVKNy)
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

Before installing osTicket, ensure you have the following:


Before installing osTicket, ensure you have the following:

- **Azure Virtual Machine**
  - Windows 10, 4 vCPUs
  - Virtual Machine Name:
  - Username:____
  - Password:____
  - Remote Desktop Access to the VM

- **Required Software & Dependencies**
  - IIS (Internet Information Services) with CGI enabled
  - PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
  - IIS Rewrite Module (rewrite_amd64_en-US.msi)
  - PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)
  - VC_redist.x86.exe
  - MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  - HeidiSQL

<h2>Installation Steps</h2>

1️⃣ Set Up the Azure VM & IIS
	•	Create a Windows 10 VM in Azure (osticket-vm), log in via RDP.
	•	Install IIS with CGI enabled.
<img width="341" alt="osticket-vm" src="https://github.com/user-attachments/assets/4a338c0f-f0c5-4f07-bc3e-61952060631c" />

<img width="332" alt="windows:standard" src="https://github.com/user-attachments/assets/db68a7dd-3376-41ef-af16-5ae3910ebdfd" />

<img width="436" alt="Screenshot 2025-03-05 at 9 32 43 AM" src="https://github.com/user-attachments/assets/698c4a4e-6a89-4efe-9475-fb9b137783cf" />



2️⃣ Install Required Components
	•	Install PHP Manager for IIS, IIS Rewrite Module, VC_redist, and MySQL 5.5.62.
	•	Extract PHP 7.3.8 into C:\PHP and register it in IIS Manager.

3️⃣ Install & Configure osTicket
	•	Move osTicket files to C:\inetpub\wwwroot\osTicket and restart IIS.
	•	Enable PHP extensions (php_imap.dll, php_intl.dll, php_opcache.dll).
	•	Rename ost-config.php and set permissions.

4️⃣ Final Setup & Database Configuration
	•	Create the osTicket database in HeidiSQL.
	•	Complete installation via browser with Helpdesk Name, Email, and MySQL credentials.
