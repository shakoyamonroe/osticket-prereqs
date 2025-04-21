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

<img width="341" alt="osticket-vm" src="https://github.com/user-attachments/assets/4a338c0f-f0c5-4f07-bc3e-61952060631c" />
<img width="332" alt="windows:standard" src="https://github.com/user-attachments/assets/db68a7dd-3376-41ef-af16-5ae3910ebdfd" />
	
Step 1: Create Azure VM and Install IIS
Begin by accessing the Azure Portal and selecting “Create a Resource” to deploy a new Windows 10 Pro virtual machine. Configure the VM with the name osticket-vm, choose the region closest to your location, and select the Standard_D2s_v3 size (2 vCPUs, 8 GiB RAM) for optimal performance. Use Windows 10 Pro, version 22H2 - x64 Gen2 as the OS image to ensure compatibility with the required services. Once deployed, this virtual machine will serve as the host for osTicket and IIS.


<img width="436" alt="Screenshot 2025-03-05 at 9 32 43 AM" src="https://github.com/user-attachments/assets/698c4a4e-6a89-4efe-9475-fb9b137783cf" />

Connect to VM via RDP
After the VM is deployed, use Remote Desktop (RDP) and the public IP address to securely connect to your Windows 10 machine.


<img width="661" alt="Screenshot 2025-03-05 at 9 44 57 AM" src="https://github.com/user-attachments/assets/fbc563f8-b48c-4847-93b1-4379a6a74042" />


Install IIS
Open Server Manager, navigate to Add Roles and Features, and select Web Server (IIS). Under Application Development, make sure the CGI feature is enabled.



 
 
<img width="569" alt="Screenshot 2025-03-05 at 9 51 49 AM" src="https://github.com/user-attachments/assets/ecdc6703-f40b-4662-898c-fae481842e20" />
<img width="723" alt="Screenshot 2025-03-05 at 10 00 03 AM" src="https://github.com/user-attachments/assets/63c13259-a27f-485a-ab5a-fe20d4f1fa4a" />
<img width="481" alt="Screenshot 2025-03-05 at 10 03 00 AM" src="https://github.com/user-attachments/assets/efe94f55-864b-493d-b987-5d9947ee65a8" />
<img width="486" alt="Screenshot 2025-03-05 at 10 10 52 AM" src="https://github.com/user-attachments/assets/264502ea-1915-433c-a3dd-f3836981022c" />

Download and Install Components
Begin by downloading and installing the required software: PHP Manager for IIS, the IIS Rewrite Module, VC_redist.x86.exe, and MySQL 5.5.62. These tools are essential for running PHP-based applications and managing database connectivity within the Windows environment.

<img width="590" alt="Screenshot 2025-03-05 at 10 22 27 AM" src="https://github.com/user-attachments/assets/8ea2b6c4-df3e-4211-aa49-e7040a960266" />
<img width="585" alt="Screenshot 2025-03-05 at 10 22 43 AM" src="https://github.com/user-attachments/assets/9c2dc5d4-5acd-4a22-855a-ed7305276a24" />

Restart IIS to apply changes.
Open IIS Manager, select your server (osticket-vm), and click Stop, then Start under the Manage Server section to restart the service —this activates the web server so it can begin serving osTicket.


 
<img width="701" alt="Screenshot 2025-03-05 at 10 29 50 AM" src="https://github.com/user-attachments/assets/57789a49-eb45-4cd3-8570-675bffbaa9ce" />

Download and extract osTicket to:
C:\inetpub\wwwroot\osTicket

<img width="577" alt="Screenshot 2025-03-05 at 10 31 07 AM" src="https://github.com/user-attachments/assets/163c4804-9b2b-4ddb-b5e3-a01398c202d9" />

With osTicket configured in IIS, the user selects the site under Default Web Site and clicks *“Browse :80 (http)” to launch the osTicket setup page in a browser, verifying that the application is accessible and ready for final installation.

<img width="377" alt="Screenshot 2025-03-05 at 10 33 35 AM" src="https://github.com/user-attachments/assets/da0cf2a3-73d9-4c04-9dae-1256901f9edf" />
<img width="262" alt="Screenshot 2025-03-05 at 10 34 06 AM" src="https://github.com/user-attachments/assets/dd85beb0-1a4d-4969-b4f1-adcac8ad38e4" />
<img width="245" alt="Screenshot 2025-03-05 at 10 34 45 AM" src="https://github.com/user-attachments/assets/e6dc9ed9-8add-4ebc-9502-1ec5993c71e5" />

Enable Required PHP Extensions
Enable the necessary PHP extensions in IIS to ensure osTicket functions properly. Specifically, activate php_imap.dll, php_intl.dll, and php_opcache.dll by modifying the PHP configuration settings within the PHP Manager or directly in the php.ini file.

<img width="629" alt="Screenshot 2025-03-05 at 10 37 52 AM" src="https://github.com/user-attachments/assets/b5b80653-8be3-4524-9f69-8ed586fef104" />
<img width="632" alt="Screenshot 2025-03-05 at 10 36 46 AM" src="https://github.com/user-attachments/assets/126a10b3-0457-4e11-b308-0c135b5338d8" />
<img width="782" alt="Screenshot 2025-03-05 at 10 39 28 AM" src="https://github.com/user-attachments/assets/dc0d16cd-ec6d-460b-9ddf-61cf8a8d4e28" />

Rename ost-config.php and set full permissions:
Right-click > Properties > Security > Add "Everyone" with full control
Restart IIS to apply changes



 <img width="788" alt="Screenshot 2025-03-05 at 10 48 20 AM" src="https://github.com/user-attachments/assets/74753633-5434-413d-b0fd-f756d24a5513" />
 
  Configure Database in HeidiSQL
Launch HeidiSQL and connect to your MySQL server using the credentials set during installation. Once connected, create a new database named osticket, which will store all the data for your help desk application.


 <img width="380" alt="Screenshot 2025-03-05 at 10 46 39 AM" src="https://github.com/user-attachments/assets/950f1937-4f72-4b5d-aa6d-dd5d0fb07d56" />

 <img width="457" alt="Screenshot 2025-03-05 at 10 47 14 AM" src="https://github.com/user-attachments/assets/1c6b3b67-c368-44ab-890e-c34119804aae" />

 <img width="609" alt="Screenshot 2025-03-05 at 10 50 30 AM" src="https://github.com/user-attachments/assets/4a740220-38d0-4e09-a9bb-83b7d41f8d69" />






 
