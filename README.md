<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>


# Azure-Active-Directory-Installation

<br /><h2>Objectives</h2>
This project demonstrates the setup and configuration of an on-premises Active Directory environment within Azure virtual machines. It covers creating a virtual network, setting up domain controllers. <br />

<h2>Skills</h2>

- Azure Administration
- Active Directory Deployment
- Virtual Machine Configuration
- Group Policy Management



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Active Directory Domain Services 
- Powershell

<h2>Operating Systems Used </h2>

- Windows 10 Pro (21H2)
- Windows Server 2022

 

<h2>Actions and Steps</h2>
<p>
<img src="https://i.imgur.com/FaSE8Tj.png" height="80%" width="80%" alt="Installation Steps"/><br />
<br />- Set the domain controller VM's IP address to static to ensure proper communication between VMs on the same virtual network.<br />
<br />- Navigate to the Azure portal and open the **Networking** tab on the domain controller VM.<br />  
<br />- Select the **Network Interface** and go to the **IP Configurations** tab.<br />  
<br />- Toggle the **IP Assignment** to **Static** and save changes.<br />  
<br />- The static IP ensures the client VM can join the domain created later and serves as a reference for configurations.<br />  
<p>
<img src="https://i.imgur.com/4JnmUBm.png" height="80%" width="80%" alt="Installation Steps"/><br />
<img src="https://i.imgur.com/F2mPzFY.png" height="80%" width="80%" alt="Installation Steps"/><br />
<img src="https://i.imgur.com/fBRzEZ3.png" height="80%" width="80%" alt="Installation Steps"/><br />

<br />- Log in to the client VM and check connectivity to the domain controller using `ping -t (domain controller private IP)`.  
<br />- Observe the the connection.<br />
<br />- From Client-1, open powershell and run `ipconfig /all` <br />
<br />- Observe DNS output settings showing DC-1 private IP address 
  

<img src="https://i.imgur.com/fBRzEZ3.png" height="80%" width="80%" alt="Installation Steps"/><br />
<br />- Open **Server Manager** on the domain controller VM.  
<br />- Click **Add Roles and Features** and proceed through the wizard:  
  1. Confirm the domain controller's private IP address.  
  2. Select **Active Directory Domain Services** in the **Server Roles** tab.  
  3. Click **Add Features**, then **Next**, and click **Install**.<br />
<br />-Promote the server to a domain controller:
  1. In **Server Manager**, click the warning flag in the top-right corner.  
  2. Select **Promote this server to a domain controller**.  
  3. Choose **Add a new forest** and enter a domain name (e.g., `ernestotest.com`).  
  4. Set a domain password, click **Next** through the screens, and click **Install**.
   

  <h2>An Important Note </h2>

- Log back into the domain controller VM using Remote Desktop Connection.  
- Enter login credentials in the format: `domain.com\username` (e.g., `ernestotest.com\labuser`).  
- Active Directory is now installed and ready for future configurations.  
- The client VM can now join the newly created domain.  
