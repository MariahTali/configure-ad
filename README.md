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

- Create Domain Controller Virtual Machine (Windows Server 2022 named DC-1
- Ensure connectivity between the client and Domain Controller
- Install Active Directory
- Create Admin and Normal User Account in Active Directory
- Join Client-1 to your domain
- Set up Microsoft Remote Desktop for non-administrative users on Client-1
- Create additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1293" alt="Screenshot 2023-09-21 at 4 48 18 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/8f5f4296-8096-475f-b0a5-c19c36499394"><br>
</p>
<p>
Create Domain Controller & Client Virtual Machines
</p>
<br />
<p>
<img width="1287" alt="269782864-c797f515-7853-4b17-a8a4-9430f12f08dd" src="https://github.com/MariahTali/configure-ad/assets/76408932/f7d60a18-8107-4f73-8706-a277c3785094"><br>
</p>
<p>
Set Domain Controller(DC)'s NIC Private IP address to be static so that it will not change. 
</p>
<br />
<p>
</p><img width="1224" alt="Screenshot 2023-09-21 at 4 59 31 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/2aa2d674-f0e7-4ec8-9815-81cb8877f8d2"><br>
<img width="354" alt="Screenshot 2023-09-21 at 5 08 05 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/2b61abce-e9c6-411c-a551-4e8e39d4f205"><br>
<p>
Ensure you can ping DC-1 from Client-1. Perpetually ping DC-1 so that we can adjust firewall to allow icmp locally.
</p>
<br />
<p>
<img width="1538" alt="Screenshot 2023-09-21 at 5 14 02 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/12ee5eda-3a65-48a8-9d6b-acc02483aa56"><br>
<img width="1557" alt="Screenshot 2023-09-21 at 5 21 39 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/e8e77974-3d3d-4600-bc47-21ea318c4e5d">
</p>
<p>
Remote Desktop into DC-1 and Client-1 so we can access the firewall. Once logged in, search "firewall" and select "Windows Defender Firewall with Advanced Security" and "enable rule" for icmpv4 "Core Networking Diagnostics" protocols.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
