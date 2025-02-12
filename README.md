<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Domain Controller 'DC-1' in Azure
- Setup 'Client-1' in Azure

<h2>Deployment and Configuration Steps</h2>

Create a Resource Group
</p>
<br />

<p>
<img src="https://i.imgur.com/uWjEFUB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Virtual Network and Subnet
</p>
<br />

<p>
<img src="https://i.imgur.com/lW0sJgS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the Domain Controller VM (Windows Server 2022) named “DC-1”
  
Username: labuser

Password: Cyberlab123!

</p>
<br />

<p>
<img src="https://i.imgur.com/0nNWR2x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
AFTER VM IS CREATED, SET DOMAIN CONTROLLER'S NIC PRIVATE IP ADDRESSS TO BE STATIC

Networking -> Network Settings -> Network Interface / IP Configuration -> ipconfig1 -> Static
</p>
<br />
<p>
<img src="https://i.imgur.com/LNMALgA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”
  
Username: labuser

Password: Cyberlab123!

Attach it to the same region and Virtual Network as DC-1

</p>
<br />
<p>
<img src="https://i.imgur.com/4HTtz8p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
AFTER VM IS CREATED, SET CLIENT-1'S DNS SETTINGS TO DC-1'S PRIVATE IP ADDRESS

Client-1 -> Networking -> Network Settings -> Network Interface / IP Configuration -> Settings -> DNS Servers -> Custom
</p>
<br />
<p>
<img src="https://i.imgur.com/e8n5qSY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Azure Portal, restart 'Client-1' and Login to Client-1 via RDP
</p>
<br />
<p>
<img src="https://i.imgur.com/Prhc49A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Attempt to ping DC-1’s private IP address via PowerShell as Administrator
  
Ensure the ping succeeded

</p>
<br />
<p>
<img src="https://i.imgur.com/iVuxbIn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From Client-1, open PowerShell and run ipconfig /all
  
The output for the DNS settings should show DC-1’s private IP Address

</p>
<br />
<p>
<img src="https://i.imgur.com/yiXzU9w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

