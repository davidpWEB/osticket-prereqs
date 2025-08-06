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

- Azurre account with an active subscription.
- Created a resource group.
- Created a virtual network and subnet.
- Created a virtual machine in Azure.
- Connected to the vitual machine using remote desktop (RDP)

<h2>Installation Steps</h2>

### Step 1: Set Up a Resource Group

**Purpose:**  
Create a logical container to organize and manage your Azure resources such as virtual machines, networks, and storage.

**Instructions:**
1. In the Azure Portal, go to **Resource Groups** > **Create**.
2. Configure the following:
   - **Name:** `osticket` 
   - **Region:** Select your preferred Azure region

> 📁 Your resource group will act as the foundation for all osTicket-related resources in this project.


<p>
<img <img width="749" height="685" alt="image" src="https://github.com/user-attachments/assets/26913cc0-97bc-4fcd-ba74-eec026be2a68" />
/>
  <img width="873" height="281" alt="image" src="https://github.com/user-attachments/assets/3106e2c5-9d5c-4e9b-b983-56f62e5e7f87" />

</p>
<p>
  
### Step 2: Provision a Virtual Machine


**Purpose:**  
Deploy a Windows 10 VM to host osTicket and its required components.

**Instructions:**
1. In the Azure Portal, navigate to **Virtual Machines** > **Create**.
2. Configure the following settings:
   - **Name:** `osticket-vm`
   - **Operating System:** Windows 10 Pro
   - **Size:** 2 vCPUs
   - **Username:** `labuser`
   - **Password:** `osTicketPassword1!`
   - **Network:** Use the default Virtual Network (auto-created)

> 💡 Tip: Azure automatically generates a default VNet when creating a VM if one doesn't already exist.

</p>
<br />

<p>
<img width="787" height="496" alt="image" src="https://github.com/user-attachments/assets/311d21a3-dc8e-4a42-b2ec-669b9ff7164a" />
<img width="773" height="400" alt="image" src="https://github.com/user-attachments/assets/803d7a2a-f0da-4af9-8ecb-87aba342e486" />
<img width="780" height="539" alt="image" src="https://github.com/user-attachments/assets/f66ebccc-fe66-4fc8-8faa-c9696ccb14d1" />
<img width="439" height="670" alt="image" src="https://github.com/user-attachments/assets/f460b9c5-2027-4729-a8a5-aef8a525aa23" />

</p>
<p>
  
### Step 3: Connect to the Virtual Machine

**Purpose:**  
Access the VM via Remote Desktop Protocol (RDP) to perform necessary installations.

**Instructions:**
1. Once the VM is up and running, click **"Connect"** in the Azure Portal.
2. Select the **RDP** option.
3. Download the provided `.rdp` file and open it.
4. Log in using the following credentials:
   - **Username:** `labuser`
   - **Password:** `osTicketPassword1!`

> 🔐 Make sure RDP is enabled and your local machine allows remote connections.
</p>
<br />

<p>
<img width="397" height="446" alt="image" src="https://github.com/user-attachments/assets/54572a4d-9af5-45fe-ae88-f8286f265689" />
<img width="437" height="390" alt="image" src="https://github.com/user-attachments/assets/8f6c746e-486e-43f4-bc0d-c810c9f1276e" />
<img width="385" height="358" alt="image" src="https://github.com/user-attachments/assets/3b3dd377-2696-4df0-ac79-251a8c50fbc5" />
<img width="796" height="493" alt="image" src="https://github.com/user-attachments/assets/668e7ad3-db58-496b-aa74-de3ac7517244" />

</p>
<p>
  
### Step 4: Prepare the VM Desktop

**Purpose:**  
Set up a clean environment on the VM to begin the osTicket installation process.

