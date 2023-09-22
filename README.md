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
<img width="1522" alt="Screenshot 2023-09-21 at 5 28 20 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/0625a9ad-becb-45b6-8d33-f904613aa142"><br>
<p><img width="1243" alt="Screenshot 2023-09-21 at 5 33 05 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/686b5155-3017-41fd-98aa-8511a8071900"><br>

</p>
Install Active Directory Domain Services onto DC-1. Promote the server to a domain controller and create a new forest with a root domain.
</p>
<br />

<p>
<img width="674" alt="Screenshot 2023-09-21 at 5 46 31 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/ca0f997f-1578-4c3b-93dd-192456defcd3"><br>
<img width="617" alt="Screenshot 2023-09-21 at 5 48 06 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/3dae5d40-a4c0-4347-9660-5ca0a031e133"><br>
<img width="826" alt="Screenshot 2023-09-21 at 5 51 21 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/4e9882b3-6299-4673-98c2-cb56232f73be"><br>
<img width="981" alt="Screenshot 2023-09-21 at 5 53 59 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/c4a95f6d-f80d-4928-a76d-4812b46263b7"><br>
<img width="488" alt="Screenshot 2023-09-21 at 5 57 10 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/da6c674f-6f61-4fb2-b021-0c149d15100e"><br>

</p>
<p>
Create a couple of organizational units inside of Active Directory and create an administrative user. Then log out of DC-1 and log back in as admin.
</p>
<br />
<p>
<img width="884" alt="Screenshot 2023-09-21 at 6 07 36 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/b72759f1-7faa-4b18-8ce2-fe03eac046ea"><br>
<img width="1022" alt="Screenshot 2023-09-21 at 6 11 32 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/356a29e8-4351-4704-88e1-e4719c308f41">
<img width="763" alt="Screenshot 2023-09-21 at 6 21 30 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/f1220b9e-87ec-4607-9957-80bd0cde66fa">

</p>
<p>
Join Client-1 to domain by setting DNS to DC's Private IP address(10.0.0.4 in this case). 
</p>
<br />

<p>
<img width="891" alt="Screenshot 2023-09-21 at 6 25 50 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/10c92aa3-2488-4bf5-bc59-c1b9a4091063"><br>
<img width="976" alt="Screenshot 2023-09-21 at 6 29 15 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/663a9679-4071-4f28-af5b-12bba239413d"><br>
<img width="314" alt="Screenshot 2023-09-21 at 6 29 39 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/0c305494-50c1-40b4-a3c1-f0a49248fb7f"><br>
<img width="851" alt="Screenshot 2023-09-21 at 6 29 50 PM" src="https://github.com/MariahTali/configure-ad/assets/76408932/328e85b4-1c38-44bf-a8fe-3f4cfe421f3d"><br>
</p>
<p>
Run script to create many more users to make sure that any of them can log into client-1 and access the domain.
</p>
