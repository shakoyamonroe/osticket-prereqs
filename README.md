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

<img width="661" alt="Screenshot 2025-03-05 at 9 44 57 AM" src="https://github.com/user-attachments/assets/fbc563f8-b48c-4847-93b1-4379a6a74042" />

<img width="486" alt="Screenshot 2025-03-05 at 10 10 52 AM" src="https://github.com/user-attachments/assets/a4de914e-28a7-40c6-b194-003b30cc5d71" />



2️⃣ Install Required Components
	•	Install PHP Manager for IIS, IIS Rewrite Module, VC_redist, and MySQL 5.5.62.
	•	Extract PHP 7.3.8 into C:\PHP and register it in IIS Manager.
 
 
<img width="569" alt="Screenshot 2025-03-05 at 9 51 49 AM" src="https://github.com/user-attachments/assets/ecdc6703-f40b-4662-898c-fae481842e20" />

<img width="723" alt="Screenshot 2025-03-05 at 10 00 03 AM" src="https://github.com/user-attachments/assets/63c13259-a27f-485a-ab5a-fe20d4f1fa4a" />

<img width="481" alt="Screenshot 2025-03-05 at 10 03 00 AM" src="https://github.com/user-attachments/assets/efe94f55-864b-493d-b987-5d9947ee65a8" />

<img width="486" alt="Screenshot 2025-03-05 at 10 10 52 AM" src="https://github.com/user-attachments/assets/264502ea-1915-433c-a3dd-f3836981022c" />

<img width="590" alt="Screenshot 2025-03-05 at 10 22 27 AM" src="https://github.com/user-attachments/assets/8ea2b6c4-df3e-4211-aa49-e7040a960266" />

<img width="585" alt="Screenshot 2025-03-05 at 10 22 43 AM" src="https://github.com/user-attachments/assets/9c2dc5d4-5acd-4a22-855a-ed7305276a24" />


3️⃣ Install & Configure osTicket
	•	Move osTicket files to C:\inetpub\wwwroot\osTicket and restart IIS.
	•	Enable PHP extensions (php_imap.dll, php_intl.dll, php_opcache.dll).
	•	Rename ost-config.php and set permissions.
 
<img width="701" alt="Screenshot 2025-03-05 at 10 29 50 AM" src="https://github.com/user-attachments/assets/57789a49-eb45-4cd3-8570-675bffbaa9ce" />

<img width="577" alt="Screenshot 2025-03-05 at 10 31 07 AM" src="https://github.com/user-attachments/assets/163c4804-9b2b-4ddb-b5e3-a01398c202d9" />

<img width="377" alt="Screenshot 2025-03-05 at 10 33 35 AM" src="https://github.com/user-attachments/assets/da0cf2a3-73d9-4c04-9dae-1256901f9edf" />

<img width="262" alt="Screenshot 2025-03-05 at 10 34 06 AM" src="https://github.com/user-attachments/assets/dd85beb0-1a4d-4969-b4f1-adcac8ad38e4" />

<img width="245" alt="Screenshot 2025-03-05 at 10 34 45 AM" src="https://github.com/user-attachments/assets/e6dc9ed9-8add-4ebc-9502-1ec5993c71e5" />

<img width="629" alt="Screenshot 2025-03-05 at 10 37 52 AM" src="https://github.com/user-attachments/assets/b5b80653-8be3-4524-9f69-8ed586fef104" />

<img width="632" alt="Screenshot 2025-03-05 at 10 36 46 AM" src="https://github.com/user-attachments/assets/126a10b3-0457-4e11-b308-0c135b5338d8" />

<img width="782" alt="Screenshot 2025-03-05 at 10 39 28 AM" src="https://github.com/user-attachments/assets/dc0d16cd-ec6d-460b-9ddf-61cf8a8d4e28" />







4️⃣ Final Setup & Database Configuration
	•	Create the osTicket database in HeidiSQL.
	•	Complete installation via browser with Helpdesk Name, Email, and MySQL credentials.

 <img width="788" alt="Screenshot 2025-03-05 at 10 48 20 AM" src="https://github.com/user-attachments/assets/74753633-5434-413d-b0fd-f756d24a5513" />

 <img width="380" alt="Screenshot 2025-03-05 at 10 46 39 AM" src="https://github.com/user-attachments/assets/950f1937-4f72-4b5d-aa6d-dd5d0fb07d56" />

 <img width="457" alt="Screenshot 2025-03-05 at 10 47 14 AM" src="https://github.com/user-attachments/assets/1c6b3b67-c368-44ab-890e-c34119804aae" />

 <img width="609" alt="Screenshot 2025-03-05 at 10 50 30 AM" src="https://github.com/user-attachments/assets/4a740220-38d0-4e09-a9bb-83b7d41f8d69" />






 