**Instructions:**
1. Open **Microsoft Edge** or **Google Chrome** within the VM.
2. Download the file: [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
3. Extract the contents to the **Desktop**.
4. Rename the extracted folder to: `osTicket-Installation-Files`

> 🧹 This step ensures your installation files are organized and easy to access during setup.
</p>

<img width="523" height="164" alt="image" src="https://github.com/user-attachments/assets/88303a8d-44e6-4414-9150-b74fd4fe6751" />
<img width="340" height="440" alt="image" src="https://github.com/user-attachments/assets/d4e28f9b-dcc5-42c2-b92d-d8a59c442567" />
<img width="654" height="383" alt="image" src="https://github.com/user-attachments/assets/fd0599d8-fc45-4d5d-9ac7-3c984eb7fa49" />

### Step 5: Install IIS with CGI Enabled

**Purpose:**  
Install Internet Information Services (IIS) with CGI support, required to run osTicket.

**Instructions:**
1. On the VM, go to the **Start Menu** > **Control Panel** > **Programs** > **Turn Windows features on or off**.
2. Enable the following features:
   - **Internet Information Services**
   - **World Wide Web Services** > **Application Development Features** > ✅ **CGI**
3. Click **OK** and wait for the installation to complete.

> ⚙️ This enables the web server functionality needed for osTicket to run.

<img width="774" height="674" alt="image" src="https://github.com/user-attachments/assets/661b237d-995e-4c07-8069-62ee34b99198" />
<img width="704" height="317" alt="image" src="https://github.com/user-attachments/assets/6fb202af-5e3e-4c99-ba6e-00cc916e7b99" />
<img width="791" height="338" alt="image" src="https://github.com/user-attachments/assets/e6e04a4e-d1d6-41e9-996f-a3ae153f17fb" />
<img width="407" height="360" alt="image" src="https://github.com/user-attachments/assets/34fc67e9-f9ec-4922-adb7-131b9e361a49" />
<img width="404" height="357" alt="image" src="https://github.com/user-attachments/assets/42c40367-b1c1-4f10-b81b-0052fd5f6a29" />
<img width="408" height="362" alt="image" src="https://github.com/user-attachments/assets/7a820e9f-655d-468a-bcb5-aaa46767fad2" />
<img width="453" height="408" alt="image" src="https://github.com/user-attachments/assets/e06c3043-52ff-4b85-a7e0-e8c62871a624" />

### Step 6: Install IIS Extensions

**Purpose:**  
Add essential IIS extensions required for running osTicket.

**Instructions:**
1. Open the `osTicket-Installation-Files` folder on the Desktop.
2. Run the following installers:
   - **PHP Manager for IIS:** `PHPManagerForIIS_V1.5.0.msi`
   - **IIS Rewrite Module:** `rewrite_amd64_en-US.msi`

> 🧩 These extensions enhance IIS functionality and are required for osTicket to operate properly

<img width="774" height="380" alt="image" src="https://github.com/user-attachments/assets/0a59b810-2bf0-4a2f-87e5-6b15799c5a87" />
<img width="776" height="405" alt="image" src="https://github.com/user-attachments/assets/3400b55f-97b5-4d14-8dc2-2ae934a58a7a" />
<img width="494" height="403" alt="image" src="https://github.com/user-attachments/assets/90e9b060-599b-48ae-ab2a-cd29706956d3" />
<img width="493" height="400" alt="image" src="https://github.com/user-attachments/assets/0394a143-7d5f-4a76-8aa7-cce20821bafd" />
<img width="775" height="393" alt="image" src="https://github.com/user-attachments/assets/d5d7d30c-7765-4558-825d-3a6e50ded383" />
<img width="489" height="381" alt="image" src="https://github.com/user-attachments/assets/21a56f74-3f8b-4ed8-a5ee-0ea407386d21" />
<img width="1124" height="600" alt="image" src="https://github.com/user-attachments/assets/be3664dc-e51e-4183-ab31-39d1193e3e81" />
<img width="908" height="626" alt="image" src="https://github.com/user-attachments/assets/9d5ba508-039e-46aa-8ca7-c9326851f64a" />
<img width="608" height="446" alt="image" src="https://github.com/user-attachments/assets/bb9a1a97-24a5-420d-99bc-0da63e0e8f84" />
<img width="776" height="617" alt="image" src="https://github.com/user-attachments/assets/705b1ce0-0bc2-4b93-a837-ceb4f8a55719" />
<img width="614" height="450" alt="image" src="https://github.com/user-attachments/assets/b1ec1847-f9f5-4cb6-b0e4-a14fa24d7224" />

### Step 7: Set Up PHP Runtime

**Purpose:**  
Install and configure the PHP runtime environment required by osTicket.

**Instructions:**
1. Create a new folder: `C:\PHP`
2. Extract the contents of `php-7.3.8-nts-Win32-VC15-x86.zip` into the `C:\PHP` directory.
3. Run and install: `VC_redist.x86.exe` (Visual C++ Runtime)

> 🛠️ This sets up the PHP interpreter needed for osTicket to function correctly with IIS.

<img width="904" height="619" alt="image" src="https://github.com/user-attachments/assets/a016cc20-0943-4e32-b63f-4a7464f74fe8" />

### Step 8: Install MySQL Server

**Purpose:**  
Install and configure MySQL to serve as the database backend for osTicket.

**Instructions:**
1. Run the installer: `mysql-5.5.62-win32.msi`
2. Select **Typical Setup** during installation.
3. After installation, launch the **MySQL Configuration Wizard**.
4. Choose **Standard Configuration**.
5. Set the following credentials:
   - **Username:** `root`
   - **Password:** `root`

> 🗃️ MySQL is essential for storing ticket data and managing osTicket’s backend operations.

<img width="776" height="330" alt="image" src="https://github.com/user-attachments/assets/bff3291a-d0d5-4e80-9b96-03174e563591" />
<img width="488" height="380" alt="image" src="https://github.com/user-attachments/assets/4531b269-a645-4cac-9967-65d4183a5fcc" />
<img width="487" height="380" alt="image" src="https://github.com/user-attachments/assets/082efff5-83fe-4edc-9fc7-a158a260fe8f" />
<img width="495" height="375" alt="image" src="https://github.com/user-attachments/assets/737229b6-971f-4629-ab16-b25d7ae3f781" />
<img width="493" height="374" alt="image" src="https://github.com/user-attachments/assets/40afcb50-6772-4d51-b7a1-8235c0e079fa" />
<img width="494" height="372" alt="image" src="https://github.com/user-attachments/assets/36accb71-b73a-4057-8a7b-91ab7b1f0288" />
<img width="495" height="371" alt="image" src="https://github.com/user-attachments/assets/ed341715-2247-49bb-ae27-171aa2204110" />

### Step 9: Register PHP with IIS

**Purpose:**  
Connect PHP with IIS so that PHP scripts (like osTicket) can run on the web server.

**Instructions:**
1. Open **IIS Manager** as Administrator.
2. In the left pane, click your **computer name**.
3. Open **PHP Manager**.
4. Click **"Register new PHP version"** and set the path to: `C:\PHP\php-cgi.exe`
5. Restart IIS by stopping and starting it within **IIS Manager**.

> 🔁 This step ensures IIS can process PHP files through the registered PHP runtime

<img width="780" height="676" alt="image" src="https://github.com/user-attachments/assets/194b31d6-9b5c-47f8-a10b-9a83262cf537" />
<img width="792" height="408" alt="image" src="https://github.com/user-attachments/assets/8503fddf-4c36-4cd9-96b9-bc8539ecf2b3" />
<img width="702" height="303" alt="image" src="https://github.com/user-attachments/assets/7cae922a-08cb-42a8-a842-fc23ab0aef2d" />
<img width="502" height="211" alt="image" src="https://github.com/user-attachments/assets/b105ec40-6cf2-4448-8927-79e74dfa38b7" />
<img width="774" height="340" alt="image" src="https://github.com/user-attachments/assets/59fa10d4-40ac-4b54-846c-94ee69e9a067" />
<img width="774" height="337" alt="image" src="https://github.com/user-attachments/assets/147c7c4e-74c8-4709-83de-3953651a24e1" />
<img width="503" height="214" alt="image" src="https://github.com/user-attachments/assets/920ed585-0ee1-4477-ac36-b2c2df03fd71" />

### Step 10: Unzip & Move osTicket Files

**Purpose:**  
Deploy osTicket’s core files to the IIS web root so the application can run in a browser.

**Instructions:**
1. In the `osTicket-Installation-Files` folder, unzip: `osTicket-v1.15.8.zip`
2. Locate the `upload` folder inside the extracted files.
3. Copy the `upload` folder to: `C:\inetpub\wwwroot`
4. Rename the folder from `upload` to: `osTicket`

> 📂 This places osTicket’s web files in the correct location for IIS to serve the application.

<img width="779" height="336" alt="image" src="https://github.com/user-attachments/assets/22c811b3-1fa4-446a-9cf4-823026bf1c0f" />
<img width="400" height="321" alt="image" src="https://github.com/user-attachments/assets/b20a0b05-6eb1-4fd3-84c3-01ddc2c27b3a" />

### Step 11: Launch osTicket in Browser

**Purpose:**  
Access the osTicket setup page to begin the final configuration.

**Instructions:**
1. In **IIS Manager**, navigate to: **Sites** > **Default Website** > **osTicket**
2. In the right-hand pane, click **"Browse \*:80"**
3. Your default browser should open the setup page at:  
   `http://localhost/osTicket`

> 🌐 This confirms that your web server and osTicket files are correctly set up and ready for configuration.

<img width="400" height="246" alt="image" src="https://github.com/user-attachments/assets/ba700f4b-ca2e-4296-b1ef-00d591be34ac" />
<img width="400" height="487" alt="image" src="https://github.com/user-attachments/assets/3d90a611-1ac8-4349-9dd5-c95915eca488" />

### Step 12: Enable Required PHP Extensions

**Purpose:**  
Activate essential PHP extensions needed for osTicket to function properly.

**Instructions:**
1. In **PHP Manager** (within IIS Manager), click **"Enable or disable an extension"**
2. Enable the following extensions:
   - `php_imap.dll`
   - `php_intl.dll`
   - `php_opcache.dll`
3. Refresh the osTicket installer page in your browser to confirm the extensions are now enabled.

> ✅ These extensions are required for full compatibility with osTicket's features.

<img width="400" height="375" alt="image" src="https://github.com/user-attachments/assets/990cb7c8-94d3-498f-b96c-49cf23c22346" />
<img width="400" height="170" alt="image" src="https://github.com/user-attachments/assets/456518d6-58fb-4df1-9c8e-8fb0685b4189" />
<img width="400" height="483" alt="image" src="https://github.com/user-attachments/assets/31ff64e0-6d8f-465c-93dd-69cfa43c3ac7" />

### Step 13: Rename & Secure Configuration File

**Purpose:**  
Prepare and secure the osTicket configuration file before finalizing the setup.

**Instructions:**
1. Navigate to:  
   `C:\inetpub\wwwroot\osTicket\include`
2. Rename the file:  
   `ost-sampleconfig.php` → `ost-config.php`
3. Right-click on `ost-config.php` > **Properties** > **Security** tab:
   - Click **Advanced**
   - Disable **inheritance**
   - Remove all existing users
   - Add **Everyone** and grant **Full Control**

> 🔒 This ensures the config file is writable during setup but secured against unauthorized access.

<img width="235" height="146" alt="image" src="https://github.com/user-attachments/assets/62608e30-bd73-4505-b8ee-af32e258e94b" />
<img width="400" height="518" alt="image" src="https://github.com/user-attachments/assets/3d31e794-0e35-4b4e-9412-5713c3e43895" />

### Step 14: Complete the Web Installer

**Purpose:**  
Finalize the initial osTicket setup by providing basic configuration details through the browser.

**Instructions:**
1. Return to the browser and navigate to the osTicket setup page:  
   `http://localhost/osTicket`
2. Fill out the required fields:
   - **Helpdesk Name**
   - **Admin Email**
   - **Admin Username & Password**

> 📝 These details will be used to access and manage your osTicket helpdesk system.

<img width="598" height="244" alt="image" src="https://github.com/user-attachments/assets/f779d748-e400-4a85-8874-1f00b7ac63c9" />

### Step 15: Complete osTicket Installation

**Purpose:**  
Finish setting up osTicket by connecting it to the MySQL database and finalizing the install.

**Instructions:**
1. In the osTicket web installer, enter the following database details:
   - **MySQL Database:** `osTicket`
   - **MySQL Username:** `root`
   - **Password:** `root`
2. Click **"Install Now"** to begin the installation process.
3. Upon successful installation, you'll be redirected to:
   - **Admin Panel:** `http://localhost/osTicket/scp/login.php`
   - **End-User Portal:** `http://localhost/osTicket/`

> 🚀 You're now ready to log in and begin using your osTicket helpdesk!


<br />
