<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>


# Azure-Active-Directory-Configuration

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
<img src="https://i.imgur.com/fBRzEZ3.png" height="80%" width="80%" alt="Installation Steps"/><br />
<br />- Set the domain controller VM's IP address to static to ensure proper communication between VMs on the same virtual network.<br />
<br />- Navigate to the Azure portal and open the **Networking** tab on the domain controller VM.<br />  
<br />- Select the **Network Interface** and go to the **IP Configurations** tab.<br />  
<br />- Toggle the **IP Assignment** to **Static** and save changes.<br />  
<br />- The static IP ensures the client VM can join the domain created later and serves as a reference for configurations.<br />  
<p>
