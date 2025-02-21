<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

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
  - Username:
  - Password:
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

### 1️⃣ Create an Azure Virtual Machine
- Set up a **Windows 10 VM** with **4 vCPUs** in Azure.
- Name the VM `osticket-vm`.
- Log in using Remote Desktop:
  - Username: `labuser`
  - Password: `osTicketPassword1!`

### 2️⃣ Install IIS & Enable CGI
- Open **Server Manager** → **Add Roles and Features**.
- Install **IIS** and enable **CGI** under:
  - **World Wide Web Services** → **Application Development Features** → [X] CGI.

### 3️⃣ Install Required Components
- From the `osTicket-Installation-Files` folder:
  - Install **PHP Manager for IIS** (`PHPManagerForIIS_V1.5.0.msi`).
  - Install **IIS Rewrite Module** (`rewrite_amd64_en-US.msi`).
  - Create a directory `C:\PHP`.
  - Unzip **PHP 7.3.8** into `C:\PHP`.
  - Install **VC_redist.x86.exe`.
  - Install **MySQL 5.5.62** (`mysql-5.5.62-win32.msi`).
    - Choose **Typical Setup**.
    - Launch **Configuration Wizard**.
    - Select **Standard Configuration**.
    - Set Username: `root`, Password: `root`.

### 4️⃣ Configure IIS & PHP
- Open **IIS as Admin**.
- Register PHP in IIS:
  - **PHP Manager** → Set PHP path to `C:\PHP\php-cgi.exe`.
- Restart IIS (`Stop` and `Start` the server).

### 5️⃣ Install osTicket
- Unzip `osTicket-v1.15.8.zip` and move the `upload` folder to `C:\inetpub\wwwroot`.
- Rename `upload` to `osTicket`.
- Restart IIS again.
- In IIS:
  - Go to **Sites → Default → osTicket**.
  - Click **Browse *:80**.

### 6️⃣ Enable Required PHP Extensions
- In **IIS Manager**, navigate to:
  - **Sites → Default → osTicket** → **PHP Manager**.
  - Click **Enable or Disable an Extension**.
  - Enable:
    - `php_imap.dll`
    - `php_intl.dll`
    - `php_opcache.dll`
- Refresh the osTicket site in your browser to verify.

### 7️⃣ Configure osTicket
- Rename `ost-config.php`:
  - From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
  - To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`
- Assign Permissions:
  - Disable **inheritance** → Remove all permissions.
  - Add **Everyone** → **Full Control**.

### 8️⃣ Setup MySQL Database in HeidiSQL
- Install **HeidiSQL** from `osTicket-Installation-Files`.
- Open HeidiSQL → Create a new session (`root/root`).
- Create a database: `osTicket`.

### 9️⃣ Final osTicket Installation in Browser
- Continue setting up osTicket in the browser:
  - Set **Helpdesk Name** and **Default Email**.
  - Use:
    - **MySQL Database**: `osTicket`
    - **Username**: `root`
    - **Password**: `root`
  - Click **Install Now!**.
